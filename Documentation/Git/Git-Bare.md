This is my dotfiles for linux operating system</br> 
To make your own follow the steps below. I will be using `.cfg` as the directory name.

# Configuring a bare git repo

```bash
mkdir .cfg
cd .cfg
git init --bare
```

Alternatively, you can create the directory when making the git bare repos at the same time then `cd` into it. </br> 

```bash
git init --bare $HOME/.cfg
```

## Then add this alias to your .bashrc file or whatever shell alias file you are using 

You can choose any alias name I will be using `cfg` as my alias name.

```bash
alias cfg='/usr/bin/git --git-dir=$HOME/.cfg --work-tree=$HOME'
```
You can also echo it, make sure to replace `.bashrc` to whatever shell you are using.

```
echo "alias cfg='/usr/bin/git git --git-dir=$HOME/.cfg --work-tree=$HOME'" >> $HOME/.bashrc
```

Now set a local configuration to ignore untracked files since we only want git to track the file we explicitly add. Otherwise, it will show a list of untracked files under the work tree `$HOME`.

```bash
cfg config --local status.showUntrackedFiles no
```

# Adding, commit and push file to the repo

```bash
cfg add <name of the file>
cfg commit -m "<message>"
cfg push
```

## Note: before pushing to the repo
A link to a remote repo from your git bare repo is needed for pushing.</br>
To link and push run:
```bash
cfg remote add origin <remote url> 
cfg push -u origin <default branch name> 
```

# Setting up in a new machine

There could be a weird recursive behavior where the `.cfg` might try to track itself. So, add `.cfg` into your global .gitignore.
```bash
echo ".cfg" >> .gitignore
```
Now clone your repo into `.cfg` as a bare repo.
```bash
git clone --bare <remote url> $HOME/.cfg
```
Note: It is not need for `.cfg` to be cloned in `$HOME`, it can be in a subdirectory of `$HOME` just make sure you specify the path of where you want to clone it (e.g. `$HOME/sub/.cfg`). As long as the you still define the work tree as `$HOME` it will pull files and put them in `$HOME` when we checkout.</br>

Setup the alias.
```bash
alias cfg='/usr/bin/git --git-dir=$HOME/.cfg --work-tree=$HOME'
```
Checkout the content in `.cfg` and put them in `$HOME`

```bash
cfg checkout
```
Note: You might get a failed message with somewhere along the line of `error: The following untracked working tree files would be overwritten by checkout:` then showing a lists of file that would be overwritten. This is because there are identical files under the work tree `$HOME`, just either backup them or delete them if you do not need them. Then run the command again.

Set a local configuration to ignore untracked files

```bash
cfg config --local status.showUntrackedFiles no
```
And there you go the new system is setup with your dotfiles.













