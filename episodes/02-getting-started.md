---
title: "Getting started with git"
teaching: 20
exercises: 0
questions:
- "What are repositories and how are they created?"
- "What do `add` and `commit` mean?"
- "How do I check the status of my repository?"
objectives:
- "create a git repository"
- "track changes to files using the git repository"
- "query the current status of the git repository"
keypoints:
- "Git repositories contain metadata about files under version control"
- "This metadata enables us to track changes to files over time"
- "Git uses a two-stage commit process. Changes to files must first be added to the staging area, then committed to the repository"
---

### Using Git

One of the main barriers to getting started with git is the language. Although some of the language used in git is 
fairly self-explanatory, other terms are not so clear. The best way to get to learn the language - which consists of a 
number of verbs such as `add`, `commit` and `push` (preceded by the word 'git') - is by using it, which is what we will be doing during this 
lesson. These commands will be explained as we proceed from setting up a new version-controlled project to publishing 
our own website.


### Creating a repository

A Git **repository** is a data structure used to track changes to a set of project files over time. Repositories are 
stored within the same directory as these project files, in a hidden directory called `.git`. We can create a new git 
repository either by using [GitHub's web interface](https://github.com/new), or via the command line. Let's use the command line to create a git 
repository for the experiments that we're going to do today.

First, we will create a new directory for our project and enter that directory.
<!explain commands as we go along>

~~~
$ mkdir hello-world
$ cd hello-world
~~~
{: .bash}

We will now create an empty git repository to track changes to our project. To do this we will use the git **init** command, 
which is simply short for *initialise*.

~~~
$ git init
~~~
{: .bash}

The `hello-world` directory is now a git repository. 

If we run the `ls` command now (`ls` lists the content of the `hello-world` 
directory), the repository might seem empty; however, adding the `-a` flag 
for all files via `ls -a` will show all hidden files, which in this case 
includes the new hidden directory `.git`.

Note that whenever we use git via the command line, we need to preface each command (or verb) with `git`, so that the computer knows 
we are trying to get git to do something, rather than some other program.

### Displaying the current project's status

We can run the `git status` command to display the current state of a project. Let's do that now.

~~~
$ git status
~~~
{: .bash}
~~~
On branch master
Initial commit
nothing to commit (create/copy files and use "git add" to track)
~~~
{: .output}

The output tells us that we are on the master branch (more on this later) and that we have nothing to commit (no 
unsaved changes).


### Adding and committing

We will now create and save our first project file. This is a two-stage process. First, we **add** any files for which 
we want to save the changes to a staging area, then we **commit** those changes to the repository. This two-stage 
process gives us fine-grained control over what should and should not be included in a particular commit.

Let's create a new file using the `touch` command, which is a quick way to create an empty file.

~~~
$ touch index.md
~~~
{: .bash}

The `.md` extension above signifies that we have chosen to use the Markdown format, a lightweight markup language with plain text formatting syntax. We will explore Markdown a bit later.

Let's check the status of our project again.

~~~
$ git status
~~~
{: .bash}
~~~
On branch master
Initial commit
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    index.md

nothing added to commit but untracked files present (use "git add" to track)
~~~
{: .output}

This status is telling us that git has noticed a new file in our directory that we are not yet tracking. With colourised 
output, the filename will appear in red. To change this, and to tell Git we want to track any changes we make to 
index.md, we use `git add`.

~~~
$ git add index.md
~~~
{: .bash}

This adds our Markdown file to the **staging area** (the area where git checks for file changes). To confirm this we want to use `git status` again.

~~~
$ git status
~~~
{: .bash}
~~~
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

    new file:   index.md
~~~
{: .output}

If we are using colourised output, we will see that the filename has changed colour (from red to green). Git also tells us that there
is a new file to be committed but, before we do that, let's add some text to the file.

We will open the file `index.md` with any text editor we have at hand (e.g. Notepad on Windows or TextEdit on Mac OSX) and enter `# Hello, world!`. The
hash character is one way of writing a header with Markdown. Now, let's save the file within the text editor and check if Git
has spotted the changes.

~~~
$ git status
~~~
{: .bash}
~~~
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   index.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   index.md
~~~
{: .output}

This lets us know that git has indeed spotted the changes to our file, but that it hasn't yet staged them, so let's add 
the new version of the file to the staging area.

~~~
$ git add index.md
~~~
{: .bash}

Now we are ready to  **commit** our first changes. 
Commit is similar to 'saving' a file to Git. 
However, compared to saving, a commit provides a lot more information about the changes we have made,
and this information will remain visible to us later.


~~~
$ git commit -m 'Add index.md'
~~~
{: .bash}
~~~
[master (root-commit) e9e8fd3] Add index.md
 1 file changed, 1 insertion(+)
 create mode 100644 index.md
~~~
{: .output}

We can see that one file has changed and that we made one insertion, which was a line with the text '#Hello, world!'. 
We can
also see the commit message 'Add index.md', which we added by using the `-m` flag after `git commit`.
The commit message is used to record a short, descriptive, and specific summary of what we did to help us remember later on without having to look at the actual changes.
If we just run `git commit` without the `-m` option, Git will launch nano (or whatever other editor we configured as `core.editor`)
so that we can write a longer message.

Having made a commit, we now have a permanent record of what was changed,
along with metadata about who made the commit and at what time.

> ## More on the Staging Area
>
> If you think of Git as taking snapshots of changes over the life of a project,
> `git add` specifies *what* will go in a snapshot
> (putting things in the staging area),
> and `git commit` then *actually takes* the snapshot, and
> makes a permanent record of it (as a commit).
> If you don't have anything staged when you type `git commit`,
> Git will prompt you to use `git commit -a` or `git commit --all`,
> which is kind of like gathering *everyone* for the picture!
> However, it's almost always better to
> explicitly add things to the staging area, because you might
> commit changes you forgot you made. (Going back to snapshots,
> you might get the extra with incomplete makeup walking on
> the stage for the snapshot because you used `-a`!)
> Try to stage things manually,
> or you might find yourself searching for "git undo commit" more
> than you would like!
{: .callout}

![The Git Staging Area](../fig/git-staging-area.svg)

At the moment, our changes are only recorded locally, on our computer. If we wanted to 
work collaboratively with someone else they would have no way of seeing what we've done.
We will fix that in the next episode by using GitHub to share our work.
