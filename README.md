
![alt text][logo]

[logo]: https://git-scm.com/images/logos/downloads/Git-Logo-1788C.png


**Git** is an essential tool for every developer. It can be daunting at first for the beginners :dizzy: so practicing it is a top priority.

In this document, you'll find the essential commands to help you out when working on your sprints.

Think of it as a cheat sheet :ledger:, grab this readme or open it in a new tab while hacking.

I encourage you to fork this repo, and to use it as a practice dummy.
<br>
## Bootstrap And Configuration :rocket:
Before you do anything, you need to configure the User information for your local work.
- **setting the user name**
```
git config --global user.name "your_name"
```
- **setting the user email**
```
git config --global user.email "your_email"
```
## Working With A Repository

Much of the time you'll be working with an existing repository that you need to fork and download locally on your machine.
```
git clone "link"
```
This will download a "copy" form the existing repository to your machine, with all of its files, commits and branches.
> If you wish to create your own repository, use `git init` to make your local directory a git repo ready to be pushed to github :sparkles:

> By default the name of the remote will be `origin` if not specified.

- **Pull && Push** :point_down: :point_up:

This part deals with synching the remote repository(from Github) with your local one(on your machine).

Say that you've successfully clone a repo from github, and you've been working on it hard just to realize that the owner of the repo just made an update and/or added a new file to the repo :angry:. 

Should you Fork and Clone again ? HELL No !

If you've cloned the repo onto your machine, running `git remote -v` in the terminal will give you the name and the *link* of the original repo from where you cloned. Nice eyh ?

So all you need to do is to run the `pull` command and VOILA!

A typical example of this is what follows:
```
$ git remote -v
origin https://github.com/orginization/exercice01.git

```
To update your local repo with the changes made in the remote one you just run:
```
git pull origin master
```
> Notice that we used `origin master` to specify the remote and the branch from which we need the updates.

- **Push** :airplane:

Alright, you finished your work, you saved everything and now you need to show the world what good of a job you did.

Comes in the `push` command, running it will upload all of your commits and branches to Github, preferably your own account.

So first make sure you have the link of the desired repo you want to upload to :
```
$ git remote -v
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
The above command will prepare your file to be staged. It's like saving the **changes** you've made in your file **NOT** the file itself. The command `git add` grabs a *snapshot* of the file :camera:. Think of it as a camera that takes sanpshots of the changes you've made.
``` 
git add file-one
git add file -two
...
```
To snapshot all of the changes you've made on all the files in the current directory, use the `.` argument instead.

Just use `git add .` instead of adding your files one by one manually.

Now your changes are ready for the next stage.

- **Commitment** :ring:

Alright, now repeat this mantra at least twice a day:

> git, is a version-control system and Github is the platform for hosting git repositories.

The `commit` command works on the snapshots taked by the `add` command.
```
git commit -m "meaningful_message_describing_the_changes"
```
This command will save your *staged* changes.

Here if you run `git status`, it's going to tell you that your working directory(version) is clean.

Congratulation ! :tada: `git commit` has made a permanent snapshot of your **entire** repository !!!

> Try `git log` now, and see the output message :wink:

## Branches :herb:
![alt text][branches]

[branches]: https://cdn9.dissolve.com/p/D984_45_897/D984_45_897_1200.jpg
Branches are ... branches of your working tree, that holds your commits. You've already seen the `master` branch, and you've always been working on the same branch.

A branch, allows you to isolate some snapshots and commits from the original code. So the act of *Branching* allows you to work on the same code without changing the original code (if that makes sense).

Let's take an example of how branching works:

We have a repo initialized with a `master` branch that has the original code. Now Chris, wants to work on that code but accidentally in a hurry, he commits to the `master`, the original work is lost and poor Chris got fired :(  CHRIS WHAT HAVE YOU DONE !!!
To avoid Chris' mistake, we just have to create a new branch before we start our work, we call it something original like `test`, so now the repo holds two branches: `master` that has the original code and `test` our own branch, that holds our modification of `master`.

`git branch` will list to you the branch existing in your file.
> The branch that you are working on will have an asterisk sign `*` in front of it.

- **Create A New Branch**

`git branch [name-of-branch]` will create a new branch.

- **Switching Branches**

To switch from branch to branch like a professional spider monkey, use `git checkout [name-of-branch]`.
> If you don't know what branch are you looking for run `git branch`

:no_entry: `checkout` will jump you to the specified branch and **updates your directory** ! Make sure that your working directory is clean (snapshots saved) because otherwise, you'll lose any changes that weren't committed.

- **Delete Branches**

To delete a branch just use the `-d` option followed by the branch's name
```
$ git branch
person1
*master
$ git branch -d person1
$git branch
*master
```
- **Rename A Branch**

To rename a branch, use the `-m` option or `--move`.
```
git branch -m [name-of-branch] [new-name]
```

...

## Resources! :fire:

- [Simple Guide](https://rogerdudler.github.io/git-guide/). :closed_book:
- [Git Immersion](http://gitimmersion.com/).
- [Git Branching Online](https://learngitbranching.js.org/) :herb:
- [Git cheat sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet) .

