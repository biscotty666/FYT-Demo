---
fileClass: [Default, article, project]
---
%%
topic:: [[Obsidian]]
aliases:: 
related:: [[Obsidian Metadata]], [[Metadata]], [[Regular Expressions]]
created:: 2023-09-09 Sat
last edit:: 2023-09-09 Sat 
type:: article
status:: 100
action:: true
title:: Obsidian: Searching in-line metadata (properties) with regular expressions
Published to:: Medium.com, SubStack, biscotty.online
Item Action:: Lemmy Links
link:: 
Author:: [[Brian Carey]]
PubDate:: 2023-09-09 Sat
Published:: true
Project Name:: New Site
Item Notes:: Add to Lemmy?
Item Status:: alpha
Action Note:: 
Cover:: 
Stage:: published
%%
# Obsidian: Searching in-line metadata (properties) with regular expressions
If you are like me and use in-line (double colon) fields more than YAML, the improvements to metadata management (Properties) wasn’t much of a help. The new filter syntax, `["key":value]`, and the glob version, `["key":]`, don’t search in-line fields.

Of course, this isn’t unexpected. Obsidian, for what I’m sure are good reasons, resists embracing in-line metadata, even though it is very widely used. Oh well, hope springs eternal… Nevertheless, though I’ve tried many times, I can’t give up on the convenience of in-lines.

Because in-line fields use two colons, which do not appear together in ordinary writing, it is easy to filter for them. For a glob filter like `["key":]` in the new Properties, you can simply use `"key:: "` to achieve the same effect, querying in-line metadata instead of YAML.

Filtering for specific values is a little trickier, because we must take into account multi-value fields. Fortunately, Obsidian allows us to use regular expressions in filters, and a simple one will achieve our goal. To use regular expressions, use the slash, `/`, as a delimiter instead of `"`. (In the example above, we actually could have used `/key:: /` instead of `"key:: "`.)

In regular expressions, a period, `.`, matches any character, and an asterisk, `*`, indicates that there can be 0 or more of a character. By putting the combination `.*` before the value that we are filtering, we are saying that there may or may not be other characters between the field name and the value being searched. In other words, there may be multiple values.

So, even if the value we are looking for is one among many, to search for a specific key/value, you can use `/key:: .*value/`, which does the same as `["key":value]` does for YAML.

---

[Obsidian at biscotty’s Workshop](https://biscotty.online/obsidian)