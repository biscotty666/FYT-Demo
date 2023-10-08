---
fileClass: [Default, article, project]
aliases:
  - Information Tree
  - Knowledge Tree
---
%%
topic:: [[Notes/PKM]], [[Obsidian]]
aliases:: 
related:: 
created:: 2023-09-06 Wed
Item Action:: Final Review, Lemmy Links
last edit:: 2023-09-11 Mon
status:: 100
action:: false
title:: Obsidian Bookmarks 
link:: 
Author:: [[Brian Carey]]
PubDate:: 2023-09-10 Sun
Published:: true
Cover:: 
Stage:: published
Published to:: Medium.com, SubStack, biscotty.online, lemmy.world
type:: article
Project Name:: New Site
Notes:: 
Project Description:: New Site
Project Status:: alpha
Item Notes:: 
Item Status:: alpha
Action Note:: 
%%
# Obsidian Bookmarks


Bookmarks are the key to effectively using obsidian as a non-relational database. The virtues of approaching your notes this way are several and I covered some in [[Freeing Your Thinking]]. In this article I want to develop the idea of using Bookmarks to construct flexible, interactive Knowledge Trees to organize notes. Just as a reminder, we are organizing information, not files.

The Navigation tab gives at best a static arrangement of information, while the Bookmarks tab provides a dynamic way to interact with, develop and access your information. Here you can create _Views_ of your information which you can organize by domain, subject, activity, etc. Views are saved filters and queries. Your information, unlike your files, can happily exist in multiple places in your Knowledge Tree.

When you begin to build your Knowledge Tree, you might start by creating *Views* which map to your current directories using filters. After all, you want to preserve the information you have put into your vault by organizing your notes in a File Tree. Most people have a separate directory for fleeting notes, so you might make a view containing `path: "fleeting-note-directory"`. But is such a view terribly useful? Browsing through all your fleeting notes is fun if you've nothing better to do, but it's not focused or efficient use of time if you are working on a particular topic. Wouldn't it be better to just see the fleeting notes related to my topic? So I save the filter `Whatever Topic \type:: fleeting\` alongside my views of the topic itself and have a list of fleeting notes only on that topic.

As you start mapping your old directories to views, you might begin to ask yourself at some point why you would ever really want to see all your MOCs in a list? Or Daily Notes? Or Logs? If you want *information* from these types of notes you typically create a note containing a Dataview query. Bookmarked filters, which I'm calling views, are like virtual Dataview queries. And, since you can do this without referencing file locations, you might question how much useful information was actually embedded in your folder structure. Then you might have a cup of tea.

One last point to stress: the bookmarks, which I will call views, are ephemeral. They can be created, duplicated, renamed and moved around without affecting the information itself. When focusing on a topic, drag it to the top of the tree and put it back when you are done.
## The Mechanics
### Commands
The following table shows the bookmarks commands with suggested Hotkeys which are most likely unassigned.

|Command|Description|Hotkey|
|---|---|---|
|Bookmark...|Bookmark current file|`Ctrl-Cmd-Alt-M`|
|Show Bookmarks|Open bookmarks panel|`Ctrl-B`|
|Bookmark Current Search||`Ctrl-Cmd-Alt-S`|
|Bookmark Current Block|Bookmark Block Under Cursor|`Ctrl-Cmd-Alt-B`|
|Bookmark Current Heading|Bookmark Heading Under Cursor|`Ctrl-Cmd-Alt-H`|

### Bookmarks Panel
The panel lists all bookmarks, which, remember, are saved searches, or views. In the panel you can create, rename and delete bookmark groups to organize your bookmarks. Bookmarks can be dragged around to rearrange them.
## Knowledge Trees

When working with a database, we typically create views. Views are subsets of your information based on queries which have been saved. They can be used passively, as a way to look at certain information on a certain topic. They can also be used interactively, as a basis for more fine-grained queries, which, if interesting, can themselves be saved as views.

I have my Knowledge Tree organized by the different domains of my life, Living, Learning and Creating. In addition, I have a section with utilities I call the Toolbox.
### Living
This is the structure of my Living section:

```
- Daily Notes
- Logs
	- Exercise
	- Piano
	- etc.
- Daily Notes
- CV 
- People
- Leisure
```

*Daily Notes* is a view of `type:: daily`.  Exercise and Piano are actual files with interactive Dataview queries. The rest are bookmark groups containing other views.
### Learning 
I use *Learning* for study and research activities. This part of the tree is the most complex in terms of structure. 

By creating multiple views on a given topic and organizing them in folders I can essentially create an outline of my information using views. This kind of outline, again, is very flexible and can be reshaped easily as my knowledge develops.

This is an excerpt of my section on the normal distribution. It's "home" is in the bookmark group `Learing/Data Science/Probability/`.

```
Normal Distribution                 # All information on the Normal Distribution
Normal Distribution                 # The reference note on the topic
                                      The 2 are distinguished by different icons
Central Limit Theorem               # A bookmark group containing other views
68-95-99.7 Rule                     # A view of a block in a note
R Functions for Normal Distribution # A view of a section of a note
```

### Creating
is for writing and creation of other content. Creating includes works for external and internal use.

```
- Articles 
- Stories
- Video Scripts
- Musings
```

### Toolbox
In the toolbox I have the following directories, which should be self-explanatory:

```
- Templates
- fileClasses
	- Class Definitions
	- Value Lists
- Fleeting Notes
- Other
	- Articles 
	- MOCs
	- References 
	- Atomics
```

Other than templates and fileClasses, I rarely use the Toolbox.
## Conclusion
I hope I have adequately conveyed some of the advantages of building Knowledge Trees. Maybe you noticed that the word "tree" is actually a misnomer. The branches of real trees don't reconnect, but ours can. What we really have is a Knowledge Network. Bookmarks allow us to leverage Obsidian's NoSQL features to free our Second Brain.


