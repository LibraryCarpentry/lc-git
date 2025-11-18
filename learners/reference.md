---
title: 'Reference'
---

## Quick reference

### Navigating the shell

`pwd`
: print working directory

`ls`
: list directory
:
: - `-l`: list file information
: - `-lh`: list human readable file information

`cd`
: change directory

### Interacting with files in the shell

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

### Git commands

Git cheat sheet handouts:

- [GitHub git cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)
- [Tower client git cheat sheet](https://www.git-tower.com/blog/git-cheat-sheet/)

`git init`
: create a new local git repository

`git status`
: view the status of your files in the working directory and staging area

`git add`
: tell git to start tracking a file, or a series of files

`git commit`
: save file changes from the staging area permanently to the project history

`git push`
: upload all commits to a remote repository, such as GitHub

`git log`
: show history of commits in reverse chronological order

`git diff`
: show changes made to tracked files

`git pull`
: download upstream changes and merge them into your local repository

`git remote add origin`
: add a remote repository named 'origin', to upload changes to or download changes from

## Useful library-related Git repositories

- [DavidChouinard/mrc\_to\_csv](https://github.com/DavidChouinard/mrc_to_csv): Python script for converting MARC21 files to CSV, originally designed for the Harvard Libraries MARC21 records.
- [pymarc/pymarc](https://gitlab.com/pymarc/pymarc): Python package for reading, modifying, and writing records in MARC21 format.
  - Package description: [Pymarc](https://pypi.org/project/pymarc/)
- [umd-mith/git-intro](https://umd-mith.github.io/git-intro/): Slides introducing Git, aimed at Digital Humanities students, hosted on GitHub pages.
  - Rendered slides: [High level intro to Git](https://umd-mith.github.io/git-intro/)
- [ProjectMirador/mirador](https://github.com/ProjectMirador/mirador): NodeJS package providing an interactive image viewer for cultural heritage websites.
  - Package website: [Mirador](https://projectmirador.org/)
- [edsu/microdata](https://github.com/edsu/microdata): Python package for extracting microdata (text given a machine-readable label) from HTML5.
- [dhtaxonomy/TaDiRAH](https://github.com/dhtaxonomy/TaDiRAH): Taxonomy of Digital Research Activities in the Humanities.
  - As rendered by the Dariah Vocabs Service: [TaDiRAH](https://vocabs.dariah.eu/tadirah/en/)
- [OpenAPC/openapc-de](https://github.com/OpenAPC/openapc-de): Dataset of information on fee-based open access publishing.
  - Viewer for the dataset: [OpenAPC](https://treemaps.openapc.net)
- [JiscMonitor/allapc](https://github.com/JiscMonitor/allapc): Python package providing an API and reporting system for aggregated APC (article publication charge) data.
- [fbkarsdorp/python-course](https://github.com/fbkarsdorp/python-course): Tutorial and introduction to programming with Python, aimed at students/researchers in the humanities and social sciences, maintained as a set of Jupyter Notebooks.
  - Rendered version: [Python Programming for the Humanities](https://www.karsdorp.io/python-course/)
- [openingscience/book](https://github.com/openingscience/book): The evolving guide on how the Web is changing research, collaboration and scholarly publishing, maintained as Markdown files and rendered using Jekyll (also used by GitHub Pages).
  - Rendered book: [Opening Science](https://www.openingscience.org/get-the-book/)
- [programminghistorian/jekyll](https://github.com/programminghistorian/jekyll): A collection of lessons useful to historians and people working in libraries, maintained as Markdown files and hosted by GitHub Pages.
  - Rendered site: [Programming Historian](https://programminghistorian.org)

## Further reading

- The [help pages](https://help.github.com/) of GitHub are a good place to start.
- GitHub has '[activities](https://guides.github.com/activities/hello-world/)' which aim to explain how git works.
- GitHub also has interactive tutorials for their [online version (GitHub Skills)](https://skills.github.com/) and for [using Git offline (Git-It)](https://github.com/jlord/git-it-electron#git-it-desktop-app).
- Atlassian has in-depth but clear [tutorials](https://www.atlassian.com/git/tutorials) on using git.
- [Code4Lib 2008 lightning talk – Git and distributed cataloging](https://galencharlton.com/blog/2008/03/code4lib-2008-lightning-talk-git-and-distributed-cataloging/): Slides by Galen Charlton drawing parallels between how git works and how cataloging should work.
