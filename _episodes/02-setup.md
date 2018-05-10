---
title: "Setting git up"
teaching: 15
exercises: 0
questions:
- "How do I set `git` up?"
objectives:
- "Configure `git` for the first time on your machine"
keypoints:
- "You cannot use `git` without telling it your name and email address"
---

### Using Git

One of the main barriers to getting started with git is the language. Although some of the language used in git is 
fairly self-explanatory, other terms are not so clear. The best way to get to learn the language - which consists of a 
number of verbs such as `add`, `commit` and `push` (precdeded by the word 'git') - is by using it, which is what we will be doing during this 
lesson. These commands will be explained as we proceed from setting up a new version-controlled project to publishing 
our own website.

We will try to do this session as a group, but those who prefer to go at a slower pace can follow the instructions on 
the [GitHub page](https://github.com/data-lessons/library-git).

### Set Git Up

The first thing you have to do after installing git on your computer for the first time is to tell git who you are! You **cannot** make a commit without giving git your name and email address. Ideally, this is the same email address as your GitHub account. 

~~~
$ git config --global user.name "FirstName LastName"
$ git config --global user.email "librarian@library.com"
~~~
{: .bash}

You also probably want to tell git which text editor you like. When using git, you need to use a **plain text editor** such as TextEdit (Mac), Notepad (Windows), or nano (Linux). If you use another editor, feel free to use that as well, as long as it's not something like Microsoft Word, LibreOffice Writer, or the like. Other examples of plain text editors include Sublime Text, notepad++, Vim, or gedit.

To tell git which editor we want to use (and that we want the colors in the terminal to be meaningful!), we type the following commands:

~~~
$ git config --global text.editor "EditorName"
$ git config --global color.ui "auto"
~~~
{: .bash}

Did you notice all these commands have `--global`? This is because we want these settings to apply to *all* our git projects, not just the one we are working on now. This will save you a lot of time in the future!

### Git Help and Manual

Always remember that if you forget a `git` command, you can access the list of commands by using `-h` and access the Git manual by using `--help` :>

~~~
$ git config -h
$ git config --help
~~~
{: .bash}
{: .callout}

