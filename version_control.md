**BES Guide to Reproducible Code: Version Control**

Scripts for reproducible code evolve over time, so keeping track
of the changes that you make is important. You might need to access a
particular version of your code in order to verify or reproduce the
analysis used for a published paper, or to identify where you introduced
a change which has caused problems in your code at a later stage.

Anyone who has wrestled with multiple versions of a document or script
named by appending the word ``final'' will know how quickly such naming
conventions can
[escalate into absurdity](http://phdcomics.com/comics.php?f=1531).
[Version control](https://en.wikipedia.org/wiki/Version_control)
provides a structured and transparent means of tracking changes to code
and other files. Although it was developed for use in software
development it is equally applicable to scientific programming.  Using
version control allows you to back up old versions of files while
keeping your workspace clean. By recording snapshots of a project at
particular points in time, you can create a record of your project’s
development. Version control also facilitates collaboration when used
within project teams or when contributing to open source software
projects.

**Version control with cloud file storage services**

Some cloud services such as Google Drive and Dropbox offer access to a
file’s version history, backing up versions for a limited time,
usually 30 days, and allowing restoration of previous versions within
this time frame. While this can be a useful option for managing recent
changes, for example to recover a previous version of a
document, we don't recommend this route because there is limited
control over revisions.

**Version control software**

Version control software is designed to help you to manage your file
revisions. A wide range of version control software, both open source
and proprietary, is available. In this guide we’ll focus on the widely
used open source software called [*git*](https://en.wikipedia.org/wiki/Git).

Git is a distributed version control system, which means that each user
interacts with a standalone copy of the versioned files, called a
*repository*. Individual repositories are synchronized with each other
by exchanging information about what changes have been made. Git can be
used as an independent tool or through software such as RStudio, so it
is easily integrated into your normal workflow.

Git is suitable for managing files which are largely text-based, such as
code or text files with simple formatting like RMarkdown. It can also be
used to store versions for other files such as graphics. Tracking changes in
documents with extended file formats such as Word documents is better
done using built-in revision control, although you can store file
versions using git.

Git is not recommended for use with large files such as databases due to
the storage and bandwidth required. [Git Large File Storage (Git LFS)](https://git-lfs.github.com/) is
an extension to git that can be used to manage large files by storing
them outside your git repository, ensuring that the repository does not
become unmanageably large.

**Getting started with git**

-   To get started you’ll need to download git:
    [*https://git-scm.com/downloads*](https://git-scm.com/downloads)

-   Once installed you should configure git with your name and email
    address so that this information can be added to your
    version history.

-   If you want to use RStudio’s git integration, go to
    Options/Preferences &gt; Git/SVN and make sure that the path to
    the git executable is correctly specified.

**Version control repository hosting services**

Git is sometimes confused with *GitHub*, which is a web-based hosting
service for git repositories. There are a range of version control repository hosting services,
including GitHub, GitLab, Bitbucket, and Savannah. These services allow you to
create a remote copy of your local version control repository and to use it as an
off-site backup and archive. It’s easy to make your work available to
collaborators through these services.

Version control repository hosting services offer a choice between public and private
repositories. The former can be used for publicly accessible work,
while the latter may be more suitable for sensitive or unpublished
work. Public repositories are visible to anyone through the hosting
service; however, the owner of the repository retains full control
over the contents of the repository.


Currently, GitHub provides unlimited private repositories for
educational users
[*https://education.github.com/discount\_requests/new*](https://education.github.com/discount_requests/new)

Repository hosting services such as GitHub provide many other features
including file preview and rendering, submitting change requests
through the web browser interface, issue tracking, wiki-style
documentation and website hosting. GitHub is also integrated with the
open access data repository service, Zenodo.

**Git and the command line**

While git can be used through software with a graphical user interface
such as RStudio, there are occasions when you’ll need to use the command
line. These include git configuration and setting up remote
repositories. You can access the command line (Terminal in MacOS and Linux or
Command Prompt in Windows) from RStudio by going to Tools &gt; Shell…

**Version control workflow**

*Typical use of git in a version control workflow*

When using git for a project we follow these steps:

1.  Set up a local repository

2.  Write some code.

3.  Save the file to the working directory or R project

4.  Check what is ready to add or commit

5.  Choose files to be included in the commit

6.  Commit the files with a suitable message e.g. "My first commit"

7.  Make sure your local repository is connected to a remote GitHub
    repository

8.  Push your code to the remote GitHub repository

9.  Repeat steps 2-8

We describe these steps in more detail below.

*Setting up a repository*

A git repository is simply a directory on your computer with some hidden
files for bookkeeping. You can create a git repository from scratch when
you create an RStudio project. You can also clone git repositories from
existing repositories (such as those on GitHub) or create them directly
using the command line.

If you have set up a version-controlled project in RStudio, the
operations described below are available from the “Git” tab within the
Environment/History panel.

*Adding or staging files*

Git will only keep track of modifications to files that it has been
asked to manage, so you need to tell git which files to include. You can
do this by adding or staging files in your project directory.

*Creating a commit*

A commit is a snapshot of the changes to the project directory and forms
part of the history of your project through time. When you commit
changes using git you’ll be prompted to enter a *commit message*. This
can be used to provide a description of the changes that you’ve made.
Each commit is assigned a unique identifier which is stored together
with the date, author, and commit message. This identifier can be used
to specify a commit.

*Connecting to a remote repository*

While a local git repository can help you to track changes to files, in
order to back up your version history and share code with others you’ll
want to link your repository to a remote repository. Syncing your local
repository to a remote repository will archive your code and provide a centralised
store for your project, allowing you to share your work or to access it
from another computer.

You can set up a remote repository on a hosting service such as GitHub
or host it on your own server. If you’re using a repository hosting
service, make sure that you choose a private or public repository
according to your needs.

*Pushing to the remote repository*

This step sends the details of any commits which have been made locally
to the specified remote repository which can act as a backup of your
work or a resource to share with others.

**What you can do with version control**

Once you have a git version control workflow in place it can be useful
in a number of different ways.

*Viewing your version history*

The version history that you build up as you commit your work forms a
record of the changes that you’ve made to your code or documents. This
can help you to track a project’s development, understand reasons for
past coding decisions, highlight major revisions and identify where bugs
were introduced.

*Returning to a previous commit*

The real power of git will become clear when you need to return to a
previous point in your revision history, for example to recreate figures
for a paper or to run an analysis again. You can use the unique ID for a
commit to tell git to return your working directory to the state
captured by that commit. You can then work with your code as it was at
that point in time.

*Using version control to collaborate*

There are a number of alternative models for collaborating when using
version control. When you use a distributed system such as git, each
individual collaborator works with their own repository and you need to
decide how to combine your work. A couple of possible workflows are:

1.  Everyone connects their local repository to the same remote
    repository and must coordinate their changes. Changes to the
    central repository must be integrated into a user’s local
    repository before they can submit their own changes to the remote
    repository.

2.  Individual contributors create a copy or *fork* of the main
    repository and use this as their remote repository. They must send
    a request to the maintainer of the main repository to incorporate
    their changes into the main repository. This model allows a
    formalised review process before changes are integrated and is
    often used in open source projects.

**Going further with version control**

Git is a flexible and powerful toolkit that provides a wide range of
advanced features such as *branching*, *stashing* and *tagging*. These
topics are beyond the scope of this guide but there are many online
resources where you can read more about using these features in your
workflow.

**Resources**

-   Git - the simple guide by Roger Dudler
    [*http://rogerdudler.github.io/git-guide/*](http://rogerdudler.github.io/git-guide/)

-   Software Carpentry guide to Version Control with Git
    [*http://swcarpentry.github.io/git-novice/*](http://swcarpentry.github.io/git-novice/)

-   Chacon, S. and Straub, B., 2014. *Pro git*. Apress.
    [*https://git-scm.com/book/en/v2*](https://git-scm.com/book/en/v2)

#### **Cheatsheets and troubleshooting**

-   Git reference/cheatsheets
    [*https://git-scm.com/docs*](https://git-scm.com/docs)

-   Oh shit git! [*http://ohshitgit.com/*](http://ohshitgit.com/)

**Using git with RStudio**

-   Using Version Control with RStudio
    [*https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN*](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)
