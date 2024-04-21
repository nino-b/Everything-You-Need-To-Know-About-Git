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