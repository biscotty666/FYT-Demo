---
cssclass: "qs-html"
fileClass: [Default, article]
related: 
---
%%
title:: My Logging System
Published to:: 
link:: 
Author:: [[Brian Carey]]
topic:: 
related:: 
PubDate:: 
Published:: false
Cover:: 
Stage:: shelved
topic:: [[Obsidian]]
aliases:: 
created:: 
last edit:: 2023-09-09 Sat
status:: 75
action:: false
topic:: 
type:: article
%%
# Logging in Obsidian

## Motivation
I like to keep track of the work I have done in some of my activities. Up until recently I have done this rather simplistically leveraging my daily note for log entries with a special setup for my exercise logs[^2]. I recently started using Todoist for task management and that has required (inspired 🤔) me to re-think how I keep my logs. I would like to do all of this in [Obsidian](https://obsidian.md) with basic plugins except the actual task management. The Obsidian [Todoist](https://todoist.com/) plugin is very good but still lacks some basic functionality.

[^2]: I use an app on my phone to track my ride. My exercise logs are special because they contain an html iframe (`<iframe src="url-from-app" height=700px width=700></iframe>`) which displays the ride statistics exposed on a web page by the app.

Specifically I want to be able to:
- Add log information to a note
- Create arbitrary log entries 
- Display the day's logs on the Daily Note 
- Create views based on, eg., type of entry or topic
- Make log entries from anywhere rapidly with only 1 or 2 keystrokes/clicks

Here I will describe the Ultimate Logging Solution. Well, my current solution anyway 😉. In the process of developing this I discovered a use for the often ignored core plugin _Unique Note Creator_ [^3]. In addition I will use the *Dataview* and *Templater* plugins. I will not go into detail in relation to these plugins but you should be able to easily modify the examples I give.

I should say that this is aimed at users familiar with the plugins used and are comfortable using Obsidian and so I won't be explaining the Dataview queries and Templater commands. Never-the-less none of this is too fancy and beginners should be able to easily follow along and at least imitate the implementation.

[^3]: This plugin is designed for a purist sort of Zettelkasten where file names and directory structures are not important. It is true that Obsidian does not care about such things and, within the limitations of your file system, is perfectly happy to have everything in one directory with arbitrary file names. After all, every time you search for a file based on it's name you are not making use of one of the most powerful aspects of Obsidian: it's search functionality (`Shft-Ctrl-F` is your friend), I still cling to the old ways myself. I like to see the names of the notes in Graph View.

## Implementation

I will use *tags* to indicate a log entry. I'll create template "snippets" which can be inserted in existing documents to make a log entry related to that note. I will also create a template for a new "Log Note" with a guaranteed unique name for log entries not linked to a specific note. 

I will add _Dataview_ queries to my daily note to show the day's activities. Finally I will create a note which gathers all log entries for a specific log topic, also with *Dataview* queries.

### Tags

In order to easily work with _Dataview_ I'll use tags to indicate log entries. In my case I'll use the following tags, each representing a type of activity I'd like to track:

```
#log/study 
#log/project 
#log/infrastructure 
#log/exercise 
#log/piano
#log/domestic
```

Using these tags will make it easy to write my queries. By the nature of tags in Obsidian this will automatically create a bare `#log` tag which I can use for queries across different types of activities.

### On-the-fly Log Entries 

Before setting up the generic log entry template we need to enable the "Unique Note" core plugin. Once enabled we need to define a directory and a template for the plug-in to use. In my file structure the appropriate directory is called `Extras` so I created a directory called `Extras/Logs`. I decided to keep the template itself here as well instead of with my other templates 🤷 so I also created a note called `Extras/Logs/Log Entry`. 

In Obsidian's settings, toggle on the _Unique note creator_ plugin under _Core Plugins_.

![[Screenshot_20230729_121842b.jpeg]]

![[Screenshot_20230729_122215.jpeg]]

This plugin enables a new command, `Create new unique note`. I assigned this to a hotkey because it's __The Right Thing To Do__ 😉.

![[Screenshot_20230729_131915.jpeg]]

I created the file `Extras/Logs/Log Entry` which looks like this:

```
# Log Entry

tags:: #log 
Date:: 2023-10-06
Topic:: 
Notes:: 
Related:: 
References:: 
```

As you can see I have provided the generic tag #log as a default. This will be changed to the specific log tag when making the entry. Also note that I'm using *Templater* to provide the date automatically.

I plan to use these fields as follows:
- `Topic` will be a link to one or more Maps of Content. (Thanks to Obsidian these need not already exist to be useful.)
- `Related` may contain links to other notes or MOCs
- `References` are for external resources. These could be web links or book/article references
- `Notes` is for comments, descriptive information, and other text to put in the log

Now any time I want to make a log entry I can simply to `Ctrl-Alt-Sftd-L` and I have a new, uniquely named note in which I can make my log entry. The most common use-case for this type of note is to log certain tasks when I've completed them. (I use Todoist with the Obsidian plugin for task management.)

### Add Log Entries to Existing Notes

Sometimes I want to make a log entry in a note I am working with. For example, I'm learning how to do things in NixOS which I recently installed. They have great documentation, and I'll typically create a note from the page (with the _Surfing_ plug-in.) After working through the page and making new _atomic notes_ (from the information by `Extract current selection` and writing the information in my own words, but with the referred to text). After working through the page I might want to make an entry in my _Study Log_, and if it leads to some change on my system I might want an entry in my *Infrastructure Log*.

I need 2 templates for this:

```
%%
#log/infrastructure
Topic:: 
Note:: 
Date:: 2023-10-06
Related::  
%%
```

```
%%
#log/study
Topic:: 
Note:: 
Date:: 2023-10-06
Related::  
%%
```

Note that the use of `%%` prevents the fields from showing in *Read View*. Now to log relevant information from within the note I'm working on I just need to `Ctrl-T` to insert a template and I can again fill in the relevant information.

NB. Unfortunately a given note can only contain one log entry or the *Dataview* queries break since there would be multiple fields with the same name[^1]. 

[^1]: I know I could create more specific fields for each snippet to have multiple log entries in a single note, but to make the unique note I need generic field names.  So this is a trade-off for the ease of automatically generating unique note names. I do not anticipate this as a problem for what I'm logging, though. And it's easy to just make a stand-alone log note and link to other notes with the `Related` field. Adds a keystroke on the rare occasion.

### The Daily Note

One use of these logs is to see my daily activity. To do this I have created a section in my daily note for logs.

![[Screenshot_20230729_135721.jpeg]]

This is the query  I used
```
```dataview
table without id
topic as Topic, file.name as Reference, note as Note, date as Date, related as Related, references as References
from #log/study & -"Extras/Templates"
where date = date("2023-10-06")
```

The templater command will supply today's date. Note that the basic filter is the tag, and each activity log has the same structure with that being the only change. Also you can see that I am ignoring any templates that might have the tag in them.

### Sample Topic Report

Here is an example of a view of all my log entries related to NixOS

![[Screenshot_20230729_150225.jpeg]]

And this is the query I used:

```
table without id
date as Date, notes as Note, related as Related, file.etags as Tags, file.name as Reference
from #log & -"Extras/Templates"
where topic = [[NixOS]]
sort date desc
```

(I started out using tags for topic metadata but find that using a Map Of Content is better for a number of reasons. Simply put, that way I use linking instead of marking to indicate what are ultimately relationships between notes.)

## Closing thoughts

It is so interesting to me how often working with Obsidian has led me to change the way I think about things and how I do things. Going through the process of developing this system has led me to reflect on my work patterns and where I can make them more efficient. 

> Brian Carey, Albuquerque, 2023

---

## Resources

### The Official Word
[Obsidian - Sharpen your thinking](https://obsidian.md)

[Todoist | A To-Do List to Organize Your Work & Life](https://todoist.com)

[Dataview](https://blacksmithgu.github.io/obsidian-dataview/)

[Introduction - Templater](https://silentvoid13.github.io/Templater/introduction.html)

[Obsidian HTML Export](https://github.com/KosmosisDire/obsidian-webpage-export)

Just because I referred to it: [Nix & NixOS | Reproducible builds and deployments](https://nixos.org/)

### Masters, Muses...

[FromSergio](https://youtube.com/@FromSergio)

[Linking Your Thinking with Nick Milo](https://youtube.com/@linkingyourthinking)

[Zsoldt's Visual Personal Knowledge Management](https://youtube.com/@VisualPKM)

[Nicole van der Hoeven](https://youtube.com/@nicolevdh)

### ...and Me

This file and other content can be found in my [GitHub repository](https://github.com/biscotty666/OBSPKMEssentials) where you can also make comments. ☮🤎

<span class="imgcenter">![[CL2.png|100]]</span>

