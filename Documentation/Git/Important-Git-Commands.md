# Important Git Commands 

### Git Pull, Git Fetch and Git Merge

When doing a `git pull`, git actually runs two commands; `git fetch` and `git merge`
- `git fetch` downloads all new commits/changes from a remote repo onto your local repository. However, your local repo will not integrate those new commits/changes until a merge. In other words, your change exists but the it is not yet merged with your local repo.
- `git merge` integrates the new commits/changes onto your local repository. 

To perform fetch from a specific remote
```bash 
git fetch [remote_name]
```
To perform fetch from a specific remote branch 
```bash 
git fetch [remote_name] [remote_branch]
```

>[!note]
> 
>The main difference between the two commands is that: 
>- `git fetch [remote_name]` will download all changes from the specified remote repo across all its remote branches
>- `git fetch [remote_name] [remote_branch]` will just download changes from that specific remote branch from that remote
>
>If there are multiple remotes, a`git fetch` that does not specify any remote will by default will use the `origin` remote(even if the current branch is not tracking any remote branch). However if the current branch is tracking a remote branch from another remote then that remote will be used instead.

To integrate changes from a specific remote branch onto your current branch
```bash 
git merge [remote_name]/[remote_branch]
```
To integrate changes from a local branch on to your current branch 
```bash 
git merge [local_branch_name]
```

>[!note]
> 
>`git merge` vs `git merge [remote_name]/[remote_branch]`
>- What is the difference? 
>	- The former will try to integrate any new commits/changes that have been downloaded from the remote branch that your current branch is tracking. If the current branch is not tracking any remote branch or no new commits/changes were downloaded then this command does nothing. Generally speaking a `git merge` does nothing if a `git fetch` command is not performed first. 
>	- The latter forcefully integrates changes from the specified remote branch onto your current branch regardless of whether or not your current branch is tracking any remote branch. If your current branch contains any files, this command can overwrite, delete, or add files into your current branch so be careful with this command. Generally speaking it is likely to  result in a merge conflict if the current branch is not empty. Do also note even if `git fetch` is not performed first this command will try to integrate the already downloaded commits/changes from the specified remote branch onto your current branch but not the new commits/changes that have not been downloaded yet.


 To pull from a specific remote
```bash 
git pull [remote_name]
```
>This would do a `git fetch [remote_name]` and `git merge` on the current branch if the current branch is tracking a branch from that remote

To pull from a specific remote branch 
```bash 
git pull [remote_name] [remote_branch]
```
> This would do a `git fetch [remote_name] [remote_branch]` and `git merge [remote_name]/[remote_branch]`

>[!note]
>A basic `git pull` does a basic `git fetch` that does not specify any remote and `git merge` that does not specify any remote branch. To understand what these basic command reread the information given above.
>
>
> - Although the `git pull` command is a convenient way to use both `git fetch` and `git merge` at once, it is generally avoided by professionals. Instead they would recommend do a `git fetch` first and examine the changes, and if you would like to integrate those changes then do a `git merge` or `git pull` after `git fetch`. Generally speaking that depends on the situation and there are also different `git pull` strategies you can use but for now you just need to know the generic `git pull`. 
>   - Note after you do a `git fetch` it generally doesn't really matter if you do a `git pull` or `git merge`, but if new commits/changes were made after your initial `git fetch`, then a `git pull` would download those new commits/changes and integrate them into your current branch. This may be a problem since you did not examine those changes, so to be safe it is better to just do a `git merge` after `git fetch`. 

>[!tip] 
>
>The commands given above do not automatically set up tracking but we can do a `git pull` and set up tracking at the same time. Run the command:
>- `git pull -u [remote_name] [remote_branch]` in your current branch 
>	- This would do a `git pull [remote_name] [remote_branch]` and set the current branch to track that remote branch.


### Git push 

Now here comes the fun part, after we made our commits/changes we want to push the commits/changes to the remote repo for other to see and pull from. 

> New commits and changes are made when `git commit -m "some message goes here"` is performed. But remember to commit something you must first stage a change using `git add .` or `git add [file_name]`

To push to a specified remote, use
```bash 
git push [remote_name]
```
To push a specific local branch to the remote repo
```bash
git push [remote_name] [local_branch_name]
```
To push to a remote branch with a different name from the current or any local branch
```bash 
git push [remote_name] [local_branch_name]:[remote_branch_name]
```
>[!note]
>
>Differences between the three commands
>1. The first command will try to push the commits/changes to a remote branch that the current branch is tracking. If the current branch is not tracking any remote branch then this command does nothing.
>		- This command would also fail if the tracked remote branch name is different from the current branch name even if the current branch is tracking that branch.
>		- Now here is confusing part if the tracked remote branch that the current branch is tracking does not exist on the specified remote then git will actually create a new remote branch on that specified remote based off of the current branch. But why it does this? Well, I don't exactly know why.
>1. The second command will try to push any new commits/changes made on that local branch to the remote repo assuming no merge conflict happen. However two cases can happen
>		1. If there is a remote branch with the same name as the local branch it will try to push the new commits/changes to that remote branch
>		2. If there no remote branch with the same name as the local branch then git will create a new remote branch on the remote repo with the same name as the local branch
>2. This would push new commits/changes from the specified local branch to the specified remote branch
>
>if there are multiple remote, a `git push` that does not specified any remote would by default used the `origin` remote(even if the current branch is not tracking any remote branch) unless the current branch is tracking a remote branch from another remote then that remote is used instead. 
>
>Git may required you to do a `git pull` first before you push your new commits/changes when this happen it just mean there are new commits/changes that your current branch does not from the remote branch since someone else may have push a new commit to that remote branch this is to make sure that after your new commits/changes still works with those new commits/changes that someone else made. 
>- Also certain errors may occur such as you creating a new local branch that has completely different history from the remote branch you are trying to push to, this would not work even if the two branches have the same name. 
>
> Example: 
> 
> Let say a remote branch called `feature` exist on the remote repo and you create a new local branch called `feature` although they are the same name you may not be able to push local branch `feature` to remote branch `feature` since your local branch `feature` may have completely different commit history depending how it is created(see [[#Branching]] section). To fix this either create a completely empty local branch `feature` with no history at all(see [[#Branching]] section to see how to do this) then do a `git pull origin feature` or `git merge origin/feature` to integrate the commits history and files from remote branch `feature` into local branch `feature`. Or instead creating a local branch called `feature` we just do a `git checkout feature` since `feature` is not an local branch yet it will just create a `feature` branch based off of the remote branch `feature` and also set up tracking for us. 

>[!tip]
>To push and set up tracking at the same time run
>- `git push -u [remote_name] [local_branch_name]`
>	- This would run `git push [remote_name] [local_branch_name]` and set up tracking for the specified local branch. 
