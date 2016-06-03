---
layout: reference
title: Reference
permalink: /reference/
---

## Quick reference

### Basics - navigating the shell

`pwd`
: print working directory

`ls`
: list directory
:
: - `-l`: list file information
: - `-lh`: list human readable file information

`cd`
: change directory

### Basics - interacting with files

`mkdir`
: make directory

`cat`
: send file or files to output (in most cases, print to shell)

`head`
: output first parts of a file or files

`tail`
: output last parts of a file or files

`mv`
: rename or move a file or files. Syntax for renaming a file: `mv FILENAME NEWFILENAME`

`cp`
: copy a file or files. Syntax: `cp FILENAME NEWFILENAME`

`>`
: redirect output. Syntax with `cat`: `cat FILENAME1 FILENAME2 > NEWFILENAME`

`rm`
: remove a file or files. NB: *USE WITH CAUTION!!!*

### Basic Git commands 

`git init`
: creates a git repository

`git status`
: view the status of your files in the working directory and staging area

`git add`
: tells git to start tracking a file, or a series of files. 

`git commit`
: commits 'saves' the staged snapshot to the project history. 

`git push`
: commits the staged snapshot to the project history.

`git log`
: history of commits in reverse chronological order.

`git diff`
: shows changes made to files

`git pull`
: Merges upstream changes into your local repository 

`git remote add origin`
: add a repository where changes will be stored -
