---
title: "What is git?"
teaching: 10
exercises: 0
questions:
- "What is Git?"
- "What is Github?"
objectives:
- "to understand what Git and Github are?"
keypoints:
- "Git and Github are not the same"
---
### What is Git?

Git is a 'free and open source distributed version control system'. We probably know what free and open source means but we might be less sure about what a 'distributed version control system is'. One way to understand what Git and version control systems do is to look at the types of problems they are built to address. 

[PhD comics](http://www.phdcomics.com/comics/archive/phd101212s.gif)

Many of us will have had an experience similar to this. We are working on an important piece of work and we attempt to maintain multiple versions of this document, all at different stages of completeness. 

Version control addresses this problem by recording the changes made to a file as we proceed. Each 'commit' we make is recorded and we can go back across a file or set of files and look at what changes have been made. 

Version control allow us to take this one step further. It not only records changes to a file one person is working on but allows multiple people to work on a file and record the changes *they* make. It is then possible to merge these multiple files into one. 

This method came about to help software developers work collaboratively on coding projects. With version control, groups did not have to wait for someone else to finish working, nor did they have compare changes manually (and laboriously). 

When we make 'commits', we record a range of metadata about that change. As librarians, we might already be inclined to think creating metadata is useful but an example of what information is recorded will illustrate why the information recorded by version control systems in particular is useful. 'Commits' record the time and date a commit was made. Although we can often see information about when we last edited or saved say, a Word document, this only shows us the most recent changes. When we make commits, we can record a message explaining what changes we have made. This makes it especially useful for collaborating. Rather than sending an email with a document with track changes and some comments, we can include all that information with the document itself. This makes it easy to get an overview of changes that have been made to a document by looking at a log of all the changes that have been made. 

### Git vs. GitHub

We often hear the terms Git and GitHub used interchangeably but they are slightly different things. Git refers to the software and principles used for a particular flavour of version control system, also called VCS in short (there are other systems such as Mercurial and SVN). GitHub is a popular site which hosts Git repositories. The majority of the content that GitHub hosts is open source software, though increasingly it is being used for other projects such as open access journals and constantly updated text books. GitHub is a great place to learn how to use Git but once you have learned the ideas and processes behind GitHub you can use Git on other storage systems. You can even host repositories on your own server if you want to keep your files private or if you wanted to encrypt your repository. You can get private repositories on GitHub for a fee. Gitlab is an open source Git repository management and hosting software. You can host it on your own server and configure with unlimited private repositories.
