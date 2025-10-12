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
