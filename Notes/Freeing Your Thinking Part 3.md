---
fileClass: [article, project]
aliases: NoSQL Obsidian
---
%%
related:: [[Notes/PKM]], [[Freeing Your Thinking Part 1]], [[Freeing Your Thinking Part 2]], [[Obsidian]]
created:: 2023-08-22 Tue
last edit:: 2023-08-24 Thu
title:: Freeing Your Thinking Part 3
link: :
Author:: [[Brian Carey]]
Stage:: published
PubDate: 2023-08-24 Thu
Item Action:: Final Review, Lemmy Links
action:: false
status:: 100
topic:: [[Freeing Your Thinking]]
link:: 
PubDate:: 2023-08-29 Tue
Project Name:: New Site
Item Notes:: 
Item Status:: alpha
Action Note:: 
Published:: true
Cover:: 
aliases:: 
Published to:: Medium.com, SubStack, biscotty.online, lemmy.world
type:: article
%%

# Obsidian - Freeing Your Thinking
## Part 3: Obsidian is a NoSQL Database
### SQL and NoSQL
There are two different types of databases, relational and non-relational. Relational databases are the kind most people usually think about. Data is kept in tables, with columns for fields and rows for values. The tables have special columns which relate (link) them to other tables. A well-formed table in a spreadsheet is a database. If two are linked by a common column, that is a relational database.

Obsidian is obviously not a relational database.

SQL stands for Structured Query Language, and it is the syntax which was designed to work with relational databases. The association of the syntax and data structure is so strong that relational databases came to be referred to as SQL databases, even though SQL, the language, can be used with any type of database.

An SQL query should look familiar to you if you have used Dataview:

`SELECT name FROM users WHERE location = “Earth” ORDER BY age;`

It’s just like Dataview queries, yet Obsidian is not an “SQL database”. My point is that we can use SQL queries to access our data even if it isn’t a relational database.

The other type of database, a non-relational database, is unfortunately called a NoSQL database. SQL, the language, can still be used to query data in a NoSQL database. If I’ve adequately confused you, let’s proceed.

Rather than storing data in tables, NoSQL databases store data in documents. Documents are text files written in a standard format, usually JSON (JavaScript Object Notation) but frequently YAML, which is the syntax used in frontmatter in Obsidian.

In a NoSQL database, documents contain information and metadata in key/value pairs. The metadata can be used to make relationships (links) between data (information). NoSQL databases are flexible and new key/value pairs can be added to a document without modifying a whole table. None of the relationships need be pre-defined, nor need they be hierarchical. NoSQL databases are ideal for data structures which consist of nodes (documents) and edges (links). Does any of this sound familiar?

Obsidian is a NoSQL database.

### On Ontologies

Commonly used organizational systems often focus on ontological relationships. Four relationships exist: parent, child, sibling, and friend. First, note that the first three are essentially the same since when a parent is defined, child and sibling relationships are logically specified. So we really only have two categories, which could just as easily be called “directly related” and “indirectly related”. Also, notice that in file-based hierarchical, ontological data structures a note (usually) has, rather unnaturally, only one parent.

Obsidian offers core functionality that allows me to ignore files and focus on information. I’m referring to Search, Bookmarks and Unique Notes. The latter is effectively invisible in articles and videos, and the other two rarely come up. This is especially surprising with regard to Search because that’s the most efficient and powerful way to find information in your vault. Most presenters use Quick Switcher or the Navigator to create and access files in order to create or access information. This is an extra step, wasting time and energy and impeding the flow of thought.
	
SQL databases rely on hierarchy. NoSQL databases don’t. By thinking in hierarchical, ontological terms, we tie ourselves to a table-based way of thinking. By thinking instead about direct and indirect relationships, a note can have multiple “parents” because it can naturally relate directly to more than one topic. (We all have at least two parents in life, and often have other people who fill the role as well.) These articles, for example, have two main topics, two direct relationships: Obsidian and Personal Knowledge Management. I don’t have to choose one or the other. I might decide to write about information processing, in which case these articles could be given another “parent”, the new topic.

### Interacting with NoSQL Databases

The word graph is commonly used to refer to many different types of charts, such as bar charts or line graphs. It has a more specific meaning, however, which is the specific type of graph produced by Graph View. This is the normal way that these data structures are visualized, which is why Graph View is the ideal way to visually explore our vault. This is also the way neural networks are visualized.

Getting information from NoSQL databases is done through queries, not by opening documents. Filters in Obsidian Search have all the capabilities of Dataview queries, with a somewhat simpler syntax.

### Final words

I hope I have explained what it means to say that Obsidian is a NoSQL and the implications of that. Everything we write, every word, becomes part of a database, and we can use the power of databases to retrieve information. Stop using Obsidian as a file manager!


