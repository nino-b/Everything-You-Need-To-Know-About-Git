

1. ``` cat .git/refs/heads/main ```  Will display sha of branches. Branches exist in 'heads' foldes as SHAs. 
2. ```git cat-file -p <sha> ``` then we can see the tree.

- ```  >> ``` means add to the file at the end, do not overwrite it.


### Merging

1. git will gind first in common parent (called: the best common ancestor);
2. git merges the sets of commits onto the merge base and creates a new commit at the tip of the branch that is being merged on with the canges combined into one commit.

- <b>Target branch:</b> the branch we are on (not main).
- <b>Sorce branch:</b> the branch that we named (```<branchname>``` (main)).

```git merge <branch name>``` merge branches.


#### Solving merging problem (Merge Conflit)

1. ```git branch -D foo``` Delete branch.
1. ```git checkout main``` tried to switch branches but got an error:
```
error: you need to resolve your current index first
README.md: needs merge
```
3. ```git merge --abort``` Stop merging.
4. ```git checkout main``` Switch branches.
5. ```git branch -D main-merge-foo``` Delete branche.
6. ```git checkout HEAD~2```Walk back 2 commits.
7. ```git checkout -b foo``` Create new branch and switch.