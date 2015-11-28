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

**WAIT** what's a git repository?

Git turns your directory into a **repository** which tracks all of the changes you make to your project as you update and commit new changes.  In Git, you have a working directory, or staging area, where you edit files and different branches or versions of your project.  Git keeps track of changes from you and other users to make sure your work isn't lost and you can collaborate easily.

Okay, here are the essential commands:
- `git init` - creates a repository in the current directory 
- `git status` - prints the current branch, changes staged for commit, changes to be committed, any errors
- `git log` - shows all commits, use `spacebar` to move through and `q` to leave the logs
- `git add <file>` - adds files, directories and modifications to be committed, requires and argument
  - `git add .` - adds all changes
  - `git add index.html` - adds specific file
  - `git add css/` - adds directory with all files
- `git commit` - commits changes - in git changes have to be committed to be permanently added to a project, each commit marks a new update in the project - commits have identification numbers to be references for reverting, checking out etc.
  - `git commit -m "initial commit` - common way to commit, `-m` lets you add message describing changes in commit
- `git checkout <branch>` - checkout a different commit or branch
  - `git checkout -b new_feature` - creates a new branch and checks it out (opens it in working directory)
  - `git checkout master` - checkout master branch at HEAD (most recent commit)
  - `git checkout HEAD~2` - move back to earlier commit
  - `git checkout 874f93` - move to specific commit using first 6 digits in id number
- `git merge <branch>` - merges a branch with current branch
  - `git merge new_feature`
- `git revert <branch>` - undoes specific commit
  - `git revert 1839dj`
- `git rebase <branch>` - brings current branch up to date with specific branch
  - `git rebase master`

Most likely, if you're working on your own, you will only need `init`, `status`, `add` and `commit` from this set.

**Now make a github account.**

Keep track of the email you use, you will need to set it as your `user.email` to upload repos to your account.

Create a new repo and copy the address.  Should be something like `https://github.com/username/reponame.git`

**More git commands to add your local repo to the GitHub repo**

- `git remote add origin <server>` - this is how to add a remote repo to your project.  usually you will use origin as the name for the GitHub repo, but it could be anything.  Argument is the link we just copied.
  - `git remote add origin https://github.com/username/reponame.git`
- `git config` - configure your user settings.  May need to do this to get permissions set up to push to your repo, or not sometimes.  If you use `https://` to remote add or clone should be fine.
  - `git config -help` - see your config options.  in general `-help` after a command is very helpful.
  - `git config --global user.name "your name"` - Set your username.
  - `git config --global user.email <email>` - use same email as github account.
  - `git config --list` - Lists config keys, values.
- `git push origin master` - send your commits to the remote repo.  origin is the remote location, master is the branch.  you can commit multiple branches.
- `git pull` - get changes from remote repo.

If you are working on a project that already exists, you can `clone` to make a copy on your macine:

- `git clone https://github.com/username/reponame.git`

Don't make a folder with the name of the project to clone into because the clone operation will make a folder so then you'll just have two folders.  Start in the folder where you want the project folder to be.

With remote repos, commits and merges work the same, but only when you push the changes.  If you are collaborating with other developers, you will sometimes get a `merge conflict`, where one lines have been changed in both commits that are being merged, and git doesn't know which to use, which will look like this:

```
<<<<<<< HEAD
<p>Welcome to my website!</p>
=======
<p>Welcome to my butt!!!</p>
>>>>>>> new_feature
```

You then edit the file to get rid of the git stuff and the uneeded code, and create a new commit.


#Links
- [Set up git](https://help.github.com/articles/set-up-git/)
- [git simple guide](http://rogerdudler.github.io/git-guide/)
