# Git Commands

```bash
$ git --version

$ git --help

$ git <sub_command> --help
```

<br>

```bash
$ git config --global user.name

$ git config --global user.email

$ git config --global --list # list all the global git configurations
$ git config -l # list all the git configurations

$ git config --global alias.<alias_name> "<cmd>"
# Eg:- git config --global alias.co "checkout" # create an alias for git checkout command
# git co <branch_name> # use the alias to checkout a branch

$ git config --global diff.tool <editor> # set any editor as default diff tool

$ git config --global merge.tool <editor> # set any editor as default merge tool

$ git config --global core.editor <editor> # set any editor as default
# Eg:- git config --global core.editor "code --wait"

$ git config --glabal branch.sort -committerdate # sort branches by committer date, latest commit first
```

<br>

```bash
$ git init # initialize local git repo, create an empty repo in current directory

$ git init <directory> # initialize local git repo, create an empty repo in specified directory

$ git init -b <branch_name> # initialize local git repo, create an empty repo with given branch
```

<br>

```bash
$ git status # check status of a working tree

$ git status -s # give short status of a working tree
```

<br>

```bash
$ git clone <url> # clone repo into a new directory

$ git clone <url> -b <branch_name> <path/to/directory> # clones a git repo from the address into the given directory and checkout's the given branch

$ git clone <url> -b <branch_name> --single-branch  # Clones only single branch
```

<br>

```bash
$ git add <file> # To add a single file toa staged area

$ git add . # To add everything at once to the staging area

$ git add -A/--all # To add everything at once to the staging area

$ git add --dry-run <file> # To check what files will be added to the staging area

$ git add --interactive # To interactively add files to the staging area, allows you to review changes before adding them to the staging area

$ git add --update # To add only the modified and deleted files to the staging area, but not the new untracked files

$ git add --patch # To interactively review changes in each file and decide which changes to add to the staging area, allows you to add only specific changes from a file to the staging area
```

<br>

```bash
$ git commit -m "<msg>" # saves snapshot of changes in git and clears staging area

$ git commit -am "<msg>" # shortcut, to commit changes without adding to staging area

$ git commit --amend # combine staged changes with the previous commit, or edit the previous commit message without changing its snapshot

$ git commit --amend -m "<msg"  # change msg of last commit

$ git commit --amend --no-edit # adding files to last commit / amends a commit without changing its commit message

$ git commit --amend --author='Author Name <email@address.com>'  # Amend the author of a commit

$ git commit --dry-run # Check what changes will be committed without actually committing them
```

<br>

```bash
$ git branch or git branch --list/--all # show all branches

$ git branch <branch> # Creating a new branch

$ git branch -d <branch> # Deleting a branch

$ git branch -m <oldname> <newname> # change name of branch

$ git branch --sort=-committerdate # sort branches by committer date, latest commit first

$ git checkout <branch> # Switching to <branch>

$ git checkout -b <branch> # creates a new branch and Switches to new branch

$ git checkout -d <branch> # delete a branch and switch to the branch you want to switch to

$ git checkout - # switch to the previous branch

$ git branch -a  # List all local and remote branches

$ git branch -r  # List all remote branches

$ git switch <branch> # switch to the specified branch

$ git switch -c <branch> # creates a new branch and switches to it
```

<br>

```bash
$ git log # list of commits / show history of commits

$ git log --oneline # list of commits in single line

$ git log --oneline --reverse # list of commits in single line in reverse order

$ git log --stat # show stats of commits

$ git log -n <n> # list of <n> commits

$ git log --decorate --stat # show stats of commits with the reference names of any commits that are shown

$ git log --graph --decorate --oneline # show commits in a graph format with the reference names of any commits that are shown, and the commit messages in a single line

$ git log --author="<author_name>" # list of commits by the given author

$ git log --since=<date> # list of commits since the given date

$ git log --until=<date> # list of commits until the given date

$ git log --grep="<pattern>" # list of commits with the given pattern in
their commit message

$ git reflog # show the history of HEAD, # more comprehensive than git log
```

<br>

```bash
$ git show <commit_hash> # show changes made in the given commit

$ git show <commit_hash>:<file> # show changes made in the given file in the given commit

$ git show HEAD # show changes made in the latest commit

$ git show HEAD~<no> # show changes made in the commit <no> commits ago

$ git show HEAD~<no>:<file> # show changes made in the given file in the commit <no> commits ago
```

<br>

```bash
$ git ls-tree <commit> # show the files in the given commit

$ git ls-tree HEAD  # show the files in the latest commit

$ git ls-tree HEAD~<no> # show the files in the commit <no> commits ago
```

<br>

```bash
$ git revert <commit_hash> # undo the given commit, but will create a new commit without deleting the older one, safer than git reset

$ git revert HEAD --no-edit # revert to the latest commit
```

<br>

```bash
$ git reset <file> # unstage file

$ git reset # unstage all files

$ git reset --hard # discards away all your uncommitted changes, hard reset files to HEAD

$ git reset <commit_hash> # reset our repository back to the specific commit

$ git reset HEAD~<no> # reset our repository back to the commit <no> commits ago

$ git reset --hard <commit_hash> # reset our repository back to the specific commit, discarding away all your uncommitted changes

$ git reset --hard HEAD~<no> # reset our repository back to the commit <no> commits ago, discarding away all your uncommitted changes

$ git reset --soft <commit_hash> # reset our repository back to the specific commit, keeping all your uncommitted changes

$ git reset --soft HEAD~1 # Undo the Last Commit but Keep Changes in the working directory and staging area, but the commit is removed from the history.

$ git reset HEAD~1 # Undo the Last Commit and Unstage Changes

$ git reset --hard HEAD # Undo the Last Commit and Discard Changes

$ git reset --mixed <commit_hash> # reset our repository back to the specific commit, keeping all your uncommitted changes in the working directory but not in the staging area
```

<br>

```bash
$ git rm <file> # removes <file> from the staging area as well as from directory

$ git rm --cached <file> # only removes <file> from git index(staging area)
```

<br>

```bash
$ git merge <branch> # merge the specified branch with current branch

$ git merge --abort # abort the merge

$ git merge --continue # continue the merge after resolving conflicts
```

<br>

```bash
$ git stash # stashes the staged and unstaged changes, clears staging area

$ git stash -u # stash everything including new untracked files

$ git stash create # creates a stash but does not save it, returns the stash reference

$ git stash save "<msg>" # stash with a msg to reference the stash later

$ git stash list # list all stashes

$ git stash push -m "<msg>" # stash with a msg

$ git stash pop # delete the recent stash and applies it

$ git stash pop stash@{2} # delete the {2} stash and applies it

$ git stash show # shows the description of stash

$ git stash apply # keep the stash and applies it to the git

$ git stash apply stash@{<number>}

$ git stash apply <name>

$ git stash branch my-branch stash@{1} # creates a branch from your stash

$ git stash drop stash@{1} # deletes the {1} stash

$ git stash clear  # clears all the stash
```

<br>

```bash
$ git diff # showing changes between staging area and working directory

$ git diff --staged # comparing changes between latest commit and staging area

$ git diff <branch1> <branch2> # comparing changes between two branches

$ git diff <branch1>..<branch2> # comparing changes between two branches

$ git diff <commit_hash1>..<commit_hash2> # comparing changes between two commits

$ git diff <commit_hash1> <commit_hash2> # comparing changes between two commits

$ git diff <commit_hash1> # comparing changes in working tree relative to the named <commit_hash>

$ git diff --cached <commit> # comparing changes in staging area relative to the named <commit>
```

<br>

```bash
# restore changes from the next environment

$ git restore <file_or_files>  # removes all the changes on the working dir # takes copy of changes from staging area and add it to the working dir

$ git restore --staged # restore all changes in staging area # takes copy of the file from last commit and add it to the staging area # unstage changes

$ git restore --staged <file_or_files> # restore changes in staging area # takes copy of the file from last commit and add it to the staging area # unstage changes

$ git restore <file_or_files> --source=<commit_hash> # restore the working dir by taking the copy of changes from the source

$ git restore <file_or_files> --source=HEAD~<no> # restore the working dir by taking the copy of changes from the source

$ git restore <file_or_files> --source=<branch> # restore the working dir by taking the copy of changes from the source
```

<br>

```bash
$ touch .gitignore # add files or folders to .gitignore you want git to ignore and not track
```

<br>

```bash
# To merge changes from main/master in feature branch

$ git rebase main/master # rebase feature branch on top of main/master

$ git rebase --abort # abort the rebase

$ git rebase --interactive main/master # interactively rebase feature branch on top of main/master, allows you to edit, reorder, squash commits during the rebase process
```

<br>

```bash
$ git rm --cached <file> # remove file from staging area

$ git rm --cached -r <folder> # remove folder from staging area
```

<br>

```bash
$ git remote -v

$ git remote add <remote_name> <url>

$ git push <remote_name> <branch> #  uploading your commits to the remote repository
# Eg:- git push origin main/master

$ git push <remote_name> <branch> --force # force push your commits to the remote repository, use with caution as it can overwrite changes in the remote repository

$ git remote rm <remote_name> # remove a remote
```

<br>

```bash
# git pull downloads the changes and merges them into your current branch.
$ git pull <repo> # get updates from the remote repo.  # git fetch + git merge

$ git pull --verbose <repo>

$ git pull --no-commit <repo>
```

<br>

```bash
# git fetch just "downloads" the changes from the remote to your local repository.
$ git fetch <remote> # fetch all of the branches from the repository, also downloads all of the required commits and files from the other repository.

$ git fetch <remote> <branch>

$ git fetch --all <remote>

$ git fetch --verbose  <remote>

$ git fetch --dry-run  <remote> # check what files will be fetched
```

<br>

```bash
$ git bisect start # start the bisect session

$ git bisect bad # mark the current commit as bad

$ git bisect good <commit_hash> # mark the given commit as good

$ git bisect reset # end the bisect session and return to the original HEAD

$ git bisect log # show the bisect log
```

<br>

```bash
$ git worktree list # list all the worktrees linked to the current repository

$ git worktree add <path> <branch> # creates a new worktree linked to the current repository at the specified path and checks out the specified branch in that worktree

$ git worktree remove <path> # removes the worktree at the specified path, but does not delete the branch associated with that worktree

$ git worktree prune # removes all the worktrees that have been removed but not pruned yet
```

<br>

```bash
$ git cherry-pick <commit_hash> # apply the changes introduced by the given commit on the current branch

```
