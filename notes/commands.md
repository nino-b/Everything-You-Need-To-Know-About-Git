|              Command                     | Explanation |
|------------------------------------------|-------------|
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |





|   Commands: Global Configuration                  |   Explanation                               |
|---------------------------------------------------|---------------------------------------------|
|```git config --global init.defaultBranch<name>``` | Sets the default branch name globally (I use 'main' instead of 'master') |
|```git config --add --global pull.rebase true ```  | Always use rebase instead of merge when pulling changes from a remote repo. |





|   Commands: Configuration Management   |   Explanation   |
|----------------------------------------|-----------------|
|```git config --add<section>.<keyname> <value> ``` | Adds or updates a config key in the special section of the git config. |
|```git config --list \| grep <section> ```         | Lists all configuration settings mathing the specified section using ```grep```. ```--list``` option displays both local and global config settings (at first it always displays local settings, even if global was the last one added). |
|```git config --get-regexp <regex> ```             | List out all config settings that match specific regex. |
|```git config --get <section>.<key> ```            | Returns the value of specified config key in the specified section of Git config. It will return last added value.  |
|```git config --get-all  ```                       | Returns all values associated with a config key. Useful for keys with multiple values. |
|```git config --unset <section>.<key> ```          | Unset values (if there are multiple keys, we should use --unset-all. We can't unset just one of many). Removes the specified config key from the specified section of Git config. |
|```git config --unset --all <section>.<key> ```          | Removes all values associated with the specified key in the specified section. Used if  key we want to remove has multiple values and we want to remove all of them. If key has multiple values we can't remove just one, we have to remove all!  |
|```cat .git/config ```                             | Displays contents of entire git config. |
|```git config --remove-section <section name> ```  | Removes entire specified section from git config. |




|   Commands: Branching and switching   |   Explanation   |
|---------------------------------------|-----------------|
|```git branch -M <name>```                | Rename the current branch to `<name>` |
|```git branch <branch name> ```           | Create a new branch named `<branch name>`. It does not switch branches! |
|```git branch ```                         | List all local branches. |
|```git switch <branch name> ```           | Switch to an existing branch named `<branch name>`. |
|```git checkout <branch name> ```         | Switch to an existing branch named `<branch name>`. |
|```git checkout -b <branch name> ```       | Create a new branch named `<branch name>` and switch to it. |
|```git branch -a ```                      | List all local and remote branches. |
|```git branch --set-upstream-to=origin/<branch name> main ``` | Set the upstream tracking information for the current branch to `origin/<branch name>`. Tell git which remote are we linking to. |
|```git switch -c <branch name> ```        | Create a new local branch based on the specified remote branch and switch to it. |




|   Commands: Status and History   |   Explanation   |
|----------------------------------|-----------------|
|```git status ```                         | Describes the state of our git repo, which includes tracked, staged and untracked changes. |
|```git log ```                            | Shows the history of commits in reverse chronological order. |
|```git log --graph --oneline ```          | Displays the commit history in a concise format with a graphical representation of branches and merges. |
|```git log --oneline --parents ```        | Displays each commit on a single line with its parent commits. |
|```git reflog ```                         | Shows where head has been |
|```git reflog ```                         | Shows the history of `HEAD` and other references, such as commits and merges. |
|```git reflog -<number> ```                      | Limits the output to the last e.g. 4 entries in the reflog. |
|``` cat .git/refs/heads/<branch name> ```          | Displays the SHA of the latest commit on the specified branch. |
|```cat .git/logs/HEAD \| tail -<number> ```      | Displays the last e.g. 3 entries in the reflog for the `HEAD` reference. (remember: last line of result of ```git reflog``` is the first line of this command's result)                     |
|```git cat-file -p <some sha> ```         | Prints the contents of the specified git object, such as a commit or a file.                      |
|```git cat-file -p <sha> <new file's name where we want to recover deleted information> ``` | Recovers deleted file |




|   Commands: Staging and Committing   |   Explanation   |
|--------------------------------------|-----------------|
|```git.add <path to file> ```             | It will add zero or more files to the staging area (index). |
|```git commit -m <message> ```            | Commits the changes that are in the staging area, creating a new commit with the specified commit message. The commit includes author information, timestamp, and the contents of the changes. It produces a SHA (Secure Hashing Algorithm) identifier. |
|```git diff --staged ```                  | Shows the differences between the files in the staging area and the last committed version of those files. |




|   Commands: Merging and Cherry-Picking   |   Explanation   |
|------------------------------------------|-----------------|
|```git merge <branch name>```             | Merges the changes from the specified branch (`<branch name>`) into the current branch, incorporating the branch's history into the current branch's history. |
| ```git merge --abort ``` | Abort the merge due to conflict. |
|```git cherry-pick <sha> ```              | Applies the changes introduced by the specified commit (`<sha>`) onto the current branch. It effectively picks the specified commit and applies it on top of the current branch's commit history. |




|   Commands: Remote Operations   |   Explanation   |
|---------------------------------|-----------------|
|```git remote add <name of the origin> <uri> ```        | Add a named remote repo with the specified URI to the local Git repo. Name is usually 'origin'. |
|```git remote -v ```                      | List the names and URLs of all remote repositories associated with the local Git repo. |
|```git fetch ```                          | Retrieve the latest changes from the remote repository without merging them into the current branch. |
|```git pull <remote> <branch name> ```    | Fetch the latest changes from the specified remote repository and merge them into the current branch. |
|```git pull --rebase ```                  | Fetch the latest changes from the remote repository and rebase the current branch onto the fetched changes instead of merging them. |
|```git push <remote> <local name>:<remote name> ``` | Push the specified local branch to the remote repository with a different name. |
|```git push <remote> :<remote name> ```   | Delete the specified branch from the remote repository. |




|   Commands: File System Operations   |   Explanation   |
|--------------------------------------|-----------------|
|```mkdir <directory name> ```         | Create a new directory with the specified name. |
|```touch <file name> ```              | Create a new empty file with the specified name. |
|```vim <file name> ```                | Open the specified file in the Vim text editor for editing. |
|```cat ```                            | Display the contents of the specified file. |




|   Commands: Miscellaneous   |   Explanation   |
|-----------------------------|-----------------
|```git reset --hard HEAD~2 ```            | Reset current branch's HEAD to two commits prior to the current one. It also resets the working directory and the index to match the state of the specified commit. The `--hard` flag indicates that both the working directory and the index will be forcefully updated to reflect the state of the specified commit, potentially discarding any changes in the working directory and the index. |
|```git revert <sha> ``` | Creates a new commit that undoes the changes introduced by a previous commit. Useful if we want to undo efects of a particular commit without removing it from the project history. |






|              Command              | Explanation |
|-----------------------------------|-------------|
|```-d ``` | Delete branch |
|```-D ``` | Delete branch |
|```-S ``` | Search commit change |
|```git stash -m <message> ``` | add in the stash |
|```git stash list ``` | list out stash |
|```git stash show [--index <index> ] ``` | show diff/ changes (0 based) |
|```git stash pop ``` | pop the stash |
|```git stash pop [--index <index> ] ``` | pop the stash at an index |
|```git reset HEAD <file name> ``` | remove file from staging area |
|```git reset --soft HEAD~1 ``` | Reset current branch to the commit before the latest commit (HEAD~1) |
|```git log -S <string> ``` | Search the commit history for changes that introduced or removed instances o a specific string. |
|```git merge --squash <branch name> ``` |  |
|```git config --list --local ``` | Local configuration list. |
|```git checkout --ours <path to the file> ``` |  |
|```git checkout --theirs <path to the file> ``` |  |
|```git rebase -i <commitish> ``` |  |
|```git rebase -i HEAD~3``` |  |
|```git log --grep foo -p``` |  |
|``` git log -p -- src/index.js ``` |  |
|```git bisect run <cmd> ``` |  |
|```git revert <commitish> ``` |  |
|```git reset ``` |  |
|```git commit --amend ``` |  |
|```git worktree list ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |