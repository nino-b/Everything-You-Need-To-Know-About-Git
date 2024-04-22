

1. ``` cat .git/refs/heads/main ```  Will display sha of branches. Branches exist in 'heads' foldes as SHAs. 
2. ```git cat-file -p <sha> ``` then we can see the tree.

- ```  >> ``` means add to the file at the end, do not overwrite it.


### Merging

1. git will first find the common parent (called: the 'best common ancestor' or 'merge base');
2. Plays commits on top of it.
3. Creates a new commit called a 'merge commit' and it will have two parents, from each branch that are being merged.

- <b>Target branch:</b> the branch we are on (not main).
- <b>Sorce branch:</b> the branch that we named (```<branchname>``` (main)).

```git merge <branch name>``` merge branches.

-  If best common ancestor (or merge base) has only one branch, we can have 'Fast Forward Merge'. Which means that we merge our branch to the tip of the main branch (best common ancestor).
- In this case we don't need merge commit. It automatically does everything necessary.



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




### Rebase

- It allows us to update underneath our set of changes.
- In some sence, we can think that it 'rewrites the history'.
- Allows us what is currently the reality and then our changes. So it allows us to check our code in new reality, instead of checking it in previous reality.
- We can do 'Fast Forward Merge' (commits are not necessary).

The basic steps of rebase:
1. Execute ```git rebase <target branch>```. We will refer to the current branch as ```<current branch>``` later on.
2. Checkout the last commit on ```<target branch>```.
3. Play one commit at a time from ```<current branch>``` (plays each commit on top of the last commit).
4. Once finished will update ```<current branch>``` to the current commit sha. (Once all commits are successfully applied on top, Git will update the current branch to point to the latest commit of the rebase, effectively moving the branch pointer).


```
   B----C (foo)
 
  /
A----D----E----X----Y   (main)


                      B----C (foo)
                     /
A----D----E----X----Y   (main)
````
d 
1. Execute git rebase main:
First, ensure you're on the foo branch:
git checkout foo
2. Then, execute the rebase command to rebase foo onto main:
git rebase main
3. Checkout the last commit on main:
Git will automatically rewind the foo branch to the commit where it diverged from main, which is commit A.
Then, Git will checkout the tip of the main branch, which is commit Y.
4. Play one commit at a time from foo:
Git will start applying each commit from foo (commits B and C) on top of commit Y in sequence.
Update foo branch to the current commit SHA:
Once all commits are successfully applied on top of main, Git will update the foo branch to point to the latest commit of the rebase, which is commit C.







main branch: main
target branch: bar

checkout latest commit on: bar
play one commit at a time from: main