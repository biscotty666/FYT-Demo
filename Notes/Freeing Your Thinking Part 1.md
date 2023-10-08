---
aliases: FYTP1
fileClass: [article, project]
---
%%
status:: 100
related:: [[Freeing Your Thinking Part 2]], [[Freeing Your Thinking Part 3]]
created:: 2023-08-22
last edit:: 2023-10-02 Mon
action:: false
title:: Freeing Your Thinking, Part 1
link:: 
Stage:: published
Cover:: 
PubDate:: 2023-08-24 Thu
Item Action:: 
Published:: true
Project Name:: New Site
Item Notes:: 
Item Status:: alpha
Action Note:: Add to Lemmy
Cover:: 
topic:: [[Freeing Your Thinking]]
Author:: [[Brian Carey]]
Published to:: Medium.com, SubStack, biscotty.online, lemmy.world
type:: article
%%
# Obsidian - Freeing Your Thinking

## Part 1: Stop Wasting Time With Directories and Filenames

### The Problem

Because we’ve all used computers, when we think of organizing our stuff we naturally think in terms of files and directories, and are aware of the value of descriptive file names. Personally, if I even need to scroll down to see all the files in a single directory, it’s probably time for a subdirectory. And I'm equally unsettled when I see files with meaningless or unclear names. Many people like me explore various systems like PARA, ACCESS, LATCH, etc. to organize our stuff.

To be explicit, the stuff referred to here is files. But we use Obsidian for information management, not file management.

Obsidian stores information, but it’s not a database, at least not an SQL database. It is essentially a NoSQL database (more on that in Part 2 and 3). It stores information in text files, but it doesn’t care where the files are nor what they are called. So why should we care?

I should point out that the word “notes” can mean two different things, really: the file or the information it contains. Decoupling the two meanings, I really only care about the information. The file must exist, of course, but it is not important. What is important is the information in it.

If I think in terms of files, I need to spend time thinking about file names and locations, both when recording and retrieving information. I need to navigate to files and directories and/or think about and type out file names. This is all wasted time because, again, the files aren’t important, it’s the information in them that I care about.

Obsidian is powerful and allows us to work with our information in many ways without stopping our flow of thought to worry about files. Stop spending your time in the Navigation pane and start using Search and Bookmarks. That way, you can focus all your attention where it should be, on your information.

### Information First

Ok, full disclosure, I do use two directories in my vault, one for templates and one for non-md files. Templates would be impractical to use lumped with all the other files. And attachments aren’t native Obsidian formats and raise other maintenance issues.

Obsidian offers core functionality that allows me to ignore files and focus on information. I’m referring to Search, Bookmarks and Unique Notes. The latter is effectively invisible in articles and videos, and the other two rarely come up. This is especially surprising with regard to Search because that’s the most efficient and powerful way to find information in your vault. Most presenters use Quick Switcher or the Navigator to create and access files in order to create or access information. This is an extra step, wasting time and energy and impeding the flow of thought.

`Ctrl-Shft-F` is all I need to do to start querying my information. I don’t need to open any files, I just start typing what I’m looking for. If I think I might look for the same or similar information later, I can bookmark the filter.

When I want to write something down, I hit `Ctrl-U` (I’ve got an assigned hotkey), type my thought, then immediately return to my reading. Again, I don’t have to think about files and directories. It’s that simple, fast, and does not impede my thinking with irrelevant considerations and extra keystrokes.

### Search

Simply typing the word or phrase I’m looking for in the search field will bring up all directly relevant notes on my topic. In case of TMI, I can specify that the terms should be in the same section or the same line. With Hover Editor, I can see the contents of each file listed without opening it, and even modify content directly if I want. I don’t need to actually open a file to get the information I’m looking for, or even modify it.

Search filters are just as powerful as Dataview queries. I can use logical AND, OR and NOT, group them with parentheses and sort by modified date. I can include or exclude based on any criteria (WHERE) and specify source (FROM). And I can save the filters as bookmarks. This way I don’t need to have a file that contains a query. The query results don’t “live” in a file, either. I do use Dataview queries frequently to aggregate information that I want to display information in notes. I do not use it to aggregate files that I want to interact with. That’s what Search is for.

### Bookmarks

I can bookmark files, of course, but I don’t… instead I bookmark sections or blocks (information, not files). I can also bookmark searches and graphs, and organize bookmarks in directories and subdirectories. In most of the videos I see, people have the Navigator panel open “by default”. For me, it’s the bookmarks panel. The Bookmarks panel provides an information tree, the Navigator panel provides a file tree. I want the information tree.

I can use bookmarks and metadata to mimic directories if I want. My new notes used to go in a certain directory called +, and I had an “Inbox” note with a Dataview query to display the notes. The default template I now apply to every new note contains a field status:: new. I have also bookmarked a search filter “status:: new”. To see all of my new notes, I don’t need to open a directory or go to a file containing a Dataview query. All I need to do is click on the bookmark.

Any useful search can be bookmarked. I have a bookmark, “action”, for example, which shows all files requiring attention. I always have many bookmarked searches and graphs related to topics I'm focused on, organized in virtual directories.

### Unique Notes

Most people are unfamiliar with Unique Notes, even though it is a core plugin. This plugin will generate a new file with a unique name in a pre-defined location and automatically apply a specified template. The idea of randomly-named files dumped in one directory does seem scary, but don’t worry. The default template is, for me at least, entirely metadata. Metadata can be either frontmatter or double-colon in-line style. My template currently looks like this:

```

%%
topic-ex:: 
related-ex:: 
created-ex:: 2023-10-06
last edit-ex:: 
type-ex:: article
status-ex:: 0
source-ex:: 
title-ex:: 
link-ex:: 
action-ex:: false
%%
```

topic and related take meaningfully named links, possibly to non-existent files (Obsidian doesn’t care about existence either). type can be atomic, moc, log, etc. Everything else should be self-explanatory. I don’t have to fill any of this in when I’m making notes. I can just jot down the thought and keep reading and thinking. And I can get back to them later by opening my bookmarked “status:: new” search. When I revisit the note to make it atomic, I can fill in the rest of the fields.

With this plugin, as I said earlier, I just press Ctrl-U and start writing my information without ever thinking about file names and directories.

Efficiency Tip: When I’m reading a book or article, knowing I will take several notes in succession from the same source, I temporarily edit the default template to include basic information like source, title, etc. so I don’t have to type what is essentially boilerplate when I process the note and make it atomic.

### Try it out without commitment

Since I started with Obsidian, I’ve changed the way I work multiple times. But rarely do I need to “clean up” old notes. For example, as my logging system has evolved, I have left all my old logs and their related Dataview queries in place, adding the newly written queries above them. It just means I have multiple query blocks instead of one in my Exercise Note, for example, but the information displayed remains the same.

Fuller disclosure: I actually have more directories in my vault than just templates and attachments. I used to use the ACCESS directory structure and have many, many notes. When I switched to this information first way, I stopped caring about files, remember, and I didn’t want to start this journey by launching into a massive exercise of moving files around, and adding metadata to all my old notes. That would be unacceptably ironic.

Obsidian is truly a compassionate ally. Very little needs to be done. I had to re-write some queries, as mentioned above. But any Dataview queries which aggregated files instead of information are no longer necessary anyway. For example, my Inbox note that displayed my new notes became irrelevant, since I now have a bookmarked filter, “status:: new”. If directory locations were really important in some queries, just add “(path:old-directory) OR” to your filters.

You could just continue to keep your Calendar notes in the same place as you do now, for that matter, or any other plugin that already has directory locations specified in settings. There is no need to be doctrinaire and rigid, after all, since we don’t care about directories anyway. Keep it simple, flexible, and don’t waste time on things that don’t add value.

Finally, I’ll point out that I didn’t give up on meaningful file names, just at the point of initially writing down an idea. One step in processing a note to ensure its completion and atomicity is to change the name of the file. At the processing stage, choosing a name does not interrupt the flow of thinking, but complements it, since it helps encapsulate an idea and solidify my understanding. It’s just not something to do when making a fleeting note, that’s all. And the name will be useful later.

### Closing Thoughts

This article covers recording and retrieval of information. The second part covers how to analyze and synthesize information with this system.

I hope I have convinced you at least to give it a try. Obsidian offers so many ways for us to free our thinking and focus on information and flow of thought. Keep the file tree closed, instead use the information tree.

I am aware that this topic may be controversial because it goes so clearly against most of the approaches proposed on the internet. I do not mean any disrespect to the authors and videographers who have helped and inspired my journey with Obsidian, and to whom I am grateful.

Continue to [[Freeing Your Thinking Part 2|Part 2]]




