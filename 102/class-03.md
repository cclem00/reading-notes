# Git intro

## Prerequisites 
- Have some knowledge of Terminal if using Mac and Command Line if using Windows or Linux

## Version control
- System that allows someone to revisit various versions of a file that has been created or a set of files by activly recording every change that happens to that file.
- Useful for correcting mistakes

## Centralized Version Control 
- One server that stores all information including each and every modification to every file on that server
- Can be accessed by various clients for collaboration

## Distributed Version Control 
- Solves the biggest potential threat for the centralized version control
- Because CVS is a single server if it goes down collaborators cannot work together or save any changes made to those files.
- the DVCS allows for clients to copy mirrored repositories so if anything does happen such as catastrophic loss these files can be replaces.
- really good for collaboration 

## What is Git
- When a project is modified and saved its called **commit**
- Git then creates a snapshot of that file and stores a reference to it.
- Depending if the file was modified or not Git will store a reference to the identical version of that file

## Local Operations 
- Works from locally stored data 
- Faster processing
- No need to fetch data 

# Tracking changes
- Every edit or modification to a file or directory is tracked by Git
- Git always detects file corruption or loss of information in transit 

## Loss of Data 
- Git makes it difficult for a snapshot of a file that is **committed** to be lost

## States 
- Three main states
- Committed, modified, and staged

## Modified
- The file has been editeed or changed but not committedd to the database 

## History of Git
- Created in 2005 by Linus Torvalds
- He was the chief architect of linux Kernel
- Allowed non-linear development via multiple branches, could support large projects, had fast processing, prevented corruption and was simple in design

## Thing I want to know more of
- How does Git find damaged files
- How many years it took to get to the point its at now
- If there will be something that replaces Git

### The following is step by guide on how to insall it.
Getting Started
Download Git
In order to use Git, your computer must have it available. If you already have Git on your computer, you should make sure you have the latest version.
Git can be installed in three ways:
1. Install as a package
2. Install via another installer
3. Download and compile the source code.
Mac OS X
Terminal
The simplest method for installing Git on a Mac (for Mavericks 10.9 and above) is running Git from the Terminal. If Git is not installed, you will see a prompt for installation.
Git Website
You can also download Git by visiting this link and following the posted directions:
http://git-scm.com/download/mac
GitHub
A third option is to install Git as part of the GitHub for Mac install. GitHub is repository hosting service, which we will discuss in a future section.
Download GitHub for Mac via the following link:
http://mac.github.com
Windows
Git Website
You can download Git by visiting this link and following the posted directions:
http://git-scm.com/download/win
GitHub
Install Git as part of the GitHub for Windows install.
http://windows.github.com
Linux
Package Manager
You can try installing Git via your distribution’s inherent package management tool.
For Fedora:
$ sudo yum install git
For Ubuntu:
$ sudo apt-get install git
Git Website
To download Git for Linux, visit this link and follow the posted directions:
http://git-scm.com/download/linux
Graphical Clients
Git includes inherent Graphical User Interface (GUI) tools. However, users can also utilize third-party tools created for particular platforms.
GUI Clients
You can access a variety of GUI clients for Mac, Windows, and Linux via the following link:
https://git-scm.com/downloads/guis
Initial Customization
After making sure Git has been installed, you should perform some customization steps, which should only need to be completed once on any machine. To change settings, you can repeat these steps.
Configuration of Variables
An inherent Git tool called git config allows the setting of configuration variables that control aspects of Git’s operation and look.
Identity Setting
After installing Git, users should immediately set the user name and email address, which will be used for every Git commit.
Type the following into Terminal or Command Line:
git config --global user.name "Jane Smith"

git config --global user.email "example@email.com"
To confirm that you have the correct settings, enter the following command:
git config --global user.name (should return Jane Smith)

git config --global user.email (should return example@email.com)
*By using the –global option, these Git settings apply to anything on the system. To use different identity settings for a specific project, change the working directory to the desired local Git repository and repeat the steps above without using –global.
Default Text Editor
Without configuration of a default text editor, Git will use the system’s default editor–most likely Vim. To configure a different text editor, such as Emacs, type the following into your Terminal or Command Line:
$ git config --global core.editor emacs
Note: For some editors, you may need to find specific instructions for default configuration.
Check Settings
To check settings, use the git config --list command.
Example:
$ git config --list

user.name=Jane Smith

user.email=example@email.com

color.status=auto

color.branch=auto

color.interactive=auto

...
Getting Help
There are three ways to get more information on a particular command, by accessing the manual:
git help command

git command --help

man git-command
Setting up a Git Repository
Importing
To import an existing project or directory into Git, follow these steps using the Terminal or Command Line:
1. Switch to the target project’s directoryExample:$ cd test (cd = change directory)
2. Use the git init command$ git initNote: At this stage, you have created a new subdirectory named .git that has the repository files. Tracking has not commenced.
3. To start tracking these repository files, perform an initial commit by typing the following:$ git add *.c$ git add LICENSE$ git commit -m “any message here”
Now, your files are tracked and there’s an initial commit. We will discuss the particular commands in detail soon.
Cloning
You can also create a copy of an existing Git repository from a particular server by using the clone command with a repository’s URL:
$ git clone https://github.com/test
By cloning the file, you have copied all versions of all files for a project. This command leads to the creation of a directory called “test,” with an initialized .git directory inside it, which has copies of all versions of all files for the specified project. The command also automatically checks out — or retrieves for editing — a copy of the newest version of the project.
To clone a repository into a directory with another name of your choosing, use the following command format:
$ git clone https://github.com/test mydirectory
The command above makes a copy of the target repository in a directory named “mydirectory.”
Workflow
Local Repository Structure
The local Git repository has three components:
1. Working Directory: The actual files reside here.
2. Index: The area used for staging
3. Head: Points to the most recent commit

Saving Changes
All files in a checked out (or working) copy of a project file are either in a tracked or untracked state.
Tracked
Tracked files can be modified, unmodified, or staged; they were part of the most recent file snapshot.
Untracked
Untracked files were not in the last snapshot and do not currently reside in the staging area.
*After cloning a repository, files have tracked status and are unmodified because they have been checked out but not edited.
The Life Cycle of File Status
1. After you edit a file, Git flags it as modified because of changes made after the previous commit.
2. You stage the modified file.
3. Then, you commit staged changes.

Check File Status
To determine the state of files, utilize the git status command:
$ git status
On branch master
nothing to commit, working directory clean
*This information indicates which branch you’re on (we will cover branches in a later section) and states “working directory clean,” which means that files have tracked or modified status at the moment. Also, no untracked files are present because Git has not listed any.
Tracking and Staging a New File
Single File
Track one file only by using the following format:
git add filename
All Files
Track all files in a repository by using the following command:
$ git add *
*After using these commands, files are tracked and staged for committing.
After adding a new file called EXAMPLE, you would see information regarding changes to be committed when using the git status command:
$ git status

On branch master

Changes to be committed:

  (use "git reset HEAD ..." to unstage)
new file: EXAMPLE
This information tells us that there are changes to be committed and that the file has been staged.
Committing a File
After staging one or multiple files, you should commit the changes and record what you did within the commit message:
$ git commit -m “made change x,y,z”
*This step has committed changes for the file or files (you can have one commit message for multiple files, if applicable) to the HEAD.
Committing All Changes
$ git commit -a
*This command commits a snapshot of all modifications to tracked files in the working directory.
Pushing Changes
Next, you would push changes to a remote repository. We will discuss remote repositories in more depth in the next section. For now, we will look at a general overview of pushing changes to remotes.
Example:
$ git push origin master
*This command pushes changes from the local “master” branch to the remote repository named “origin”.
*For cloned repositories, Git will automatically give the name “origin” to the server from which you cloned and the name “master” to your local repository. However, these names can be changed by the user.
Stashing Changes
When you are not ready to commit changes but do not want to lose them either, git stash is a great option. This command temporarily removes changes and hides them, giving you a clean working directory. When you are ready to continue working on the changes, simply use the git stash apply command to retrieve the hidden changes.
Remote Repositories
In order to collaborate on Git projects, you must interact with remote repositories, versions of a project residing online or on a network. You can work with multiple repositories, for which you can have read/write or read-only privileges. Teams can use remote repositories to push information to and pull data from.
Cloned Repositories
As mentioned earlier, for cloned repositories, Git will automatically give the name “origin” to the server from which you cloned and the name “master” to your local branch.
Seeing Your Remotes
By running the git remote command, you can view the short names, such as “origin,” of all specified remote handles.
By using git remote -v, you can view all the remote URLs next to their corresponding short names.