---
title: "Github pages"
teaching: 15
exercises: 20
questions:
- "what is GitHub Pages?"
objectives:
- "set up a website using Github Pages"
- "share work and collaborate using GitHub"
keypoints:
- "GitHub Pages use the Git/GitHub workflow to help you build webpages"
---
## GitHub Pages

GitHub Pages are websites hosted on GitHub. They allow you to build a repository that displays as a website. GitHub pages uses Jekyll, a 'blog-aware static site generator' to turn a site of files and folders into a website.

### Why GitHub pages are awesome!

GitHub pages allow you to version control your website. This is useful for a lot of different reasons. It allows you to keep a record of what changes you have made. It allows people to reference your website at a particular point in time and (if you make your source open) to see what it was like at that particular point in time. This is very useful for academic citations. Most people have had the experience of following up a reference to a website and either getting a 404 error or seeing something completely different. Although using versions on your site doesn't guarantee this won't happen, it does make it easier to manage old versions of your site.

GitHub pages also mean that you can collaborate on a website with a lot of people without everyone having to communicate endlessly back and forwards about what changes need to be made, or have been made already. You can create 'issues' (things that need discussing or fixing), list things to do in the future, and allow other people visiting your website to quickly suggest, and help implement changes through pull requests.

### Setting up a GitHub page

Now we're all persuaded of how awesome GitHub pages are (or you've identified some fatal flaws in my reasoning), it would be useful to try playing around with some things we can do with GitHub pages. This will help us cement what we have learned in the previous hour and may help spark discussion for the last section of this session.

### Exercise - contributing to a GitHub pages site

To practise using Git, GitHub pages and Markdown we can contribute to a GitHub pages site. This page is currently very bare but we can change that by making some pull requests and suggesting changes.

#### pull-request (slightly easier way)
1. Navigate to the https://github.com/davanstrien/week-three-library-carpentry
2. Click on 'fork' repository. You will then be asked to choose where to 'fork' your repository.
3. Once we have our own fork, we can edit files directly from the GitHub site. This is a good chance to practise some markdown syntax. You can preview how it will look before you commit changes. N.B. this is 'GitHub' flavour of markdown; there are slight differences between different 'flavours'.
4. Once we have done this, we can commit our changes.
5. If we've made some changes which we think would be worth adding to the original site, then we can create a pull request. This slightly confusing terminology basically means you are asking the owner of the original source if they would like to add (pull) some of your changes into their version.
6. Click on compare changes. This will show you if there are any differences between the two versions you have. From here we can make a pull request.
7. When we make a pull request, we have the option of explaining what the pull request relates to. It is important to give a short concise explanation of what it is about.

#### pull-request (slightly more complicated way)
* instead of making edits on the GitHub website you can 'clone' the repository to your local machine.
* follow steps 1 and 2 above.
* then follow the steps outlined here: http://www.thinkful.com/learn/github-pull-request-tutorial/Writing-a-Good-Commit-Message
