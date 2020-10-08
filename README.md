# daily-dev-cheatsheet
Aggregation of some cheatsheets I use on a daily basis

## Git

### Configure tooling
Configure user information for all local repositories

`$ git config --global user.name "[name]"`

Sets the name you want attached to your commit transactions

`$ git config --global user.email "[email address]"`

Sets the email you want attached to your commit transactions

`$ git config --global color.ui auto`

Enables helpful colorization of command line output

### Branches
Branches are an important part of working with Git. Any commits you make will be made on the branch you’re currently “checked out” to. Use git status to see which branch that is.

`$ git branch [branch-name]`

Creates a new branch

`$ git checkout [branch-name]`

Switches to the specified branch and updates the working directory

`$ git merge [branch]`

Combines the specified branch’s history into the current branch. This is usually done in pull requests, but is an important Git operation.

`$ git branch -d [branch-name]`

Deletes the specified branch

### Create repositories
When starting out with a new repository, you only need to do it once; either locally, then push to GitHub, or by cloning an existing repository.

`$ git init`

After using the git init command, link the local repository to an empty GitHub repository using the following command:

`$ git remote add origin [url]`

Turn an existing directory into a Git repository

$ git clone [url]

Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits

The .gitignore file
Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named .gitignore. You can find helpful templates for .gitignore files at github.com/github/gitignore.

## Synchronize changes
Synchronize your local repository with the remote repository on GitHub.com

`$ git fetch`

Downloads all history from the remote tracking branches

`$ git merge`

Combines remote tracking branches into current local branch

`$ git push`

Uploads all local branch commits to GitHub

`$ git pull`

Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. git pull is a combination of git fetch and git merge

## Make changes
Browse and inspect the evolution of project files

`$ git log`

Lists version history for the current branch

`$ git log --follow [file]`

Lists version history for a file, including renames

`$ git diff [first-branch]...[second-branch]`

Shows content differences between two branches

`$ git show [commit]`

Outputs metadata and content changes of the specified commit

`$ git add [file]`

Snapshots the file in preparation for versioning

`$ git commit -m "[descriptive message]"`

Records file snapshots permanently in version history

### Redo commits
Erase mistakes and craft replacement history

`$ git reset [commit]`

Undoes all commits after [commit], preserving changes locally

`$ git reset --hard [commit]`

Discards all history and changes back to the specified commit
