## Version Control

Scripts for reproducible code evolve over time, so keeping track
of the changes that you make is important. You might need to access a
specific version of your code in order to verify or reproduce the
analysis used for a published paper, or to identify where you introduced
a change which has caused problems in your code at a later stage.

Anyone who has wrestled with multiple versions of a document or script
named by appending the word ``final'' will know how quickly such
naming conventions can
[escalate into absurdity](http://phdcomics.com/comics.php?f=1531).
[Version control](https://en.wikipedia.org/wiki/Version_control)
provides a structured and transparent means of tracking changes to
code and other files. Although it was designed for use in software
development it is equally applicable to scientific programming.  Using
version control allows you to back up old versions of files while
keeping your workspace clean. By recording snapshots of a project at
successive points in time, you can create a record of your project’s
development while keeping your workspace clean. Version control also
facilitates collaboration when used within project teams or when
contributing to open source software projects.

### Version control with cloud file storage services

Some cloud services such as Google Drive and Dropbox offer access to a
file’s version history, backing up versions for a limited time,
usually 30 days, and allowing restoration of previous versions within
this time frame. While this can be a useful option for managing recent
changes, for example to recover a previous version of a
document, we don't recommend this route because there is limited
control over revisions.

### Version control software

Version control software is software designed to help you to manage
your file revisions. Version control software runs directly on your
computer, allowing you to manage files within your local file
system. You can also use version control software to interact with
external copies of versioned files if you choose.

Version control software is suitable for managing files which are
largely text-based, such as code or text files with simple formatting
like Markdown. It can also be used to store versions of other files
such as graphics. Tracking changes in documents with extended file
formats such as Word documents is better done using built-in revision
control, although you can use version control software to store
snapshots of these files.

Version control software is not recommended for use with very large
files such as data files or databases because these generate excessive
storage and download requirements. It is better to use other storage
solutions for this type of file.

---

------------------- ----------------------------------------
**Note**\           [Git Large File Storage (Git LFS)](https://git-lfs.github.com/)
                    is an extension to git that can be
                    used to manage large files by
                    storing them outside your git
                    repository, ensuring that the
                    repository does not become
                    unmanageably large.

----------------------------------------------------------------

---

A wide range of version control software, both open source
and proprietary, is available. In this guide we’ll focus on the widely
used open source software called [*git*](https://en.wikipedia.org/wiki/Git).

Git is a good choice because its distributed model offers flexibility
in how you can use it for version control. You can use it as a
standalone tool to manage files in your own file system and,
optionally, you can use it to connect to an external service to
archive your files. Git can be used directly or through other software
such as RStudio, so it is easily integrated into your normal workflow.

Git is a distributed version control system, which means that each user
interacts with a standalone copy of the versioned files, called a
*repository*. Individual repositories are synchronised with each other
by exchanging information about what changes have been made. Typically,
changes are coordinated via a centralised repository but there are a
range of other possible working models.

### Version control repository hosting services

Git is sometimes confused with *GitHub*, which is a web-based hosting
service for git repositories. There are a range of version control repository hosting services,
including GitHub, GitLab, Bitbucket, and Savannah. These services allow you to
create a remote copy of your local version controlled project and to use it as an
off-site backup and archive. It’s easy to make your work available to
collaborators through these services.

Version control repository hosting services offer a choice between *public* and *private*
repositories. The former can be used for publicly accessible work,
while the latter may be more suitable for sensitive or unpublished
work. Public repositories are visible to anyone through the hosting
service website. However, the owner of the repository retains control
over the contents of the repository.

---

------------------- --------------------------------------------
**Note**\           Currently, GitHub provides unlimited
                    private repositories for educational
                    users:
                    [*https://education.github.com/discount\_requests/new*](https://education.github.com/discount_requests/new)<br>
                    Your account needs to be associated with
                    an academic/educational email address.

---------------------------------------------------------------------

---

Repository hosting services such as GitHub provide many other features
including file preview and rendering, submitting change requests
through the web browser, issue tracking, wiki-style documentation and
website hosting. Some services offer desktop client software which can
be used to access your remote repository. GitHub is also integrated
with the open access data repository service, Zenodo.

---

#### Getting started with git

-   To get started you’ll need to download git:
    [*https://git-scm.com/downloads*](https://git-scm.com/downloads)

-   Once installed you should configure git with your name and email
    address so that this information can be added to your
    version history.

-   If you want to use RStudio’s git integration, go to
    Options/Preferences &gt; Git/SVN and make sure that the path to
    the git executable is correctly specified.

#### Git and the command line

While git can be used through software with a graphical user interface
such as RStudio, there are occasions when you’ll need to use the command
line. These include git configuration and setting up remote
repositories. You can access the command line (Terminal in MacOS and Linux or
Command Prompt in Windows) from RStudio by going to Tools &gt; Shell…

---

### Version control workflow

In this section, we aim to give you an overview of basic version
control workflow. We introduce some of the terminology used and
provide some examples of how to carry out simple workflow tasks in
git. You can find more help in the
[materials from the BES Best Practice for Code Archiving workshop](https://github.com/BES2016Workshop/version-control)
or by consulting some of the resources that we recommend at the end of
this section.

<!-- TODO Replace figure with accessible markdown version -->
![Figure 1. Steps in a typical version control workflow, with examples
 for carrying out the steps using git at the command line or through
 RStudio.](version_control_workflow.png)

#### Basic version control workflow

A typical version control workflow (Figure 1) includes the following steps:

1. Set up a local version control repository.
2. Write some code.
3. Save your script to the repository.
4. Choose files to be included in the version history.
5. Create a record of your changes in the version history with a suitable message e.g. "Add new script to project".
6. Sync your changes with a remote repository.
7. Repeat steps 2-7.

We describe carrying out these steps using git in more detail below.

#### Setting up a repository

When you use git you interact with a set of versioned files called a *repository*.
A git repository is simply a directory on your computer with some hidden
files for bookkeeping. You can create a git repository from scratch when
you create an RStudio project. You can also clone git repositories from
existing repositories (such as those on GitHub) or create them directly
using the command line.

If you have set up a version-controlled project in RStudio, the
operations described below are available from the “Git” tab within the
Environment/History panel.

#### Adding or staging files

Git will only keep track of modifications to files that it has been
asked to manage, so you need to tell git which files to include in your version history. You can
do this by *adding* or *staging* files in your project directory.

#### Creating a commit

A *commit* is a snapshot of the changes to the repository and forms
part of the history of your project through time. When you create a commit
using git you’ll be prompted to enter a *commit message*. This
can be used to provide a description of the changes that you’ve made.
Each git commit is assigned a unique identifier which is stored together
with the date, author, and commit message. This identifier can be used
to specify a commit later.

#### Connecting to a remote repository

A local git repository allows you to track changes to files, storing
the details in your version history and allowing you to go back to
previous file versions if necessary. If you want to create an external
copy of your version history and share code with others you should
consider linking your repository to a *remote* repository. Synchronising
your local repository to the remote repository will archive your code
and provide a centralised store for your project, making it easy for
you to share your work or to access it from another computer.

You can set up a remote repository on a hosting service such as GitHub
or host it on your own server. If you’re using a repository hosting
service, make sure that you choose a private or public repository
according to your needs. Please note that a public repository doesn’t
mean anyone can directly make changes to its contents, it simply means
that the repository is publicly viewable. Private repositories are
accessible only to those who have been granted access.

#### Pushing to the remote repository

This step sends the details of any commits which have been made locally
to the specified remote repository, which can act as a backup of your
work or a resource to share with others.

### Making use of version control

Once you have a git version control workflow in place it can be useful
in a number of different ways.

#### Viewing your version history

The version history that you build up as you commit your work forms a
record of the changes that you’ve made to your code or documents. This
can help you to track a project’s development, understand reasons for
past coding decisions, highlight major revisions and identify where bugs
were introduced.

#### Returning to a previous commit

The real power of git will become clear when you need to return to a
previous point in your revision history, for example to recreate figures
for a paper or to run an analysis again. You can use the unique ID for a
commit to tell git to return your working directory to the state
captured by that commit. You can then work with your code as it was at
that point in time.

#### Using version control to collaborate

There are a few alternative models for collaborating when using
version control. If you use a distributed system such as git, each
individual collaborator works with their own repository and you need to
decide how to consolidate your work. A couple of possible workflows are:

1.  Everyone connects their local repository to the same remote
    repository and must coordinate their changes. Changes to the
    central repository should be integrated into a user’s local
    repository before they submit their own changes to the remote
    repository.

2.  Individual contributors create a copy or *fork* of the main
    repository and use this as their remote repository. They must send
    a request to the maintainer of the original repository to
    incorporate their changes into the repository. This model allows a
    formalised review process before changes are integrated and is
    often used in open source projects.

### Going further with version control

Git is a flexible and powerful toolkit that provides a wide range of
advanced features such as *branching*, *stashing* and *tagging*. These
topics are beyond the scope of this guide but there are many online
resources where you can read more about using these features in your
workflow.

---

### Resources

#### Tutorials

-   Guide to version control from BES Best Practice for Code Archiving
    workshop
    [https://github.com/BES2016Workshop/version-control](https://github.com/BES2016Workshop/version-control)

-   Git - the simple guide by Roger Dudler
    [*http://rogerdudler.github.io/git-guide/*](http://rogerdudler.github.io/git-guide/)

-   Software Carpentry guide to Version Control with Git
    [*http://swcarpentry.github.io/git-novice/*](http://swcarpentry.github.io/git-novice/)

-   Chacon, S. and Straub, B., 2014. *Pro git*. Apress.
    [*https://git-scm.com/book/en/v2*](https://git-scm.com/book/en/v2)

#### Cheatsheets and troubleshooting

-   Git reference/cheatsheets
    [*https://git-scm.com/docs*](https://git-scm.com/docs)

-   Oh shit git! [*http://ohshitgit.com/*](http://ohshitgit.com/)

#### Using git with RStudio

-   Using Version Control with RStudio
    [*https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN*](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)


---

### Git quick reference

<dl>
<dt><em>Add</em></dt><dd>the process of selecting a file for inclusion in version history</dd>
<dt><em>Branch</em></dt><dd>a separate set of changes to version history allowing users to work in parallel on the same files</dd>
<dt><em>Commit</em></dt><dd>a snapshot of changes to be added to version history</dd>
<dt><em>Commit message</em></dt><dd>user-specified description of the changes made in a commit</dd>
<dt><em>Conflict</em></dt><dd>a problem arising when changes from different sources cannot be combined automatically</dd>
<dt><em>Fork</em></dt><dd>a remote repository derived from another project which can be used for collaboration</dd>
<dt><em>Merge</em></dt><dd>combining changes which originate from different repositories or branches</dd>
<dt><em>Pull</em></dt><dd>an action which synchronises the local repository with remote changes</dd>
<dt><em>Push</em></dt><dd>an action which synchronises the remote repository with local changes</dd>
<dt><em>Remote</em></dt><dd>an external repository which can be synchronised with local changes</dd>
<dt><em>Repository</em></dt><dd>a directory containing the files under version control</dd>
<dt><em>Stage</em></dt><dd>the process of selecting a file for inclusion in version history</dd>
</dl>

---
