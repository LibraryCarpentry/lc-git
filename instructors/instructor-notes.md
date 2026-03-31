---
title: Instructors' Guide
---

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

## Troubleshooting Common Problems

- When using an outdated version of Windows OpenSSH, learners cannot set up the SSH connection to GitHub.

  - Try updating their version of OpenSSH version.

## Making a handout

To make a handout for this lesson, adapt/print from the [Reference page](https://librarycarpentry.org/lc-git/reference.html).

## Teaching Notes

- Utility for "splitting" your shell so that recent commands remain in view: [Software Carpentry Shell Split Window](https://github.com/UCL-ARC/swc-shell-split-window).

- Make sure the network is working *before* starting this lesson.

- Drawings are particularly useful in this lesson: if you have a whiteboard,
  use it to visualise and describe GitHub flow.
  The [current documentation of GitHub flow](https://docs.github.com/en/get-started/using-github/github-flow) is text-heavy,
  so it might be easier to draw inspiration from the interactive guide "[Understanding the GitHub flow](https://web.archive.org/web/20200728161719/https://guides.github.com/introduction/flow/)" from 2020.

- Version control is usually not the first subject in a workshop,
  so get learners to create a GitHub account after the session before.
  Remind learners that the username and email they use for GitHub (and setup
  during Git configuration) will be viewable to the public by default.
  However, there are many reasons why a learner may not want their personal
  information viewable, and GitHub has [resources for keeping an email address
  private](https://docs.github.com/en/account-and-profile/how-tos/email-preferences/setting-your-commit-email-address).

- It is likely that learners will run into issues when merging files due to whitespace differences.
  For example, a text editor might automatically add a newline to the last line of a file, causing an unexpected difference.
  Conflicts can also arise due to Windows using different line endings from other operating systems.
  Take a moment to explain these issues, since learners will almost certainly trip over them again.
  GitHub provides guidance on [how to configure Git to handle line endings](https://docs.github.com/en/get-started/git-basics/configuring-git-to-handle-line-endings);
  the [section on refreshing a repository](https://docs.github.com/en/github/using-git/configuring-git-to-handle-line-endings#refreshing-a-repository-after-changing-line-endings) may be helpful if learners need to change the `core.autocrlf` setting after already having made one or more commits.

- We don't use a Git GUI in this lesson because we haven't found one that
  installs easily and runs reliably on the three major operating systems, and
  because we want learners to understand what commands are being run.  That
  said, instructors should demo a GUI on their desktop at some point during
  this lesson and point learners at the Git website's [list of available GUIs](https://git-scm.com/tools/guis).

- Instructors should show learners graphical diff/merge tools like
  [DiffMerge](https://sourcegear.com/diffmerge/).

- When appropriate, explain that we teach Git rather than CVS, Subversion, or
  Mercurial primarily because of GitHub's growing popularity: CVS and
  Subversion are now seen as legacy systems, and Mercurial isn't nearly as
  widely used in the sciences right now.

- Further resources:
  
  - [Git-it](https://github.com/jlord/git-it-electron#git-it-desktop-app) is a self-paced Git demo that runs as an app on your computer.
  - Try GitHub's [resources to learn Git](https://learn.github.com/) or Codecademy's [Learn Git & GitHub](https://www.codecademy.com/learn/learn-git).
  - For instructors, [the Git parable](https://tom.preston-werner.com/2009/05/19/the-git-parable.html) is useful background reading.
