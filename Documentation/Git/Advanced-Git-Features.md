# Other Useful Git Feature

## Three-Way Merge vs Fast-Forward Merge

When performing a `git merge`, without any configuration, git will do either a fast-forward merge or a three-way merge depending on the situation. 
1. A fast-forward merge will occur by default if there is no divergence in its commit history between the two branches. 
2. A three-way merge will occur by default if there is divergence.
Here is a [video](https://www.youtube.com/watch?v=zOnwgxiC0OA) that explains it better with motion graphic. The video also goes into the technical differences between `git rebase` and `git merge`. 

In layman's terms, a `git rebase` will re-anchor the commit from another branch to the tip of the latest commit made on the current branch in order to make the commit history linear. This makes the commit history easier to read and understand but it does have a downside of rewriting commit history. It also makes it harder for other people working in the same branch to merge their commits due to its confusing commit history, and it makes it a pain to debug and resolve conflicts. In other words do not use `git rebase` on a public repositories where there are others, only use it in your own local repository or a private remote repository(we will talk about remote repositories later).
> As long as you follow this quote from the Git official documentation about [rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) you will be fine
> - **"Do not rebase commits that exist outside your repository and that people may have based work on."**

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
