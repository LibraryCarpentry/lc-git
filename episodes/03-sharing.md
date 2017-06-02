---
title: "Sharing your work"
teaching: 30
exercises: 0
questions:
- "What does `push` and `pull` mean?"
objectives:
- "create a repository on GitHub"
- "link a local repository with a repository on GitHub"
- "push changes from the local repository to GitHub"
- "pull changes back from GitHub to the local repository"
keypoints:
- "remote repositories on GitHub help you collaborate"
- "`push` is a Git verb for sending changes from the local repository to a remote repository"
- "`pull` is a Git verb for bringing changes from a remote repository to the local repository"
---

## Create a GitHub Account

Go to https://github.com and create an account. GitHub.com is a company that makes Git easy to use on the web.
GitHub is a company trying to make a profit, but they are committed to supporting open source. There are specific
[terms of serivce](https://help.github.com/articles/github-terms-of-service/) which you should carefully review
before you share your major creative works via GitHub. Their policies and procedures are, today, generally open and
reasonable, which is why so many organizations use GitHub. They allow free hosting of Open Source projects if you agree
to make the content available to the world. If you would like to keep some of your code or creative works private, GitHub
has a fee-for-service subscription model you can look into.

## Create a reposiotry

When we have logged in to GitHub, we will see an option to create a new repository. Let's make one for the GitHub experiments we are going to do today.

* new repository
* give it a name

GitHub will ask you to create README.md, add a license and a `.gitignore` file. Do not do any of that for now.
Once we have created the new repository, we still need to link the repository we have on our computer with the one we've just set up on GitHub.

Choosing a license is an important part of openly sharing your creative work online. For help in wading through the
many types of open source licenses, please visit https://choosealicense.com/.

## Connecting your local repository to a remote repository

~~~
$ git remote add origin <web address of your repo.git>
~~~
{: .bash}

> ## Why `origin`?
> `origin` in the `git remote add` line is just a short name or alias we're giving to that big long repository URL.
> It could be almost any string we want, but by convention in Git, it is usually called `origin`, representing where
> the repo originated.
{: .callout}

This will add a repository on GitHub for our changes to be committed to.

Check that it is set up correctly with the command:

~~~
$ git remote -v
~~~
{: .bash}

## "Pushing" changes

Then enter:

~~~
$ git push -u origin master
~~~
{: .bash}

**git push** will add the changes made in our local repository to the repository on GitHub. The nickname of our remote is origin and the default local branch name is master. The `-u` flag tells Git to remember the parameters, so that next time we can simply run `git push` and Git will know what to do. Go ahead and push it!

You will be prompted to enter your GitHub username and password to complete the command.

When we do a `git push`, we will see Git 'pushing' changes upstream to GitHub. Because our file is very small, this won't take long but if we had made a lot of changes or were adding a very large repository, we might have to wait a little longer.
We can get to see where we're at with `git status`.

~~~
On branch master
Your branch is up-to-date with 'origin/master'.

nothing to commit, working directory clean
~~~
{: .output}

This is letting us know where we are working (the master branch). We can also see that we have no changes to commit and everything is in order.

We can use `git diff` to see changes we have made before making a commit.
Let's add another line to our text file.

~~~
$ open git_test.txt
$ git diff
~~~
{: .bash}
~~~
diff --git a/git_test.txt b/git_test.txt
index 70c379b..1d55e1a 100644
--- a/git_test.txt
+++ b/git_test.txt
@@ -1 +1,2 @@
-Hello world
\ No newline at end of file
+Hello world
+More changes to my first github file
\ No newline at end of file
~~~
{: .output}

We can see the changes we have made.

1. The first line tells us that Git is producing output similar to the Unix diff command comparing the old and new versions of the file.
2. The second line tells exactly which versions of the file Git is comparing; `df0654a` and `315bf3a` are unique computer-generated identifiers for those versions.
3. The third and fourth lines once again show the name of the file being changed.
4. The remaining lines are the most interesting; they show us the actual differences and the lines on which they occur. In particular, the + markers in the first column show where we have added lines.

We can now commit these changes again:

~~~
$ git add git_test.txt
$ git commit -m 'second line of changes'
~~~
{: .bash}

Say we are very forgetful and have already forgotten what we changes we have made. `git log` allows us to look at what we have been doing to our Git repository (in reverse chronological order, with the very latest changes first).

~~~
$ git status
~~~
{: .bash}
~~~
commit 40d3f7af25e19c06fa839a570d51e38fdb374e80
Author: davanstrien <email@gmail.com>
Date:   Sun Oct 18 15:25:19 2015 +0100

    second line of changes

commit 27c3f19c3340d930234d592928b11b63403d0696
Author: davanstrien <email@gmail.com>
Date:   Sun Oct 18 13:27:31 2015 +0100

    hello world
~~~
{: .output}

This shows us the two commits we have made and shows the messages we wrote. It is important to try to use meaningful commit messages when we make changes. This is especially important when we are working with other people who might not be able to guess as easily what our short cryptic messages might mean.

We might get a lit bit lonely working away on our own and want to work with other people. Before we get to that, it is worth learning one more command.

## "Pulling" changes

We can try to see how this works by making changes on the GitHub website and then 'pulling' them back to our computer.

Let's go to our repository. We can see our txt file and make changes. However, you may have noticed only our first change is there. This is because we didn't push our last commit yet. This might seem like a mistake in design but it is often useful to make a lot of commits for small changes so you are able to make careful revisions later and you don't necessarily want to push all these changes one by one.

## Pushing and Pulling

Let's go back and push our changes

~~~
$ git push
~~~
{: .bash}

Now if we go back to our GitHub repo, we can see all our changes. Let's add an extra line of text there, and commit these changes. When we commit changes on GitHub itself, we don't have to push these.

Now let's get the third line on to our computer.

~~~
$ git pull
~~~
{: .bash}
~~~
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/davanstrien/git_lesson_example
   40d3f7a..ef95e51  master     -> origin/master
Updating 40d3f7a..ef95e51
Fast-forward
 git_test.txt | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
~~~
{: .output}

If we open our text file again

~~~
$ open git_test.txt
~~~
{: .bash}

we can see our new lines.

When we begin collaborating on more complex projects, we may have to consider more aspects of Git functionality, but this should be a good start. In the second hour we can look more closely at collaborating and using GitHub pages.
