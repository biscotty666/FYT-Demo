---
aliases:
fileClass: [Default, article, project]
---
%%
topic:: [[Obsidian]]
related:: 
created:: 2023-10-05 Thu 
last edit:: 2023-10-05 Thu 
type:: article
action:: true
title:: Obsidian: Pretty Canvas
Published to:: Medium.com, SubStack, biscotty.online
link:: 
Author:: [[Brian Carey]]
PubDate:: 2023-10-05 Thu
Published:: true
Cover:: ![[canvas--pretty-css-composite.png|100]]
Stage:: published
Project Name:: Lemmy
Item Notes:: Add to Lemmy?
Item Status:: 
Item Action:: Lemmy Links
%%
# Pretty Canvas

Going visual has really helped free my thinking, and pretty much all of my time in Obsidian is now spent on canvases. Other than when I am making fleeting notes on an article, book or video, I do pretty much everything from a canvas. I process and edit my notes, list questions which guide my research, maintain tasks associated with the effort, and perhaps develop an article on the topic, all from the canvas.

Naturally I want my canvases to be pretty. It's not just a question of aesthetics either. Changing simple things like the color or size of elements makes the canvas much more use-able, drawing your eyes quickly to more important information and removing extraneous stuff. Obsidian fortunately allows us to use [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) to do this.

Here's an example of a Visual Dashboard I'm just getting started with for a new article. The first image is with default styling. It is usable, and has some pretty colors, but it's visually confusing.

![[canvas-plain.png]]

There are too many colors for one. The title of the canvas doesn't stand out, and the group headings don't either. There is also a bunch of stuff that I don't need to see, like the links after every task.

Here is the same with CSS applied. Notice how some useless clutter has been removed, task descriptions have a standardized color which is easy to read, group headings stand out better to guide your eyes, and titles look good.

![[canvas-pretty.png]]


# Implementation

## Getting Started

Using CSS is pretty straight-forward in principle, but figuring out how to apply it can take a bit of work, as there seems to be no good documentation for automatically generated classes. Also, CSS is simply unfamiliar to many people. Never the less, a little can go a long way. So I wanted to share some of the styling I'm using for my canvases as a jumping-off point for you to personalize your canvases and be more efficient in working with them.

To get started, you need to create a `snippets` directory in the hidden `obsidian` directory of your vault. Any files placed here with the extension `css` will be available to Obsidian. You can name the files anything you want, so choose a descriptive name. With obvious irony, these files can only be edited with an external editor, but any editor will do, like vim, nano or Notepad. I suggest you create a file called `canvas-fyt.css` and copy the contents below into the file. In Obsidian, you will be able to "activate" whichever files you want to use, so you can have multiple styles of canvases.

Once you have created a `css` file in the correct directory you can go to the  <span class="cta">Appearance</span> section and toggle on the new file to make it active.  You may need to press the <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-refresh-cw"><path d="M21 2v6h-6"></path><path d="M3 12a9 9 0 0 1 15-6.7L21 8"></path><path d="M3 22v-6h6"></path><path d="M21 12a9 9 0 0 1-15 6.7L3 16"></path></svg> button to re-scan the directory.

![[Enable CSS.png]]

## Background

With that done, let's start with the background.  Add the following to the file to change the color and remove the dots:

```
svg.canvas-background {
	background: linear-gradient(80deg, #253B0B, #2c0149, #390B1C);
}

svg.canvas-background circle {
	display: none;
}
```

The background is actually an image of the type svg, which stands for Scalable Vector Graphic (as compared to png or jpg). The svg is automatically assigned the class `canvas-background`. By writing `svg.canvas-background`  we select only the background image and not any other svg files which might be on the canvas. As you can see, styles use key/value pairs followed by a semi-colon. I've used a gradient here, but if you only want a single color, you could simply write `background-color: tan;` for example. There are over 150 [named colors](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color) which you can use. If you have an RGB value from a color picker, you can write `background-color: rgb(10,160,245);`.

`display: none;` says not to display a particular element, in this case the grid dots (circles). We'll use this again later. 
## Tasks

Next we can style the tasks. Adding 

```
.task-description {
	color: cyan;
}

.tasks-backlink {
	display: none;
}
```

will change all of the task descriptions to a consistent and easily readable color. It also removes the backlink text which points to the file containing the task. I'm not interested in files, so this is useless to me but takes up a lot of visual space.

## Titles/Headers

With that done we can turn to the textual elements. For these, you must specify on the canvas which elements you want to apply the styles to. For this you need to use HTML instead of markdown, allowing you to assign a _class_ to an element. Let's style the headings which I will use for titles so they stand out. 

```
.markdown-rendered .title-tag-1 {
	text-align: center;
	font-size: 4em;
}
.markdown-rendered .title-tag-2 {
	text-align: center;
	font-size: 3em;
}
.markdown-rendered .title-tag-3 {
	text-align: center;
	font-size: 2em;
}
```

On the canvas, in order to use the styles, you can't use the standard hash tags (`#, ##, ###`) for headers. Instead you need to use HTML and specify the class. For example, instead of writing `# Header` you write `<h1 class="title-tag-1">Header</h1>`. Then you will see the styles applied to the class.

Notice the units used for the font size. You can use different units for font size such as pixels (`font-size: 24px;`). `em` is convenient though, because it is a relative size. `2 em` is like saying "display this twice as large as it would normally be displayed". The actual size will change based on the zoom level.

## Other textual elements

I also like to be able to have certain words jump out on the page, more than can be achieved with bold or italics. So I have a class

```
.markdown-rendered .my-emphasis {
	color: #b7db6f;
	font-size: 1.2em;
}
```

I can use this class by wrapping text in a `<span>` element like this:

```
In this paragraph <span class="my-emphasis">these words</span> will stand out.
```

In this paragraph <span class="cta">these words</span> will stand out.

To change the font, add

```
.markdown-rendered {
	font-family: "Quicksand", sans-serif;
}
.canvas-group-label {
	font-size: 2em;
	font-family: "Quicksand";
	font-weight: bold;
	color: black;
}
```

I like the Quicksand font. It is a [free font](https://fonts.google.com/) from Google, which provides a huge variety of fonts. In order to display a font you must download it and install it to your system. If it is not on your system, the default sans-serif font will be used instead. As you can see, I've also changed the size, color and weight of the labels for the groups on the canvas.

Finally, I would like to have the filenames of links on the canvas to be a different color, so 

```
.markdown-rendered .internal-link {
	color: red;
}
```

And that's it. For convenience I provide the complete file below. I hope adding some style will enrich your experience working with your Visual Dashboards.

# Final File

```
svg.canvas-background {
	background: linear-gradient(80deg, #253B0B, #2c0149, #390B1C);
}

svg.canvas-background circle {
	display: none;
}

.markdown-rendered .title-tag-1 {
	text-align: center;
	font-size: 4em;
}
.markdown-rendered .title-tag-2 {
	text-align: center;
	font-size: 3em;
}
.markdown-rendered .title-tag-3 {
	text-align: center;
	font-size: 2em;
}
.canvas-group-label {
	font-size: 2em;
	font-family: "Quicksand";
	font-weight: bold;
	color: black;
}

.task-description {
	color: cyan;
}

.tasks-backlink {
	display: none;
}

.markdown-rendered .internal-link {
	color: red;
}

.markdown-rendered {
	font-family: "Quicksand";
}

.markdown-rendered .my-emphasis {
	color: #b7db6f;
	font-size: 1.2em;
}
```








