- All git config keys are in the following shape: ```<section>.<key>```
- ```--global``` flag will ensure we set this key value for all future users of git and repos
- ```user.name``` and ```user.email``` are the key's used in creating a commit tied to us
- To add a key value, execute ```git config --add --global <key> "<value>"```
We can view any value of git config by executing ```git config --get <key>```


#### ```git init```

We use it to initialize our project. It will add ```.git``` folder inside the directory.

#### ```.git``` folder

Every single repo comes with ```.git``` folder. And this is where all the data structures are kept. 

All of git's history is in this ```.git``` folder. If you delete it, repo won't exist any more.

When printing anything out to a file, add ```--decorate```, e.g. list out all named commits:
```git log --graph --decorate > out```

#### SHA

git commits come with SHA (Secure Hashing Algorithm) - a 40 character hash with 0-9a-f characters.

We can specify the first 7 characters of a SHA for git to identify what we are referring to.

Commits that exist in .git/objcts directory with the first 2 letters as a directory, adn remaining 38 as a file.

If we try to cat out the commit file, we see nothing useful.

1. ```git log --graph --decorate``` : find sha.
2. ```git cat-file -p <sha>``` : inspect contents of this sha.
3. One of its components is 'tree'. Grab its sha and write same command with this new sha to actually inspect the contents. If you want to inspect specific file's contents, repeat the process.


#### Terms

- tree: directory.
- blob: file.


#### Make changes in the file

1. ```vim <file name>```: Open file in 'vim'.
2. ```i```: Press i to enter insert mode, and then start typing your content.
3. ```Esc```: Press Esc to exit insert mode when you've finished typing.
4. ```:wq```: Save the changes and exit vim by typing: ```:wq```.


#### Listing out values

- ```--list``` : where it will list out the entirety of the config.
- ```--get-regexp <regex>``` : takes a pattern and looks for all names matching.

#### We might accidentally add the same keys multiple times to the git config. And when we look for them, we will have multiple keys as a result.


```--unset``` and ```--unset-all``` unsets values (if there are multiple keys, we should use --unset-all. We can't unset just one of many).


#### config is just a folder (```git config```)

```--get``` will return local even if global was added later.