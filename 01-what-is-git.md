---
title: What is Git/GitHub?
teaching: 10
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- recognize why version control is useful
- distinguish between Git and GitHub

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- What is Git?
- What is GitHub?

::::::::::::::::::::::::::::::::::::::::::::::::::

## What is Version Control

Version control is a name used for software which can help you record changes you make to the files in a directory on your computer. Version control software and tools (such as Git and Subversion/SVN) are often associated with software development, and increasingly, they are being used to collaborate in research and academic environments. Version control systems work best with plain text files such as documents or computer code, but modern version control systems can be used to track changes in any type of file.

At its most basic level, version control software helps us register and track sets of changes made to files on our computer. We can then reason about and share those changes with others. As we build up sets of changes over time, we begin to see some benefits.

### Benefits of using version control?

- **Collaboration** - Version control allows us to define formalized ways we can work together and share writing and code. For example merging together sets of changes from different parties enables co-creation of documents and software across distributed teams.
- **Versioning** - Having a robust and rigorous log of changes to a file, without renaming files (v1, v2, *final\_copy*)
- **Rolling Back** - Version control allows us to quickly undo a set of changes. This can be useful when new writing or new additions to code introduce problems.
- **Understanding** - Version control can help you understand how the code or writing came to be, who wrote or contributed particular parts, and who you might ask to help understand it better.
- **Backup** - While not meant to be a backup solution, using version control systems mean that your code and writing can be stored on multiple other computers.

There are many more reasons to use version control, and we'll explore some of these in the library context, but first let's learn a bit about a popular version control tool called Git.

## What are Git and GitHub?

We often hear the terms ***Git*** and ***GitHub*** used interchangeably but they are slightly different things.

***Git*** is one of the most widely used version control systems in the world. It is a free, open source tool that can be downloaded to your local machine and used for logging all changes made to a group of designated computer files (referred to as a "git repository" or "repo" for short) over time. It can be used to control file versions locally by you alone on your computer, but is perhaps most powerful when employed to coordinate simultaneous work on a group of files shared among distributed groups of people.

Rather than emailing documents with tracked changes and some comments and renaming different versions of files (example.txt, exampleV2.txt, exampleV3.txt) to differentiate them, we can use Git to save (or in Git parlance, "commit") all that information with the document itself. This makes it easy to get an overview of all changes made to a file over time by looking at a log of all the changes that have been made. And all earlier versions of each file still remain in their original form: they are not overwritten, should we ever wish to "roll back" to them.

Git was originally developed to help software developers work collaboratively on software projects, but it can be and is used for managing revisions to any file type on a computer system, including text documents and spreadsheets. Once installed, interaction with Git is done through the Command Prompt in Windows, or the Terminal on Mac/Linux. Since Word documents contain special formatting, Git unfortunately cannot version control those, nor can it version control PDFs, though both file types can be stored in Git repositories.

*How can understanding Git help with work in libraries?*

- Enables you to contribute to, collaborate on, and support digital research projects
- Enables you to control changes to your files over time without keeping multiple copies of those files

***GitHub*** on the other hand is a popular website for hosting and sharing Git repositories remotely. It offers a web interface and provides functionality and a mixture of both free and paid services for working with such repositories. The majority of the content that GitHub hosts is open source software, though increasingly it is being used for other projects such as open access journals (e.g. [Journal of Open Source Software](https://joss.theoj.org/)), blogs, and regularly updated text books.  In addition to GitHub, there are other Git hosting services that offer many similar features such as [GitLab](https://about.gitlab.com/), [Bitbucket](https://bitbucket.org/) and [Gitee](https://gitee.com/).

*How can GitHub help with work in libraries?*

- A place to discover and reuse ("fork") a huge amount of openly licensed digital projects and open source software
- A new and alternative means for publishing content online. Any GitHub repository can have its own project website, blog and wiki using GitHub Pages.

## Uses in a Library Context

Consider these common library world scenarios:

### Scenario 1: Local library looking to start a crowdsourcing project

A local librarian is looking to put thousands of historical photographs of the area online so that the community can help identify the people and places they depict. She combs the web for examples of existing crowdsourcing projects, and even though they all appear unique to each institution, she notices quite a few seem to have almost the exact same functionality and structure. Rather than build a whole new version from scratch herself, she wishes there was a way to just copy the code of an existing one, and modify it to reflect her project. She notices the [GitHub icon](https://github.com/logos) at the bottom of one of the projects she likes, but clicking on the link just brings her to a confusing directory of files and oddly labeled buttons such as "Fork".

GitHub hosts many open-licensed projects and allows any user to fork any public project. By clicking the "fork" button, any GitHub user can almost instantaneously create their own version of an existing project. That "forked" project can be used as the basis for a new project, or can be used to work out new features that can be merged back into the original. (From: [GitHub for Academics](https://hybridpedagogy.org/push-pull-fork-github-for-academics/) )

### Scenario 2: Multiple people editing metadata for a collection

A metadata specialist has exported a spreadsheet from a repository for cleaning and editing. She's working with a group of library workers and students, so they need to make sure edits don't conflict. They also need to be able to undo any edits and preserve the original metadata. Once edits are complete, the whole group wants to review the changes before re-ingesting the spreadsheet of metadata into the repository.

The team can choose to use Git by itself to track changes and resolve conflicts or they can choose to use GitHub to host the project so that users can collaborate and review changes on the Web. Git will preserve the original metadata as well as all edits. GitHub will facilitate discussion about what changes should be made, who should make them, and why.

:::::::::::::::::::::::::::::::::::::::: keypoints

- Version control helps track changes to files and projects
- Git and GitHub are not the same

::::::::::::::::::::::::::::::::::::::::::::::::::


