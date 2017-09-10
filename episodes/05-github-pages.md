---
title: "Github Pages"
teaching: 15
exercises: 20
questions:
- "What is GitHub Pages?"
objectives:
- "set up a website using Github Pages"
- "share work and collaborate using GitHub"
keypoints:
- "GitHub Pages use the Git/GitHub workflow to help you build webpages"
---
## GitHub Pages

GitHub Pages is a simple service to publish a website directly on GitHub from a Git repository.
You add some files and folders to a repository and GitHub Pages turns it into a website.
You can use HTML directly if you like, but they also provide Jekyll,
which renders Markdown into HTML and makes it really easy to setup a blog or a template-based website.

### Why GitHub Pages is awesome!

GitHub Pages allows you to version control your website. This is useful for a lot of different reasons. It allows you to 
keep a record of what changes you have made. It allows people to reference your website at a particular point in time 
and (if you make your source open) to see what it was like at that particular point in time. This is very useful for 
academic citations. Most people have had the experience of following up a reference to a website and either getting a 
404 error or seeing something completely different. Although using versions on your site doesn't guarantee this won't 
happen, it does make it easier to manage old versions of your site.

GitHub Pages also mean that you can collaborate on a website with a lot of people without everyone having to 
communicate endlessly back and forwards about what changes need to be made, or have been made already. You can create 
'issues' (things that need discussing or fixing), list things to do in the future, and allow other people visiting your 
website to quickly suggest, and help implement changes through pull requests.

### Setting up a site

Now we're all persuaded of how awesome GitHub Pages is (or you've identified some fatal flaws in my reasoning), it 
would be useful to try playing around with some things we can do with it. This will help us cement what we 
have learned in the previous hour and may help spark discussion for the last section of this session.

There are various options for setting up a GitHub Pages site. Let's run through a few of them now.

### The gh-pages branch

GitHub Pages uses a special branch in your GitHub repository to look for website content,
and by default this is the branch with the name 'gh-pages'.
You can actually change this, under repository settings, to use for instance the master branch instead,
but let's stick with the default for now.

It's possible to create a new branch directly on GitHub, but we will use the command line now.
So we will move back to the command line and type

~~~
$ git checkout -b gh-pages
$ git push
~~~
{: .bash}
~~~
fatal: The current branch gh-pages has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin gh-pages
~~~
{: .output}

Ouch, that didn't go as we wanted, we got a fatal error!
Let's see what Git tells us.
It says that it doesn't know where it should push the changes.
But it's also friendly enough to tell us what we most likely want to do,
which is to push to the `gh-pages` branch at "origin"
(remember that "origin" in our case is just a nickname for our GitHub repository).

So let's do that:

~~~
$ git push --set-upstream origin gh-pages
~~~
{: .bash}
~~~
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/danmichaelo/hello-world.git
 * [new branch]      gh-pages -> gh-pages
Branch gh-pages set up to track remote branch gh-pages from origin.
~~~
{: .output}

You might remember from earlier that we did `git push -u origin master` to
set up the master branch. The `-u` is a shorthand for `--set-upstream`, so
above you could also have typed `git push -u origin gh-pages`.

### Exercise - Contributing to a GitHub pages site

To practise using Git, GitHub pages and Markdown we can contribute to a GitHub pages site. This page is currently 
very bare but we can change that by making some pull requests and suggesting changes.

#### pull-request (slightly easier way)
1. Navigate to the https://github.com/davanstrien/week-three-library-carpentry
2. Click on 'fork' repository. You will then be asked to choose where to 'fork' your repository.
3. Once we have our own fork, we can edit files directly from the GitHub site. This is a good chance to practise some 
markdown syntax. You can preview how it will look before you commit changes. N.B. this is 'GitHub' flavour of markdown; 
there are slight differences between different 'flavours'.
4. Once we have done this, we can commit our changes.
5. If we've made some changes which we think would be worth adding to the original site, then we can create a pull 
request. This slightly confusing terminology basically means you are asking the owner of the original source if they 
would like to add (pull) some of your changes into their version.
6. Click on compare changes. This will show you if there are any differences between the two versions you have. From 
here we can make a pull request.
7. When we make a pull request, we have the option of explaining what the pull request relates to. It is important to 
give a short concise explanation of what it is about.

#### pull-request (slightly more complicated way)
* instead of making edits on the GitHub website you can 'clone' the repository to your local machine.
* follow steps 1 and 2 above.
* then follow the steps outlined here: http://www.thinkful.com/learn/github-pull-request-tutorial/Writing-a-Good-Commit-Message
And remember, we only have to do this the first time we push to a new branch.
The next time we can just do `git push`.

If we now visit http://your-github-username.github.io/hello-world/ ,
we should see the contents of the index.md file that created earlier.
Usually it's available instantly, but it can take a few seconds and in the worst case a few minutes if GitHub are very busy.

