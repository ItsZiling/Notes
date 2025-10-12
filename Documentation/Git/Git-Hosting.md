# Using Git Hosting Service

This section will talk about using a git hosting service to backup the local repository to a remote repository. I will be using Github for this purpose, you may use other git services if you like. 
## Linking a remote repository 
1. First we would like to link a remote repo to our local repo

To link a remote repository run the following command in your local repository
```bash
git remote add [remote_name] [remote_repo_url]
```
Suppose I have a test repo I created on github, I would run the command as follows: 
```bash 
 git remote add origin https://github.com/shinziling/testRepo.git
```
Now run
```bash
git remote -v
```
>[!important]
>If you see something like this after the command `git remote -v` then you have successfully linked the repo:
>>`origin  https://github.com/shinziling/testRepo.git (fetch)`<br>
>>`origin  https://github.com/shinziling/testRepo.git (push)`
>
>It may not say `origin` for you depending on what you name the remote
>
>To remove the remote repo just run `git remote rm origin`

>[!tip]
>You can add more than one remote to your local repo, just run the `git remote add` command again with a different URL and give it a unique name. 
### Cloning
If you already have your remote repository set up on somewhere, then you can do a clone instead. This will automatically add a folder in your current directory with the same name as the remote repository if you did not specify a new name. This will also set up the remote. 

Run the command
```bash 
git clone URL
```
> If you would like to clone the remote repo to a specific folder with a specific name, add the name of the folder after the URL. If the folder is not empty, it will not clone the remote repo into that folder. Additionally if there is no folder with that name in your current directory then it will automatically create a folder with that name before cloning the remote repo into the folder. 

Now if you run 
```bash 
git remote -v
```
You should see the remote. 
>By default git names the remote `origin` and creates a branch that matches the name of the default branch of the remote repo(the default branch is the main/master branch of the repo). So for example, if the name of the default branch is `main` then after the clone it will create a local branch with the name `main`.  

>[!note]
>When you clone, the folder that you clone the remote repo into is your local repo, which only exists on your local machine. It is simply linked to a remote repository. Therefore any changes made will only be present in your local repo.
## Tracking and Making Changes

When you clone a remote repository, git will automatically set the `main branch` on your local machine to track the `main branch` on the remote repository that you just clone. 

> 1. You can run `git branch -vv` to see all the tracking information
> 2. Run `git branch -r` to see all the remote branches that exist on the remote repo
> 
> Note: when you run `git branch -r` you may see something like `origin/HEAD -> origin/main` this is something that is set by default by the repo you first cloned. You can change the pointer of where `origin/HEAD` is referencing to another branch on `origin` if you want, but it is not recommended if you do not know what you are doing. All this is telling git to do is to checkout that remote branch by default if the remote name is specified and not a specific branch. For example if you run `git log origin` it will give the commit history of the branch `origin/HEAD` is referencing since a specific branch is not specified. This is also used during cloning purpose where if you clone a remote repo, by default it will clone the remote branch HEAD is pointing to which is usually the default(main/master) branch, however, this depends on how the remote repository is set up. But right now this is not really important for us.

### Branch Tracking

You can specify each local branch to track a specific remote branch. 

- If there is a new remote branch that has been added to the remote repo, and you want to track that newly added remote branch, then you have to do a `git fetch` to download that new remote branch on to your local repo first. 

Let suppose you created a new branch within your local repository and you want to set that branch to track a remote branch on the remote repo. Run the command
```bash 
git branch [local_branch_name] --set-upstream-to [remote_name]/[remote_branch_name]
```
> [!tip]
> You can use the flag `-u` instead of `--set-upstream-to` as short hand<br> 
> `branch_name` can also come after `remote_name/remote_branch`, so you can do
> - `git branch -u [remote_name]/[remote_branch] [local_branch_name]`

Alternatively, you can first switch to the branch then run
```bash 
git branch -u [remote_name]/[remote_branch_name]
```

So if I create a local branch called `test`, I will just run
```bash 
git branch test -u origin/test
# Alternatively, I can switch then set up the track
git checkout test
git branch -u  origin/test
```
> Your local branch name does not have to be the same name as the remote branch

But let say there is a remote branch that you want to checkout but it does not exist on your local repo yet or if you don't have a local branch that is tracking that remote branch and you would like to setup tracking for that remote branch then you can just run the `checkout` or `switch` command

So run either
```bash 
git checkout [remote_branch_name]
# Alternatively
git switch [remote_branch_name]
```
> Git will automatically create a new local branch with the same name as the remote branch name and set up the tracking.

>[!note]
>Make sure you haven't created a local branch that has the same name as the remote branch or else when you run the `switch` or `checkout` command it will just switch to the local branch with that name and not set up the tracking. 
>
> - If you have multiple remotes setup in that local repo then git will may require you to manually create a local branch and specify the remote. So you would run
>   - `git checkout -b [new_local_branch] [remote_name]/[remote_branch_name]`
>   - or, `git switch -c [new_local_branch] [remote_name]/[remote_branch_name]`



>[!tip]
>You can have more than one local branch tracking the same remote branch!
