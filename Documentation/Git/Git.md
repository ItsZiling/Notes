
# What is Git?
Git is an open source version-control system (VCS) used to help manage code and files for a specific project.
- Often used in a collaboration environment where multiple people are working on the same project.
- Some cloud-based platforms such as Github or Gitlab allow the usage of git to backup the project to a user repository on their website.  


# Getting Started
>[!note]
>This article will go over the basic function of git, its basic command line terminal. You can use any terminal of your choice but I recommend using a terminal that runs on UNIX command line terminal. You can always  run `git help` any time in the terminal to get a list of git commands.
-  First make sure that git is properly installed on your local machine. To do so, run the command:

```bash 
git -v
```

It should pop up something along line of `git version [verison number]` if not, go to this [link](https://git-scm.com/downloads) to download it. 

## Now to initialize a local git repository
1. First create a folder/directory where you would initialize git
	- You can create a folder using the terminal if you would like with the following command. Then use `cd` to enter the folder you just made

```bash 
mkdir [folder_name] # Make a directory
cd [folder_name]    # change directory 
```

1. Now run this command inside the folder/directory you just made
```bash 
git init
```

>[!note]
>You can run `git init` in any folder that you would like to track changes it does not have to be an empty folder/directory. Just `cd` into the folder you would like to track changes in, and run `git init` to set up git in that folder

>To check if you properly initialize git run `ls -a`. You should see a `.git` file listed

To configure your user information locally for the current repository you're in, run the following commands in the repo. 
```bash 
git config user.name "Some name goes here"
git config user.email "Some email goes here"
```

To configure your information for all repositories append `--global` after `config` when using the above commands.

```bash
git config --global user.name "Some name goes here"
git config --global user.email "Some email goes here"
```

>[!note]
>Now note this is only a local repository. Generally speaking we would like to link a remote repository to the local repository, this way we can always push any changes made on the local repo to the remote repo. This allows us to create a backup of our project in case anything goes wrong.  I will cover this later but for now we just go over basic git commands.

## Staging

After creating our local repository we can start using git for real.

1. First, in your local repository add some files to your local repo. I will add a README.md file to illustrate this, and we can use the terminal to add the file and make changes to the file. Run this command in your local repo.
```bash 
touch README.md # This would create a file with the name README.md
```

Add something to the file with the editor of your choice (notepad works) then run the command
```bash 
git add README.md # this would add the file changes to the stage environment
```
> You can run `git add .` to add all the files to the stage environment
> To remove a stage change run `git rm [file_name]`



To see all the files in the stage environment run 
```bash 
git status
```

>[!note]
>Note when running `git add .` you might  add files that you do not want to commit. If this happens, add a `.gitignore` file in the repo using the `touch` command as used in previous examples. Then, using a text editor, add the the name of files you do not want to be added to the stage environment in the `.gitignore` file. 

2. After staging all the files we can now commit the change
```bash 
git commit -m "some message goes here"
```

> People* often get confused with the `git commit` command. All commit does is create a point in history of the changes you have made at which you can view all the commits that have been made using `git log`. It is what controls version history in your repo in simple terms.
> 
> Let's say you accidentally stage a change to a file you did not mean to make using the `git add` command. In such a case, you can then revert the change using `git restore` to revert the file to its last commit. Git will generally tell you how to revert the change when you run `git status`. Normally it will probably be something like this: 
> 1. `git restore --staged [file_name]` 
> 2. `git restore [file_name]`
> 
> Run both command in the order that is listed above
> > * Editor's Note: The writer is talking about me. He has never known anyone else to actually have difficulty with understanding commit. I am a certified idiot.

## Branching

Branching is of most utmost importance when it comes to Git. Generally, we do not want to make changes directly to the main (sometimes called master) branch since that branch should contain the most stable build and deployment-ready build. The main branch should ideally be the version the public is using. Due to this, when making any changes, we should create a new branch off of the main branch or perform a fork (covered later). The new branch will be based off of the latest commit that has been made to the main branch at the time the new branch was create; an effect of this is that you can have multiple branches off of the main branch at different points in the commit history log.
- This allows us to make any changes we want without modifying the content within main/master branch. 
	- Useful when we want test a new feature we would like to implement to the main branch.
	- When we want to implement those feature to the main/master branch we can just do a merge.
> When creating a new branch, the new branch is based off of the current branch you are in and contains all the files of the current branch and its commit history. The new branch also does not have to be based off of the main branch.

1. To create a new branch run these command in your local repository
```bash
git branch [new_branch_name]  # create the new branch if it didn't already exist
git switch [new_branch_name]  # switch to the new branch
```
> This will create a branch based off of the current branch you are in. You can also use `git checkout` instead of `git switch`. There is a slight difference in their usage which we cover in the next bits. But `git switch` is basically a split off command of the `git checkout` command. For official documentation see [switch](https://git-scm.com/docs/git-switch) and [checkout](https://git-scm.com/docs/git-checkout). 

>[!tip]
>You can simplify the process of creating a branch and switching to the branch in one terminal line command. Simply run 
>- `git checkout -b [new_branch_name]` or
>- `git switch -c [new_branch_name]`
> 
> Both commands will create and switch to the newly created branch (and checks them out).
>
>If you want to create a branch based off of another branch that you are not currently in then run 
>- `git checkout -b [new_branch_name] [name_of_another_branch]`
>
>To create an completely empty branch run 
>- `git switch --orphan [new_branch_name]`
>	- This would create a branch with no files, folders or commit history, except for changes that git has not yet tracked (due to the changes not yet being committed)

> [!important]
> Difference between `git checkout` and `git switch`
>
> As I said before, `git switch` is a split off command of the `git checkout`, it is the new way of switching to a branch due to the complexity of `git checkout` which does more than just switching to another branch: 
> - It can switch to a branch
> - It can copy the files from the stage on to your current working tree
> - It can be used to restore a file to its last commit
> - It can copy files from another branch or commit into your working tree without actually switching branches.
> 
> Because of this, it often lead to confusion in its usage so two new commands was created to reduce ambiguity: `git switch` and `git restore`. Therefore, it is recommended to soley use `git switch` for switching branch and `git restore` to restore a commit as they are easy to remember just based on their name meanwhile `git checkout` should used as an advanced option for other things that deal with the tree.

> To see all existing branches, simply run `git branch`. To remove a branch, run `git branch -d [name_of_the_branch]`

Now lets suppose we edit our README.md in our newly created branch. This change is only present within the newly created branch and not the main branch. If we want to integrate the changes to the main branch we would do a merge on the main branch
1. First change back to the main branch 
```bash 
git switch [name_of_the_main_branch] # most likely to be called master or main
```
2. Now do the merge
```bash 
git merge [name_of_the_other_branch]
```
> This would update the main branch content to match the newly created branch

>[!note]
>
>There are other ways to merge two branches together such as `git rebase`, but on the most basic level a `git merge` works well and people understand it the best. Do note, although it is called `merge` they do not actually merge together into one branch. The branch that you did the merge from still exists and you can still work on that branch. All `git merge` does is integrate changes from another branch on to your current branch

To merge main branch content on to another branch -- perhaps because someone did a commit to the main branch, and you want to see if that commit still works with the feature you are working on in the current branch-- you would do the exact same step as above but instead being in the main branch you would just be in the current branch you are working on and do a `git merge [name_of_the_main_branch]`. 
- You can also do a merge between two branches that are not the main branch
	- Let say you have `branch1` and `branch2` and both branches are not the main branch. You can still perform a merge on `branch1` from `branch2` and vice versa. 

>[!important]
>A merge conflict may occur when merging two branches together. If this happens, git will abort the merge and require the user to resolve the conflict before proceeding with the merge again. To see conflict files do `git status` and after fixing the conflict do a `git add .`  or `git add [name_of_conflicted_files]` (there can be more than one conflicted files) to stage the change and then  `git merge --continue` to continue the merge. Generally speaking you can do `git status` again after resolving the conflict, and it will tell you what to do to continue the merge.
>>If you're really stuck do a `git merge --abort` to abort the merge completely or do a `git reset --hard` this would reset your branch to its last commit state, but do note it will remove all uncommitted changes.

>[!note]
>All the branches you have made are called local branches since they only exist on your local repository. We will talk about remote branches later.

## Three-Way Merge vs Fast-Forward Merge

When performing a `git merge`, without any configuration, git will do either a fast-forward merge or a three-way merge depending on the situation. 
1. A fast-forward merge will occur by default if there is no divergence in its commit history between the two branches. 
2. A three-way merge will occur by default if there is divergence.
Here is a [video](https://www.youtube.com/watch?v=zOnwgxiC0OA) that explains it better with motion graphic. The video also goes into the technical differences between `git rebase` and `git merge`. 

In layman's terms, a `git rebase` will re-anchor the commit from another branch to the tip of the latest commit made on the current branch in order to make the commit history linear. This makes the commit history easier to read and understand but it does have a downside of rewriting commit history. It also makes it harder for other people working in the same branch to merge their commits due to its confusing commit history, and it makes it a pain to debug and resolve conflicts. In other words do not use `git rebase` on a public repositories where there are others, only use it in your own local repository or a private remote repository(we will talk about remote repositories later).
> As long as you follow this quote from the Git official documentation about [rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) you will be fine
> - **"Do not rebase commits that exist outside your repository and that people may have based work on."**
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
>[!success]
>If you see something like this after the command `git remote -v` then you have successfully linked the repo:
>>`origin  https://github.com/shinziling/testRepo.git (fetch)`<br>
>>`origin  https://github.com/shinziling/testRepo.git (push)`
>
>It may not say `origin` for you depending on what you name the remote

>To remove the remote repo just run `git remote rm origin`

>[!info]
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



>[!tip]-
>You can have more than one local branch tracking the same remote branch!
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

>[!note]
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



## Pull Request 

If you are collaborator for a remote repo, normally the repo owner prevent any direct changes onto the main branch and would required collaborator to make changes on a separate branch and create a pull request to integrate changes from one branch into another. <br>
Now pull request is not a git feature it is feature in which git hosting services use, in Github you would create a pull request on the repository to compare and merge the commit on the source branch into the destination branch and a discussion would open, in which collaborator would discuss whether or not to merge the commit onto the destination branch. 
- It typically require a certain amount of approvals before the merge can happen, however, the repo owner can force merge the commit without the required number of approval.

>[!note]
>
>You can merge commit between branch however you want in your local repository for testing purpose and it is generally recommended you do your own testing first before opening a pull request.
>
> 
> 
> - Note everything here is in regards with personal repository. Github also have something called organization and repository that belongs to an organization works differently from a personal repository since an organization support a feature called teams each teams performs a specific role in the organization but an organization repo can also have collaborator. However, a pull request still works the same. 
>
> You can merge commit between branch however you want in your local repository for testing purpose and it is generally recommended you do your own testing first before opening a pull request.
>
> 
> - Note everything here is in regards with personal repository. Github also have something called organization and repository that belongs to an organization works differently from a personal repository since an organization support a feature called teams each teams performs a specific role in the organization but an organization repo can also have collaborator. However, a pull request still works the same. 
## Forking

If you are not an collaborator for an repo then you do not have any direct access to the repo itself and cannot open branch directly on the repo. However, you can fork the repo into your own repo as long as the repo you are trying to fork is public(after all you can't see a private repo) .<br>
To fork an repository
1. Go to the Github page of the repo you wish to clone
2. press the fork button in the top-right hand area of the repository page.
4. It will then tell you to create a copy of that repository into your own account and depending on the scenario, in most cases you only just want to copy the default branch and this should be checked by default, if you unchecked this it would copy all the branches. 

After forking you can then clone the repository you just fork from your own account and onto your local machine. You can now add branches to the forked repo, make changes and push changes to the remote branch. When you make changes the changes is only present in your own forked version of the original repo. This way you can test your changes and feature you would like to add.<br>
The forked repo is also linked to the original repo so you can also make pull request from the forked repo. 
>[!note]
>It is recommended that after you clone the forked repository into a local repository you keep the local sync up to the original, so you would add original repository as another remote in your local repo. In Github the new remote would be named `upstream`. This way you can also pull changes from the original repo into your local repo to keep the repo up to date with the original. <br> 
>It is also recommended that you create a new branch off of the default branch after the fork, this is because even though it is a fork we want the default branch of the forked repo to be kept in sync of original repo default branch so we would not want to directly commit changes into the default branch instead we would just want to pull changes from the original repo default branch onto our forked repo default branch.
# Other Useful Git Feature

## FETCH_HEAD
When you do a `git fetch` such as `git fetch [remote_name] [remote_branch]` a temporary FETCH_HEAD branch will be created referencing the latest fetched commit. <br> 
We can then switch to the FETCH_HEAD using:
```bash 
git checkout FETCH_HEAD
```
This put us in a detached HEAD state and allows us to examine the commit and make experimental commit if we like and any commit we made in this state is loss after we switch out of FETCH_HEAD. If we want to retain those commits we can create a new branch using:
```bash 
git switch -c [new_branch_name]
```

>[!note]
>
>HEAD just mean it references the latest commit you made on the current branch. This is also known as the tip of the branch. 

## Git Stash
This is an advance git feature which allows you to move your uncommitted changes aside stashing them and put them on a stack. It would then revert your working directory back to the last commit you made in the current branch in other word the HEAD commit.<br>
To stash run
```bash 
git stash
```
> You can stash multiple times and it put each stash on top of the stack, meaning the very top of the stack is your latest stash

If you are lazy like me we can stash all the files(tracked and untracked) without having to do `git add` 
```bash 
git stash -u
```
> This is same thing as doing `git add .` then `git stash` 

To see all stashes run
```bash 
git stash list
```
> This would list all your current stashes with a number associated with each one, the stash on the very top is indexed-0

To see all file changes in the stash run
```bash
git stash show
```

To reapply the latest stash run
```bash
git stash pop
```

To specify a stash run 
```bash
git stash pop --index [number]
```
> Example: `git stash pop --index 1` will reapply the second stash on the stack since the first stash is indexed 0 

We can also give each stash a name to help organize the stash 
```bash 
git stash -m 'some message goes here'
```
>So if you run `git stash list` you can see the name next to each stash

We can also create a new branch and apply a stash on that branch
```bash 
git stash branch [new_branch_name] [stash_index_number]
```

To drop a stash in other word if we don't want those commit anymore run 
```bash 
git stash drop stash@{index_number}
```
>So if I run `git stash drop stash@{0}` this would drop the stash at index 0

To completely drop all stash run
```bash
git stash clear
```
