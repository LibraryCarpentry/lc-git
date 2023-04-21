---
title: Getting started with Git
teaching: 25
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- create a Git repository
- track changes to files using the Git repository
- query the current status of the Git repository

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- What are repositories and how are they created?
- What do `add` and `commit` mean?
- How do I check the status of my repository?

::::::::::::::::::::::::::::::::::::::::::::::::::

### Setting up Git

When we use Git on a new computer for the first time,
we need to configure a few things. The basic elements of a configuration for Git are:

- your name and email address,
- what your preferred text editor is,
- the name of your default branch (branches are an important component of Git that we will cover later).

To start we will check in on our current Git configuration. Open your shell terminal window and type:

```bash
$ git config --list
```

On MacOS, without any configuration your output might look like this:

```output
credential.helper=osxkeychain
```

On Windows, without any configuration your output might look like this:

```output
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=main
```

If you have different output, then you may have your Git configured already. If you have not configured Git, we will do that together now.
First, we will tell Git our user name and email.

Please note: You need to use the same email address in your Git configuration in the shell as you entered into GitHub when you created your GitHub account. Later in the lesson we will be using GitHub and the email addresses need to match. If you are concerned about privacy, please review [GitHub's instructions for keeping your email address private](https://help.github.com/articles/keeping-your-email-address-private/).

Type these two commands into your shell, replacing `Your Name` and the email address with your own:

```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "yourname@domain.name"
```

If you enter the commands correctly, the shell will merely return a command prompt and no messages. To check your work, ask Git what your configuration is using the same command as above:

```bash
git config --list
```

```output
user.name=Your Name
user.email=yourname@domain.name
```

Let's also set our default text editor. A text editor is necessary with some of your Git work, and the default from Git is Vim, which is a text editor that is hard to learn at first. Therefore, we recommend setting a simpler text editor in your Git configuration for this lesson.

:::::::::::::::::::::::::::::::::::::::::  callout

## Text editors

There are a lot of text editors to choose from, and a lot of people are enthusiastic about their preferences.
Vi and Vim are popular editors for users of the BASH shell. If you will be using Git or the Shell with a group of people for a project or for work, asking for recommendations or preferences can help you pick an editor to get started with. If you already have your favorite, then you can set it as your default editor with Git.

::::::::::::::::::::::::::::::::::::::::::::::::::

Any text editor can be made default by adding the correct file path and command line options (see [GitHub help](https://help.github.com/articles/associating-text-editors-with-git/)).
However, the simplest `core.editor` values are `"notepad"` on Windows,  `"nano -w"` on Mac, and `"nano -w"` on Linux.

For example:

```bash 
$ git config --global core.editor "notepad"
```

```bash
$ git config --global core.editor "nano -w"
```

Lastly, we need to set the name of our default branch to `main.`

```bash 
$ git config --global init.defaultBranch main
```

The `init.defaultBranch` value configures git to set the default branch to `main` instead of `master`.

### Creating a repository

A Git **repository** is a data structure used to track changes to a set of project files over time. Repositories are
stored within the same directory as these project files, in a hidden directory called `.git`. We can create a new git
repository either by using [GitHub's web interface](https://github.com/new), or via the command line. Let's use the command line to create a git
repository for the experiments that we're going to do today.

First, we will create a new directory for our project and enter that directory. We will explain commands as we go along.

```bash 
$ mkdir hello-world
$ cd hello-world
```

### Using Git

One of the main barriers to getting started with Git is understanding the terminology necessary to executing commands. Although some of the language used in Git aligns with common-use words in English, other terms are not so clear. The best way to learn Git terminology - which consists of a number of verbs such as add, commit and push (preceded by the word 'git') - is to use it, which is what we will be doing during this lesson. We will explain these commands as we proceed from setting up a new version-controlled project to publishing our own website.

On a command line interface, Git commands are written as `git verb options`,
where `verb` is what we actually want to do and `options` is additional optional information which may be needed for the `verb`. So let's get started with our setup.

We will now create an empty git repository to track changes to our project. To do this we will use the git **init** command,
which is simply short for *initialise*.

```bash 
$ git init
```

```output
Initialized empty Git repository in <your file path>/hello-world/.git/
```

The `hello-world` directory is now a git repository.

If we run the `ls` command now (`ls` lists the content of the `hello-world`
directory), the repository might seem empty; however, adding the `-a` flag
for all files via `ls -a` will show all hidden files, which in this case
includes the new hidden directory `.git`. Flags can simply be thought of as command line options that can be added to shell commands.

Note that whenever we use git via the command line, we need to preface each command (or verb) with `git`, so that the computer knows
we are trying to get git to do something, rather than some other program.

### Displaying the current project's status

We can run the `git status` command to display the current state of a project. Let's do that now.

```bash 
$ git status
```

```output
On branch main
No commits yet
nothing to commit (create/copy files and use "git add" to track)
```

The output tells us that we are on the main branch (more on this later) and that we have nothing to commit (no
unsaved changes).

### Two steps: Adding and committing

We will now create and save our first project file. This is a two-step process. First, we **add** any files for which
we want to save the changes to a staging area, then we **commit** those changes to the repository. This two-stage
process gives us fine-grained control over what should and should not be included in a particular commit.

Let's create a new file using the `touch` command, which is a quick way to create an empty file.

```bash 
$ touch index.md
```

The `.md` extension above signifies that we have chosen to use the Markdown format, a lightweight markup language with plain text formatting syntax. We will explore Markdown a bit later.

Let's check the status of our project again.

```bash 
$ git status
```

```output
On branch main
No commits yet
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    index.md

nothing added to commit but untracked files present (use "git add" to track)
```

This status is telling us that git has noticed a new file in our directory that we are not yet tracking. With colourised
output, the filename will appear in red. To change this, and to tell Git we want to track any changes we make to
index.md, we use `git add`.

```bash 
$ git add index.md
```

This adds our Markdown file to the **staging area** (the area where git checks for file changes). To confirm this we want to use `git status` again.

```bash 
$ git status
```

```output
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

    new file:   index.md
```

If we are using colourised output, we will see that the filename has changed colour (from red to green). Git also tells us that there
is a new file to be committed but, before we do that, let's add some text to the file.

We will open the file `index.md` with any text editor we have at hand (e.g. Notepad on Windows or TextEdit on Mac OSX) and enter `# Hello, world!`. The
hash character is one way of writing a header with Markdown. Now, let's save the file within the text editor and check if Git
has spotted the changes.

```bash 
$ git status
```

```output
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   index.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   index.md
```

This lets us know that git has indeed spotted the changes to our file, but that it hasn't yet staged them, so let's add
the new version of the file to the staging area.

```bash 
$ git add index.md
```

Now we are ready to  **commit** our first changes.
Commit is similar to 'saving' a file to Git.
However, compared to saving, a commit provides a lot more information about the changes we have made,
and this information will remain visible to us later.

```bash 
$ git commit -m 'Add index.md'
```

```output
[main (root-commit) e9e8fd3] Add index.md
 1 file changed, 1 insertion(+)
 create mode 100644 index.md
```

We can see that one file has changed and that we made one insertion, which was a line with the text '#Hello, world!'.
We can
also see the commit message 'Add index.md', which we added by using the `-m` flag after `git commit`.
The commit message is used to record a short, descriptive, and specific summary of what we did to help us remember later on without having to look at the actual changes.
If we just run `git commit` without the `-m` option, Git will launch nano (or whatever other editor we configured as `core.editor`)
so that we can write a longer message.

Having made a commit, we now have a permanent record of what was changed,
and git has also recorded some additional metadata: who made the commit (you!) and when the commit was made (timestamp). You are building a mini-history of your process of working with the files in this directory.

:::::::::::::::::::::::::::::::::::::::::  callout

## More on the Staging Area

If you think of Git as taking snapshots of changes over the life of a project,
`git add` specifies *what* will go in a snapshot
(putting things in the staging area),
and `git commit` then *actually takes* the snapshot, and
makes a permanent record of it (as a commit).
If you don't have anything staged when you type `git commit`,
Git will prompt you to use `git commit -a` or `git commit --all`,
which is kind of like gathering *everyone* for the picture!
However, it's almost always better to
explicitly add things to the staging area, because you might
commit changes you forgot you made. (Going back to snapshots,
you might get the extra with incomplete makeup walking on
the stage for the snapshot because you used `-a`!)
Try to stage things manually,
or you might find yourself searching for "git undo commit" more
than you would like!


::::::::::::::::::::::::::::::::::::::::::::::::::

![](fig/git-staging-area.svg){alt='The Git Staging Area'}

At the moment, our changes are only recorded locally, on our computer. If we wanted to
work collaboratively with someone else they would have no way of seeing what we've done.
We will fix that in the next episode by using GitHub to share our work.

:::::::::::::::::::::::::::::::::::::::: keypoints

- When you initialize a Git repository in a directory, Git starts tracking the changes you make inside that directory.
- This tracking creates a history of the way the files have changed over time.
- Git uses a two-step process to record changes to your files. Changes to files must first be added to the staging area, then committed to the Git repository.

::::::::::::::::::::::::::::::::::::::::::::::::::


