---
layout: page
title: Setup
permalink: /setup/
root: ../
---

If you haven't done so already, to follow this lesson you will need to:

1. Create a free [GitHub account](https://github.com/join) and confirm your email.
2. Download and install Git for your operating system: [https://git-scm.com/downloads](https://git-scm.com/downloads) (*Note:* Git for Windows comes bundled with the Git Bash terminal that allows you to use the UNIX-style commands featured in this lesson.)
3. Configure Git with your user name and email.

### 1. Create a GitHub Account

[GitHub](https://github.com/) is a Git repository hosting service, a place to store and sync your work in the cloud. 
Take a minute to create a [free account](https://github.com/join).
You will need to confirm your email for your account to become fully activated.
GitHub provides some introductory [tutorials](https://guides.github.com/) if you would like orientation to the platform.

### 2. Install Git

Git version control system is a piece of software you install on your computer.

- **Windows:** install [Git for Windows](https://gitforwindows.org/) using the default options, except when setup asks you to choose the default editor used by Git, select "Use the Nano editor by default". This will give you Git, Git Bash, and Git GUI. Git Bash is a great terminal that lets you use UNIX style commands and utilities on Windows.
- **Mac:** check if Git is already installed by opening terminal and typing `git --version`. If you do not have it, download the official [Mac installer](https://git-scm.com/downloads).
- **Linux:** install from your distribution's software center or package manager (for Ubuntu `sudo apt install git`).

### 3. Configure Git locally

Some initial setup is necessary the first time you use Git on a computer.
You will use these commands only once, unless you want to change something.

Set your user name and email (matching your GitHub account) using the `git config` command:

~~~
$ git config --global user.name "Your Name"
$ git config --global user.email "your@email"
~~~
{: .bash}

This user name and email will be recorded with each commit in the history on any repository you contribute to locally and on GitHub.
Most people keep their email public, however if you are concerned about privacy, check GitHub's tips to [mask your email](https://help.github.com/articles/about-commit-email-addresses/).

By default, Git will open the Vi / Vim text editor to request commit messages (for example when merging conflicts).
To avoid confusion, most people will want to change the default editor to something more familiar using the `core.editor` config.
Any text editor can be made default by adding the correct file path and command line options (see [GitHub help](https://help.github.com/articles/associating-text-editors-with-git/)). 
However, we suggest using Nano (a basic terminal based text editor) on all systems, by setting the `core.editor` value to `"nano -w"`:

~~~
$ git config --global core.editor "nano -w"
~~~
{: .bash}

*Note: Windows users should have set Nano as the default editor during the Git for Windows install and do not need to complete this step.*
