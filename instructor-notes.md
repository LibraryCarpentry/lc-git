---
title: Instructors' Guide
---

***

# Tips and Tricks

Known problems that learners encounter:

*Windows*: When using an outdated version of Windows OpenSSH, learners cannot set up the SSH connection to GitHub. SOLUTION: Update OpenSSH version.

***

## Making a handout

To make a handout for this lesson, adapt/print from [https://librarycarpentry.org/lc-git/reference.html](https://librarycarpentry.org/lc-git/reference.html).

***

# General notes on Git

Using a software tool to handle the versions of your project files
lets you focus on the more interesting/innovative aspects of your project.

- Version control's advantages
  - It's easy to set up
  - Every copy of a Git repository is a full backup of a project and its history
  - A few easy-to-remember commands are all you need for most day-to-day version control tasks
  - The [GitHub](https://github.com/) hosting service provides a web-based collaboration service
- Two main concepts
  - *commit*: a recorded set of changes in your project's files
  - *repository*: the history of all your project's commits
- Why use GitHub?
  - No need for a server: easy to set up
  - GitHub's strong community: your colleagues are probably already there

## Overall

Version control might be the most important topic we teach, but Git is
definitely the most complicated tool.  However, GitHub presently dominates the
open software repository landscape, so the time and effort required to teach
fundamental Git is justified and worthwhile.

Because of this complexity, we don't teach novice learners about many
interesting topics, such as branching, hashes, and commit objects.

Instead we try to convince them that version control is useful for researchers
working in teams or not, because it is

- a better way to "undo" changes,
- a better way to collaborate than mailing files back and forth, and
- a better way to share your code and other scientific work with the world.

## Teaching Notes

- Resources for "splitting" your shell so that recent commands remain in view: [https://github.com/rgaiacs/swc-shell-split-window](https://github.com/rgaiacs/swc-shell-split-window).

- Make sure the network is working *before* starting this lesson.

- Drawings are particularly useful in this lesson: if you have a whiteboard,
  use it to visualise and describe the [GitHub flow](https://guides.github.com/introduction/flow/).

- Version control is usually not the first subject in a workshop,
  so get learners to create a GitHub account after the session before.
  Remind learners that the username and email they use for GitHub (and setup
  during Git configuration) will be viewable to the public by default.
  However, there are many reasons why a learner may not want their personal
  information viewable, and GitHub has [resources for keeping an email address
  private](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address).

- If some learners are using Windows, there will inevitably be issues
  merging files with different line endings.  (Even if everyone's on
  some flavor of Unix, different editors may or may not add a
  newline to the last line of a file.) Take a moment to explain
  these issues, since learners will almost certainly trip over them
  again.  If learners are running into line ending problems, GitHub
  has a [page](https://help.github.com/en/articles/dealing-with-line-endings) that helps with troubleshooting.

- We don't use a Git GUI in these notes because we haven't found one that
  installs easily and runs reliably on the three major operating systems, and
  because we want learners to understand what commands are being run.  That
  said, instructors should demo a GUI on their desktop at some point during
  this lesson and point learners at [this page](https://git-scm.com/downloads/guis).

- Instructors should show learners graphical diff/merge tools like
  [DiffMerge](https://sourcegear.com/diffmerge/).

- When appropriate, explain that we teach Git rather than CVS, Subversion, or
  Mercurial primarily because of GitHub's growing popularity: CVS and
  Subversion are now seen as legacy systems, and Mercurial isn't nearly as
  widely used in the sciences right now.

- Further resources:
  
  - [git-it](https://github.com/jlord/git-it-electron#git-it-desktop-app) is a self-paced command-line Git demo,
    with [git-it-electron](https://github.com/jlord/git-it-electron) its GitHub Desktop successor.
  - Try GitHub's [resources to learn Git](https://try.github.io/) or Codeacademy's [Learn Git](https://www.codecademy.com/learn/learn-git).
  - For instructors, [the Git parable](https://tom.preston-werner.com/2009/05/19/the-git-parable.html) is useful background reading.


