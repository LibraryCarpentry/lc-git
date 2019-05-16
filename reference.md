---
layout: reference
root: .
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

Git cheat sheet handouts:

* https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf 
* https://www.git-tower.com/blog/git-cheat-sheet/

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

## Useful library github repositories

* [DavidChouinard/mrc_to_csv](https://github.com/DavidChouinard/mrc_to_csv): 'Python script for converting MARC21 files to a saner format (CSV), originally designed for the Harvard Libraries MARC21 records'
* [Process MARC records from Python](https://github.com/edsu/pymarc)
  * https://pypi.org/project/pymarc/
* [umd-mith/git-intro](https://umd-mith.github.io/git-intro/): high level intro to git 
* [edsu/mirador](https://github.com/edsu/mirador)
* [edsu/microdata](https://github.com/edsu/microdata)
* [dhtaxonomy/TaDiRAH](https://github.com/dhtaxonomy/TaDiRAH)
* [OpenAPC/openapc-de](https://github.com/OpenAPC/openapc-de)
* [JiscMonitor/allapc](https://github.com/JiscMonitor/allapc)
* [Python Programming for Humanities](http://www.karsdorp.io/python-course/)
* [Code4Lib 2008 lightning talk – Git and distributed cataloging](https://galencharlton.com/blog/2008/03/code4lib-2008-lightning-talk-git-and-distributed-cataloging/)
* [Open Science Guide](http://book.openingscience.org.s3-website-eu-west-1.amazonaws.com/)

## Further reading

* The [help pages](https://help.github.com/) of github are a good place to start
* Github has '[activities](https://guides.github.com/activities/hello-world/)' which aim to explain how git works
* GitHub also has a [Learning Labs](https://lab.github.com/) and an interactive tutorial via their [Desktop](https://desktop.github.com/) app
* Atlassian has in depth but clear [tutorials](https://www.atlassian.com/git/tutorials) on using git
* The [Programming Historian](https://programminghistorian.org ) uses GitHub to manage lessons useful to historians and also people working in libraries. It is a useful resource for lessons but also to see GitHub in action.
