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
