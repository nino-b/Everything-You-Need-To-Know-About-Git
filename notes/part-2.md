

1. ``` cat .git/refs/heads/main ```  Will display sha of branches. Branches exist in 'heads' foldes as SHAs. 
2. ```git cat-file -p <sha> ``` then we can see the tree.

- ```  >> ``` means add to the file at the end, do not overwrite it.


### Merging

1. <b>Find the common parent:</b> Git identifies the <b>best common ancestor</b> or <b>merge base</b>, which is the last commit that both branches have in common before diverging.
2. Plays commits on top of it.
- Example:
```
   (B)---(C)---(D)
  /               
(A)              
  \               
   (E)---(F)---(G)

``` 
- Steps:
  1. Start with a common ancestor commit A.
  2. Changes from the B-C-D branch are applied on top of commit A, creating a new sequence of commits A-B-C-D.
  3. Changes from the E-F-G branch are applied on top of commit A, creating a new sequence of commits A-E-F-G.
  4. Finally, Git creates a merge commit that combines the changes from both branches, resulting in a new commit that has two parents: one from the A-B-C-D sequence and the other from the A-E-F-G sequence.
  5. So, the resulting commit history after the merge operation would indeed look like 'A-B-C-D-E-F-G', where all changes from both branches are integrated into a single branch.


3. Creates a new commit called a 'merge commit' and it will have two parents, from each branch that are being merged.

- <b>Target branch:</b> the branch we are on (not main).
- <b>Sorce branch:</b> the branch that we named (```<branchname>``` (main)).

```git merge <branch name>``` merge branches.

-  If best common ancestor (or merge base) has only one branch, we can have 'Fast Forward Merge'. Which means that we merge our branch to the tip of the main branch (best common ancestor).
- In this case we don't need merge commit. It automatically does everything necessary.



#### Solving merging problem (Merge Conflit) in our example

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
- Allows us to apply what is currently the reality and then our changes. So it allows us to check our code in new reality, instead of checking it in previous reality.
- We can do 'Fast Forward Merge' (commits are not necessary).

The basic steps of rebase:
1. Execute ```git rebase <target branch>```: This initiates the rebase process, where ```<target branch>``` is the branch we want to rebase onto. It's important to note that we can also rebase interactively using ```git rebase -i <target branch>``` to have more control over the rebase process, such as squashing commits or reordering them.
2. Checkout the last commit on ```<target branch>```: After initiating the rebase, Git will temporarily switch to the ```<target branch>```.
3. Play one commit at a time from ```<current branch>```: During the rebase process, Git will iterate through each commit on ```<current branch>```, one at a time, and apply them on top of the ```<target branch>```. If there are conflicts, Git will pause the rebase process, allowing us to resolve them manually.
4. Update ```<current branch>``` to the current commit SHA: Once all commits are successfully applied on top of ```<target branch>```, Git will update the ```<current branch>``` to point to the latest commit of the rebase. This effectively moves the branch pointer to the new commit, incorporating the changes from both branches.



#### Rebase Pros
- We can have a clean history with no merge commits. If we use ```git log``` this can help with searching.

#### Rebase Cons
- Alters branch history. If we already had e.g. 'foo' on a remote git (on another repo), we'd have two diferent branches named the same thing with different histories. We would have to <b>force</b> push it to the remote again.


#### Never Change History of a Public Branch!!

- Always Merge on public branches!!
- Rebase on Private branches.



### HEAD

- Use it only when we have to!

### Cherry pick

```git-cherry-pick``` - allows to take one or more commits specifically.
 

This is better than using ```git merge <deleted branch's sha>``to recover deleted file, because if we use merge, it starts merging from the best common ancestor. And if we have many different commits and branches that we don't need in this case, we still would get all those history. Cherry-pick helps us to get exactly what we need.

Cherry pick requires working tree and index (staging area) to be clean (no modifications from the HEAD commit).


### Remote Git

A remote is a copy of the repo in somewhere else (not necessarily on github).

It is another git repo that is of the same project and has changes we may need.

Usually named 'origin'.


### Gitism

There are two naming conventions:

#### Remote is project repo

Typically when we have a remote git repo, it is called <i>origin</i>. This is the source of truth repo.

#### Remote is our fork of some other repo

- Our remote repo (fork) is called <i>origin</i>.
- The project repo is named <i>upstream</i>.


### Fetch

We can fetch all the git state from out remote repo by executing ```git fetch```. This won't update the current branches checked out, just where the ```origin/*``` has set to.

Fetching keeps our local repo's remotes up to date, but it doesn't alter our state.


### Git pull

```git pull``` more convinient way (than fetch) to merge changes into out branch.

```git branch --set-upstream-to=origin/main main``` - set tracking information. ```origin/main``` this specification is important because we tell git which remote are we linking to.


When we want to checkout a remote branch that we fetched but we don't have it locally, we can use ```git switch -c <branch name> ```.

- ```git switch -c <branch name>``` creates a new local branch and checks it out based on the remote branch we specify.

### Advice about using Rebase

When we pull changes from the remote authority repo, we will rebase the changes (instead of many merge commits). Always move changes to the front with rebase and make a single commit.

- A long lived branch with many merge commits is dificult to revert.
- If every change is a single commit, then the ability to revert is very trivial.
- Test changes agains the current state of master, not current state of what we fetched.


### Git push

```git push``` take our changes and move to the remote repo. Like ```git pull```, if we are not 'tracking' then we can't push. We have to specify the remote branch name.