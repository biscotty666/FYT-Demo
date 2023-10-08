---
fileClass: [article]
---
%%
up:: [[Linux]]
tags:: #moc 
action:: false
status:: 80
topic:: [[Linux]], [[NixOS]]
related:: 
created:: 2023-08-28 Mon
last edit:: 2023-09-12 Tue
title:: Declarative, Imperative NixOS
Published to:: 
link:: 
Author:: [[Brian Carey]]
Stage:: alpha review
PubDate:: 
Published:: false
Cover:: 
aliases:: 
type:: article
%%
# Declarative, Immutable NixOS

Most people have only ever used imperative, mutable operating systems. **NixOS**, on the other hand, is an *immutable*, *declarative* Linux system. In this article I will explain why this is a Good Thing for developers and system administrators.

- stability
- reproducibility
- flexibility

## Mutable and Immutable OSs

### Mutable OSs
They are mutable because the  installer will modify, with root permissions, the system directories. This also might entail setting up new services (imperatively) and or altering existing services, maybe imperatively or maybe by altering files somewhere in the system tree.

### Immutable OSs

## Containers

## Imperative and Declarative OSs
Reproducibility


Most operating systems are *imperative*, which means they are constructed by installing software using commands. The commands copy files to system directories, create or alter the contents of configuration files, stop and start services, ensure that correct dependencies are installed, etc.

And we also have to consider the uninstall process. While developers obviously spend a lot of time making sure that they're software installs properly, they are much less concerned with how well it uninstalls. Often the uninstall process will leave remnants of the program scattered around in system directories. These can come back to bite you and later on. One would hope that an uninstall would leave the system as it was before the install but this is unfortunately not always the case.

What are some of the drawbacks to this approach? 
- takes a long time 
- library version conflicts 
- cruft accumulates over time 
- stability, system or parts can break
- requires knowledge of the location of config files 



## What's wrong with that?
### Imperative design
Reproducibility
Ease and speed of administration
Consistency 
### Mutability 
Library conflicts
Knowing location of config files
Altering files can break the system 
## Immutability 


## Containers

It is becoming more common now for programmers to package their applications using container programs such as docker or podman. This is an attempt to address the problems of mutability and declaratively creating development and runtime environments. A container creates an isolated environment for the program to run which does not depend on system libraries and therefore does not need to alter them. Containers can be composed declaratively so precise systems or precise environments can be built. This approach also solves versioning problems.

Nixos is a logical extension of this, applying the concept to the entire file system to the entire OS itself. NixOS uses Ni

Nixos is probably not the best choice for a casual user, although it might be. It should be very interesting to system administrators and developers however.

Listen tax of Nick SOS configuration files may seem intimidating, although anyone with a background in JavaScript should feel right at home. With its curly braces and json like syntax it's pretty straightforward, with a few differences, like using python-esque in function definitions and space delimited lists, but it's pretty straightforward.

Nick's Oasis configuration files are actually build scripts. 
