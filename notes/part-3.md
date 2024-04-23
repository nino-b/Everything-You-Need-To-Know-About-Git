### Stash

```git stash``` will tak every change traked by git (change to index + change to work tree) and store that result like a commit in the 'stash'.


Use git stash wen we want to record the current state o the working directory and the index, but want to go back to a clean working directory. The command saves our local modificaions away and reverts the working directory to match the HEAD commit.


We can think o 'stash' as a stack of temporary changes.

- ```git stash -m <message>``` push our chanes into the stack.
- ```git stash list``` list stashes.
- ```git stash show [--index <index>]```show chanes /diff.
- ```git stash pop```pop the latest stash.
- ```git stash pop --index <index>```pop a stash at an index


### Interactive Rebasing and Squashing

Take many commits and turn it into one commit.


### Conflicts

Often it is not obvious what is in conflict just by the message (if there is a large set of changes). 

So a simple way to see what is conflicted is by checking out the status.

- ```git merge --abort``` we can abort the merge due to the conflict.


#### git push problem

If we are on the 'main' and we are trying to push changes on 'main' it won't work (if it worked, this means that anybody can change code that we are currently working on underneath us).

To solve this problem just checkout on another branch and oush it from there.



### Worktrees

Worktree is another copy of our repo without all the weight of our repo. They are more lightweight.