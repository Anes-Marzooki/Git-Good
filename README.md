# Git-Good
Git is an essential tool for every developer. It can be daunting at first for the beginners :dizzy:, so practicing it is a top priority.

In this document, you'll find the essential commands to help you out when working on your sprints.

Think of it as a cheat sheet :ledger:, grab this readme or open it in a new tab while hacking.

I encourage you to fork this repo, and to use it as a practice dummy.
<br>
## Bootstrap And Configuration :rocket:
Before you do anything, you need to configure the User imformation for you local work.
- **setting the user name**
```
git config --global user.name "name"
```
- **setting the user email**
```
git config --global user.email "email"
```
## Working With A Repository

Much of the times you'll be working with an existing repository that you need to fork and download locally on your machine.
```
git clone "link"
```
This will download a "copy" form the existing repository to your machine, with all of its files, commits and branches.
> If you wish to create your own repository, use [ git init ] to make your local directory a git repo ready to be pushed to github :sparkles:

>by default the name of the remote will be `origin` if not specified.

- **Pull && Push** :point_down: :point_up:

This part deals with synching the remote repository with you local one.

Say that you've successfuly clone a repo from github, and you've been working on it hard just to realise that the owner of the repo just made an update and/or added a new file to the repo :angry:. 

Should you Fork and Clone again ? No !

If you've cloned the repo onto your machine, runnig `git remote -v` will give you the name and the *link* of the original repo from where you cloned. Nice eyh ?

So all you need to do is to run the `pull` command.

A typical example of this is what follows:
```
git remote -v
origin https://github.com/orginization/exercice01.git

```
To update your local repo with the changes made in the remote one you just run:
```
git pull origin master
```
> Notice that we used `origin master` to specify the remote and the branch from wich we need the updates.

- **Push** :airplane:

Alright, you finished your work you save everything and now you need to show the world what good of a job you did.

Comes in the `push` command, running it will upload all of your commits and branches to Github, preferably your own account.

So first make sure you have the link of the desired repo you want to upload to :
```
git remote -v
origin https://github.com/orginization/exercice01.git
myremote https://github.com/myname/exercice01.git
```
I want to upload to the remote named " myremote ", so :
```
git push myremote master
```
I push all of my work now to the `myremote` remote in the `master` branch.

## Making Changes

- **Get Ready For The Stage** :nail_care: :lipstick:

```
git add [file-name]
```
The above command will prepare your file to be staged. It's like saving the **changes** you've made in your file **NOT** the file itself. The command `git add` graps a *snapshot* of the file :camera:.
``` 
git add file-one
git add file -two
...
```
To snapshot all the changes you've made on all the files in the current directory, use the `.` argument instead.

Just use `git add .` instead of adding your files one by one manually.

Now your changes are ready for the next stage.

- **Commitment** :ring:

Alright, now repeat this mantra at least twice a day:

> git, is a version-control system and Github is the platform for hosting git repositories.

The `commit` command works on the snapshots taking by the `add` command.
```
git commit -m "meaningfull message describing the changes"
```
This command will save your *staged* changes.

Here if you run `git status`, it's going to tell you that your working directory(version) is clean.

Congratulation ! :tada: `git commit` has made a permanent snapshot of your **entire** repository !!!

> Try `git log` now, and see the outputed message :wink:
