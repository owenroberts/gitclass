#Quick Introduction to Git and GitHub
- [Git](https://git-scm.com/): free, open source version control system
  - effecient for collaboration, sharing code, forking projects
- [GitHub](https://github.com/): hosting, social network for git repositories
  - good way to organize projects
  - public place for code, like resume
  - comment, add issues, fork, request access, etc.

##Getting Started

OSX: Open Terminal Application [OSX Command Line Reference](http://ss64.com/osx/)

Windows: Command Prompt (maybe?  i don't know... )

**Basic Unix Commands**

- `cd` - change directory - `cd Desktop/`
- `cd ..` - back to parent directory
- `ls` - list contents of directory
- `mkdir` - create a directory - `mkdir project_folder`
- `touch` - create a file - `touch index.html`
- `rm` - remove file or directory - **no undo!** - it's not going to the trash can

**Essential Git Commands**

First make sure you have git: `git --version` should print something.  If not, [download git](https://git-scm.com/downloads).

Then, move to the directory in which you want to create a git repository.

**Wait** what's a git repository?

Git turns your directory into a **repository** which tracks all of the changes you make to your project as you update and commit new changes.  In Git, you have a working directory, or staging area, where you edit files and different branches or versions of your project.  Git keeps track of changes from you and other users to make sure your work isn't lost and you can collaborate easily.

Okay, here are the essential commands:
- `git init` - creates a repository in the current directory 
- `git status` - prints the current branch, changes staged for commit, changes to be committed, any errors
- `git log` - shows all commits, use `spacebar` to move through and `q` to leave the logs
- `git add` - adds files, directories and modifications to be committed, requires and argument
  - `git add .` - adds all changes
  - `git add index.html` - adds specific file
  - `git add css/` - adds directory with all files
- `git commit` - commits changes - in git changes have to be committed to be permanently added to a project, each commit marks a new update in the project - commits have identification numbers to be references for reverting, checking out etc.
  - `git commit -m "initial commit` - common way to commit, `-m` lets you add message describing changes in commit
- `git checkout` - checkout a different commit or branch
  - `git checkout -b newfeature` - creates a new branch and checks it out (opens it in working directory)
  - `git checkout master` - checkout master branch at HEAD (most recent commit)
  - `git checkout HEAD~2` - move back to earlier commit
  - `git checkout 874f93` - move to specific commit using first 6 digits in id number
- `git merge` - merges a branch with current branch
  - `git merge newfeature`
- `git revert` - undoes specific commit
  - `git revert 1839dj`
- `git rebase` - brings current branch up to date with specific branch
  - `git rebase master`

Most likely, if you're working on your own, you will only need `init`, `status`, `add` and `commit` from this set.
