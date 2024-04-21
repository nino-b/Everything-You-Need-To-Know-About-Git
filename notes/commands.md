|              Command              | Explanation |
|-----------------------------------|-------------|
|```git config --global init.defaultBranch<name>``` | Change the name of defailt branch Globally. |
|```git branch -M <name>``` | Rename the current branch |
|```git.add <path to file> ``` | It will add zero or more files to the staging area (index). |
|```git commit -m <message> ``` | Will commit the changes that are in the staging area. It will take staged files in the index (staging area) and will turn it into a commit (with author name, time, the contents of the change). It will produce SHA ( Secure Hashing Algorithm) |
|```git status ``` | Will describe the state of your git repo, which includes tracked, stage and untracked changes. |
|```git log ``` | Will show history of commits (in my case it showed in the browser). |
|```git cat-file -p <some sha> ``` | Will print out any sha we want. It will echo out the contents of the sha. We can inspect any commit or anything else. |
|```mkdir <directory name> ``` | Create a directory |
|```touch <file name> ``` | create a file |
|```vim <file name> ``` | Open file in vim |
|```git config --add<section>.<keyname> <value> ``` | Adds a key to our git config |
|```git config --list \| grep <section> ``` | List out everything with specific section. It will print out local first (does not matter if global was added later). |
|```git config --get-regexp <regex> ``` | List out everything that matches specific regex. |
|```git config --get <section>.<key> ``` | Will return last added value.  |
|```git config --get-all  ``` | Return all values. |
|```git config --unset <section>.<key> ``` | Unset values (if there are multiple keys, we should use --unset-all. We can't unset just one of many). |
|```cat .git/config ``` |  |
|```git config --remove-section <section name> ``` | Remove whole section. |
|```git branch <branch name> ``` | Creates a new branch. But it does not swotch branches! |
|```git branch ``` | Check what branches do we have |
|``` cat .git/refs/heads/main ``` | Will display sha of branches |
|```git switch <branch name> ``` | Switch branches |
|```git checkout <branch name> ``` | Switch branches |
|```git checkout -b<branch name> ``` | Create new branch |
|```git log --graph --oneline ``` | Displays everything more concise way |
|```git merge <branch name>``` | Merge branches |
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
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |
|``` ``` |  |









|              Command              | Explanation |
|-----------------------------------|-------------|
|```-d ``` | Delete branch |
|```-D ``` | Delete branch |
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
|``` ``` |  |