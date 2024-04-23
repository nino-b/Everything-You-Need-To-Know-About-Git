|              Command                     | Explanation |
|------------------------------------------|-------------|
|```git branch -M <name>```                | Rename the current branch |
|```git.add <path to file> ```             | It will add zero or more files to the staging area (index). |
|```git commit -m <message> ```            | Will commit the changes that are in the staging area. It will take staged files in the index (staging area) and will turn it into a commit (with author name, time, the contents of the change). It will produce SHA ( Secure Hashing Algorithm) |
|```git status ```                         | Will describe the state of your git repo, which includes tracked, stage and untracked changes. |
|```git log ```                            | Will show history of commits (in my case it showed in the browser). |
|```git cat-file -p <some sha> ```         | Will print out any sha we want. It will echo out the contents of the sha. We can inspect any commit or anything else.                      |
|```mkdir <directory name> ```             | Create a directory |
|```touch <file name> ```                  | create a file |
|```vim <file name> ```                    | Open file in vim |
|```git branch <branch name> ```           | Creates a new branch. But it does not swotch branches! |
|```git branch ```                         | Check what branches do we have |
|``` cat .git/refs/heads/main ```          | Will display sha of branches |
|```git switch <branch name> ```           | Switch branches |
|```git checkout <branch name> ```         | Switch branches |
|```git checkout -b<branch name> ```       | Create new branch |
|```git log --graph --oneline ```          | Displays everything more concise way |
|```git merge <branch name>```             | Merge branches |
|```git reflog ```                         | History of HEAD and other references, such as commits and merges |
|```git reset --hard HEAD~2 ```            | Reset current branch's head to two commits prior to the current one, and it also resets the working directory and the index to match the state/ |
|```git log --oneline --parents ```        | Displays parents |
|```git reflog ```                         | Shows where head has been |
|```git reflog -4 ```                      | We will see only 4 lines of reflog |
|```cat .git/logs/HEAD \| tail -3 ```      | We will see last 3 logs (remember: last line of result of ```git reflog``` is the first line of this command's result)                     |
|```git cat-file -p <sha> <new file's name where we want to recover deleted information> ``` | Recover deleted file |
|```git diff --staged ```                  | Shows changes that are staged for the next commit |
|```git cherry-pick <sha> ```              | Allows to take one or more commits specifically |
|```git remote add <name> <uri> ```        | Add a remote |
|```git remote -v ```                      | View the list repositories associated to out local git repository along with their URLs. |
|```git fetch ```                          | Fetch all the git state from out remote repo |
|```git branch -a ```                      | See all branches |
|```git pull <remote> <branch name> ```    | Merge changes in our branch. |
|```git branch --set-upstream-to=origin/main main ``` | Set tracking information. Tell git which remote are we linking to. |
|```git switch -c <branch name> ```        | Creates new local branch and checks it out based on the remote branch we specify. |
|```git pull --rebase ```                  | Locally Rebase when pull |
|```git push <remote> <local name>:<remote name> ``` | Allows us to push and have it recieved with a different name. |
|```git push <remote> :<remote name> ```   | Will delete a branch on the remote. |
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
|``` ``` |  |
|``` ``` |  |
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
|```git config --add<section>.<keyname> <value> ``` | Adds a key to our git config |
|```git config --list \| grep <section> ```         | List out everything with specific section. It will print out local first (does not matter if global was added later). |
|```git config --get-regexp <regex> ```             | List out everything that matches specific regex. |
|```git config --get <section>.<key> ```            | Will return last added value.  |
|```git config --get-all  ```                       | Return all values. |
|```git config --unset <section>.<key> ```          | Unset values (if there are multiple keys, we should use --unset-all. We can't unset just one of many). |
|```cat .git/config ```                             |  |
|```git config --remove-section <section name> ```  | Remove whole section. |



|   Commands: Config   |   Explanation   |
|----------------------|-----------------|



|   Commands: Config   |   Explanation   |
|----------------------|-----------------|



|   Commands: Config   |   Explanation   |
|----------------------|-----------------|


|   Commands: Config   |   Explanation   |
|----------------------|-----------------|






|              Command              | Explanation |
|-----------------------------------|-------------|
|```-d ``` | Delete branch |
|```-D ``` | Delete branch |
|```-S ``` | Search commit change |
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
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |