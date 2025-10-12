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
