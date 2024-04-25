### Git Bisect

Git Bisect steps:
1. ```git bisect start```
2. ```git bisect bad ```
3. ```git bisect good <commit>```
4. test
5. ```git bisect <good | bad>```
6. go to 4 until git tells us the commit.


Our solution:
1. ```git bisect start ```
2. ```git log --oneline ```
3. ```git bisect good <sha> ```
4. ```git bisect bad ```
5. ```git bisect run ./node_modules/.bin/vitest --run ```


### Git Reset

#### Soft

Git reset soft can be very useful if we need to make a commit that is partially finished and we want to edit that commit and change the contents.

#### Hard

Hard will do the same as soft except it will drop changes to the index and worktree. That means any work that is being tracked by git will be destroyed.



### Worktree

- Main working tree is a tree which is created by ```git init```.
- A linked working tree is just another tree, but without all the git history within .git directory.