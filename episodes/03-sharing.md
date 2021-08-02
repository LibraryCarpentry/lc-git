---
title: "Sharing your work"
teaching: 30
exercises: 0
questions:
- "How can I use Git and GitHub to share my work?"
- "How do I link a local Git repository to GitHub?"
- "How do I move changes between a local Git repository and a GitHub repository?"
- "How can I see the differences between my current file and my most recent commit?"
objectives:
- "create a remote repository on GitHub"
- "link a local Git repository to a remote GitHub repository"
- "move changes between the local and remote repositories using `push` and `pull`"
- "examine the difference between an edited file and the file's most recently committed version"
keypoints:
- "remote repositories on GitHub help you collaborate and share your work"
- "`push` is a Git verb for sending changes from the local repository to a remote repository"
- "`pull` is a Git verb for bringing changes from a remote repository to the local repository"
- "`diff` is a Git verb for viewing the difference between an edited file and the file's most recent commit"
---

## The power of sharing

The real power of Git lies in being able to share your work with others and in being able to work collaboratively. The best way to do this is to use a remote hosting platform. For this lesson, we are using GitHub. Let's log in there now. 

## Create a repository on GitHub

Once we have logged in to GitHub, we can create a new repository by clicking the **+** icon in the upper-right corner of
any page then selecting **New repository**. Let's do this now.

![The GitHub website top navigation with the 'add new ...' button. ](../fig/github-repo-new.png)

* Click "New Repository"

Clicking `New Repository` will take you to a creation page with different options. For this workshop, we are not using any of the options available. 

* Name your repository "hello-world."

![The 'create a new repository' form on GitHub](../fig/github-repo-new-setup.png) 

* Click `Create Repository` button.

> ## Choosing a license
> When you are ready to use GitHub to host your own work, you should review the different license options. Choosing a license is an important part of openly sharing your creative and research  work online. For help in wading through the
> many types of open source licenses, please visit <https://choosealicense.com/>.
{: .callout}

## Connecting your local repository to the GitHub repository

The next page that GitHub displays is some helper information to allow you to connect your repository on GitHub with your local repository. We want to make GitHub the `remote` repository for our local repository. In order to do that we need the information that GitHub displays in the "Quick setup" box on this page. 

We will use the SSH protocol for this lesson, so please make sure that button shows that it is selected (gray highlight) and that the address in the text box starts with git@github. It will look something like this:

![The repository set up page in GitHub showing the SSH address to use.](../fig/github-repo-connect.png)

> ## HTTPS vs. SSH
>
> We use SSH here because, while it requires some additional configuration, it is a
> security protocol widely used by many applications.  The steps below describe SSH at a
> minimum level for GitHub. 
{: .callout}
<!--- A supplemental episode to this lesson discusses advanced setup, concepts of SSH and key pairs, and other material supplemental to git related SSH.--->
In the previous episode we created a local repository on our own computer.
Now we have also created a remote repository on GitHub.
But at this point, the two are completely isolated from each other.
We want to link them together to synchronize them and share our project with the world.

To connect the repository on our own computer (local) to the repository we just created on GitHub, we will use the commands provided by GitHub in the box with the heading "...or push an existing repository from the command line."

![GitHub instructions](../fig/github-instructions.png)

Let's use these instructions now. Move back to your shell application and enter the first command, which links our local repository
to the GitHub repository:

~~~
$ git remote add origin git@github.com:savvy-librarian/hello-world.git 
~~~
{: .language-bash }

where `savvy-librarian` should be replaced with your own username.

> ## Why `origin`?
> `origin` in the `git remote add` line is just a nickname or alias we're giving to that big long repository URL.
> It could be almost any string we want, but by convention in Git, it is usually called `origin`, representing where
> the repo originated.
{: .callout}

We can check that it is set up correctly with the command:

~~~
$ git remote -v
~~~
{: .language-bash }
~~~
origin  https://github.com/<your_github_username>/hello-world (fetch)
origin  https://github.com/<your_github_username>/hello-world (push)
~~~
{: .output}

## Pushing changes

Now we have established a connection between the two repositories, but we still haven't
synchronized their content, so the remote repository is still empty. To fix that, we
will have to "push" our local changes to the GitHub repository. We do this using the
`git push` command:

~~~
$ git push -u origin main
~~~
{: .language-bash }
~~~
Counting objects: 3, done.
Writing objects: 100% (3/3), 226 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/<your_github_username/hello-world
 * [new branch]      main -> main
Branch main set up to track remote branch main from origin.
~~~
{: .output}

The nickname of our remote repository is "origin" and the default local branch name is "main".
The `-u` flag tells git to remember the parameters, so that next time we can simply run `git push`
and Git will know what to do.

Pushing our local changes to the Github repository is sometimes referred to as "pushing changes `upstream` to Github".
The word `upstream` here comes from the git flag we used earlier in the command `git push -u origin main`.
The flag `-u` refers to `-set-upstream`, so when we say pushing changes upstream, it refers to the remote repository.

You may be prompted to enter your GitHub username and password to complete the command.

When we do a `git push`, we will see Git 'pushing' changes upstream to GitHub. Because our file is very small, this
won't take long but if we had made a lot of changes or were adding a very large repository, we might have to wait a
little longer. We can check where we're at with `git status`.

~~~
$ git status
~~~
{: .language-bash }
~~~
On branch main
Your branch is up-to-date with 'origin/main'.
nothing to commit, working tree clean
~~~
{: .output}

This output lets us know where we are working (the main branch). We can also see that we have no changes to commit
and everything is in order.

We can use the `git diff` command to see changes we have made before making a commit. Open index.md with any text
editor and enter some text on a new line, for instance "A new line" or something else.
We will then use `git diff` to see the changes we made:

~~~
$ git diff
~~~
{: .language-bash }
~~~
diff --git a/index.md b/index.md
index aed0629..989787e 100644
--- a/index.md
+++ b/index.md
@@ -1 +1,2 @@
-# Hello, world!
\ No newline at end of file
+# Hello, world!
+A new line
~~~
{: .output}

The command produces lots of information and it can be a bit overwhelming at first,
but let's go through some key information here:

1. The first line tells us that Git is producing output similar to the Unix `diff` command, comparing the old and new
versions of the file.
2. The second line tells exactly which versions of the file Git is comparing; `aed0629` and `989787e` are unique
computer-generated identifiers for those versions.
3. The third and fourth lines once again show the name of the file being changed.
4. The remaining lines are the most interesting; they show us the actual differences and the lines on which they occur.
In particular, the + markers in the first column show where we have added lines.

We can now commit these changes:

~~~
$ git add index.md
$ git commit -m 'Add another line'
~~~
{: .language-bash }

If we are very forgetful and have already forgotten what we changes we have made, `git log` allows us to look at what
we have been doing with our git repository (in reverse chronological order, with the very latest changes first).


~~~
$ git log
~~~
{: .language-bash }
~~~
commit 8e2eb9920eaa0bf18a4adfa12474ad58b765fd06
Author: Your Name <your_email>
Date:   Mon Jun 5 12:41:45 2017 +0100

    Add another line

commit e9e8fd3f12b64fc3cbe8533e321ef2cdb1f4ed39
Author: Your Name <your_email>
Date:   Fri Jun 2 18:15:43 2017 +0100

    Add index.md
~~~
{: .output}

This shows us the two commits we have made and shows the messages we wrote. It is important to try to use meaningful
commit messages when we make changes. This is especially important when we are working with other people who might not
be able to guess as easily what our short cryptic messages might mean. Note that it is best practice to always write
commit messages in the imperative (e.g. 'Add index.md', rather than 'Adding index.md').

## Pushing changes (again)

Now, let's have a look at the repository at GitHub again
(that is, `https://github.com/some-librarian/hello-world` with `some-librarian` replaced with your username).
We see that the `index.md` file is there, but there is only one commit:

![Only one commit on GitHub](../fig/github-one-commit.png)

And if you click on `index.md` you will see that it contains the "Hello, world!" header,
but not the new line we just added.

This is because we haven't yet pushed our local changes to the remote repository.
This might seem like a mistake in design but it is
often useful to make a lot of commits for small changes so you are able to make careful revisions later and you don't
necessarily want to push all these changes one by one.

Another benefit of this design is that you can make commits without being connected to internet.

But let's push our changes now, using the `git push` command:

~~~
$ git push
~~~
{: .language-bash }
~~~
Counting objects: 3, done.
Writing objects: 100% (3/3), 272 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/<your_github_username>/hello-world
   e9e8fd3..8e2eb99  main -> main
~~~
{: .output}

And let's check on GitHub that we now have 2 commits there.

## Pulling changes

When working with others, or when we're making our own changes from different machines, we need a way of pulling those
remote changes back into our local copy. For now, we can see how this works by making a change on the GitHub website and
then 'pulling' that change back to our computer.

Let's go to our repository in GitHub and make a change. Underneath where our index.md file is listed you will see a
button to 'Add a README'. Do this now, entering whatever you like, scrolling to the bottom and clicking 'Commit new
file' (The default commit message will be 'Create README.md', which is fine for our purposes).

> ## The README file
> It is good practice to add a README file to each project to give a brief overview of what the project is about. If you
> put your README file in your repository's root directory, GitHub will recognize and automatically surface your README
> to repository visitors
{: .callout}

Our local repository is now out of sync with our remote repository, so let's fix that by pulling the remote changes into
our local repository using the `git pull` command.

~~~
$ git pull
~~~
{: .language-bash }
~~~
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/<your_github_username>/hello-world
   8e2eb99..0f5a7b0  main     -> origin/main
Updating 8e2eb99..0f5a7b0
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
~~~
{: .output}

The above output shows that we have fast-forwarded our local repository to include the file README.md. We could confirm
this by entering the `ls` command.

When we begin collaborating on more complex projects, we may have to consider more aspects of git functionality, but
this should be a good start. In the next section, we can look more closely at collaborating and using GitHub pages to
create a website for our project.
