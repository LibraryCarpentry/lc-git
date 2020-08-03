---
layout: page
title: Setup
---

If you haven't done so already, to follow this lesson you will need to:

1. Create a free [GitHub account](https://github.com/join) and confirm your email.
2. Download and install Git for your operating system: [https://git-scm.com/downloads](https://git-scm.com/downloads) (*Note:* Git for Windows comes bundled with the Git BASH terminal that allows you to use UNIX-style commands on Windows)
3. Configure Git by opening a terminal window and entering the following commands:

~~~
$ git config --global user.name "Your Name"
$ git config --global user.email "your@email"
~~~
{: .language-bash }

This user name and email will be recorded with each commit in the history of your repositories.
The email address should be the same one you used when setting up your GitHub account.

By default, Git will open the Vi / Vim text editor to request commit messages (for example when merging conflicts).
To avoid confusion, most people will want to change the default editor to something more familiar using the `core.editor` config.
Any text editor can be made default by adding the correct file path and command line options (see [GitHub help](https://help.github.com/articles/associating-text-editors-with-git/)).
However, the simplest `core.editor` values are `"notepad"` on Windows,  `"nano -w"` on Mac, and `"nano -w"` on Linux.
For example:

~~~
$ git config --global core.editor "notepad"
~~~
{: .language-bash }
You will NOT get an immediate error message if you specify an incorrect or non-existent text editor command here. Therefore, you may first wish to test that the text editor you specify can be invoked, with (for the above example of `"notepad"` on Windows):

~~~
$ touch deleteme.txt
$ notepad deleteme.txt
~~~
{: .language-bash }
