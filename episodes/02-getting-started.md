---
title: "Getting started"
teaching: 20
exercises: 0
questions:
- "What do `add` and `commit` mean?"
objectives:
- "initiate a git repository on the command line"
- "configure git locally"
- "track and commit files to a git repository"
keypoints:
- "`git init` can initialize a directory on your computer as a Git repository"
- "Your Git configuration on your computer is important to attributing your work to you"
- "Git uses a two-stage commit process. Changes must be added to the staging area and then committed from there"
---
### Using Git
One of the main barriers to getting started with Git is the language. Although some of the language used in Git is fairly self-explanatory, other terms are not so clear. The best way to get to learn Git language - which consists of a number of verbs, or commands, e.g. add, commit, precended by the word Git - is by using it but having an overview of the language and the way Git is used will provide a good starting point.

<!demonstrate Git commands whilst outlining what they mean>

### Exercise for our first git repository

We will try to do this session as a group, but those who prefer to go at a slower pace can follow the instructions on the [github page](https://github.com/data-lessons/library-git).

### Some Git commands/language - what they mean and how to use them

**Repository** A repository is the place where projects and associated changes are stored. Repositories can contain one single readme file or hundreds of different folders making up the source code for extensive projects. We can create repositories in a number of different ways; we can make our own from scratch, we can fork (copy) an existing repository or we can create a Git repository from an existing folder we have been working on.

**init** Create a repository

Whenever we use Git on the command line, we need to preface our command with `git`. This is so the computer knows we are trying to get Git to do something rather than another program.

To try out some of the Git commands, we can make a repository for today's session. We can either delete this directory later or keep it as a place to test out new Git commands.

We covered the command line last week but we will go over them again. <!explain commands as we go along>

~~~
$ mkdir git_test
$ cd git_test
$ git init
~~~
{: .bash}

This initiates `git_test` as a git repository.

If you do an `ls` now, the repository might seem empty. However, an `ls -a` will show the hidden files, which includes the new file `.git`.

This signifies that the directory is now a Git repository. Were the `.git` file ever to be deleted after you have begun committing files, all versioning of the data would be lost.

### Tracking files in Git

Git is able to track changes to files and new files that get added into a Git repository. To track files in Git we need to `add` them and then `commit` them. This is a two-stage process, `add` places the file in the staging area, or "On the stage", `commit` cleans off the stage and adds the changes to the reposiotory. This is a two-stage process in order to give you control over what should and should not be included in a particular commit.

We can use `git status` at any time to let us know what Git is up to.

If we try it now, we should get something like this

~~~
On branch master
Initial commit
nothing to commit (create/copy files and use "git add" to track)
~~~
{: .output}

This is telling us that we are on the master branch (more on this later) and that we have nothing to commit (nothing to save changes from).
If we use `ls` we can see currently we don't have any files to track. Let's change that by adding a txt file. `touch` is a command which allows us to quickly create an empty file.

~~~
$ ls
$ touch git_test.txt
~~~
{: .bash}

We now have an empty file. If we try `git status` again, we will get the following

~~~
$ git status
~~~
{: .bash}
~~~
On branch master
Initial commit
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    git_test.txt

nothing added to commit but untracked files present (use "git add" to track)
~~~
{: .output}

This status is Git telling us that it has noticed a new file in our directory that we are not yet tracking. With colourised output, the filename will appear in red.

To change this, and to tell Git we want to track any changes we make to git_test.txt, we use `git add`

~~~
$ git add git_test.txt
~~~
{: .bash}

This adds our txt file to the **staging area** (the area where Git checks for file changes). Because we are not alerted that this has happened, we might want to use `git status` again.

~~~
$ git status
~~~
{: .bash}
~~~
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

    new file:   git_test.txt
~~~
{: .output}

If we opted for colourised output, we can see that the file has changed colour (from red to green) and Git also tells us that it has got a new file.

Let's make some changes to this file before we commit it:

~~~
$ nano git_test.txt
~~~
{: .bash}

Open the file in nano or another text editor.

We should now be able to add some text to our text file. For now let's just write 'hello world'. If we try `git status` again. We should get the following message

~~~
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   git_test.txt
~~~
{: .output}

This lets us know that Git has spotted changes to our txt file but that it hasn't yet 'staged' them. This means Git won't currently record the changes we made. We can add the file to the staging area again

~~~
$ git add git_test.txt
~~~
{: .bash}

We can now **commit** our first changes. Commit is similar to 'saving' a file to Git. However compared to saving, a lot more information about the changes we made is recorded and visible to us later.

~~~
$ git commit -m 'hello world'
~~~
{: .bash}
~~~
[master (root-commit) 27c3f19] hello world
 1 file changed, 1 insertion(+)
 create mode 100644 git_test.txt
~~~
{: .output}

We can see that one file changed and we made one insertion which was a line with the text 'hello world'. We have now recorded our changes and we can later go back and see when we made changes to our file and decided to add 'hello world'. We do have a problem now though. At the moment our changes are only recorded localy on our computer. At the moment, if we wanted to work with someone else, they would have no way of seeing what we've done. Let's fix that. Let's jump to the GitHub website where we could decide to host some of our work. Hosting here will allow us to share our work with our friends and colleagues but will also allow other people to use or build on our work.
