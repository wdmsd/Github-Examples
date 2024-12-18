# Github-Examples
A repo containing GitHub for programmatic examples

## Git Hidden Folder
There is a hidden folder called `.git` which tells us that our project is a git repo.

If we want to create a git repo in a new project we create a folder that we initialize that repo using `git init`

```sh
mkdir /workspace/tmp/new-project
cd /workspace/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add . 
# we can remove everything by using git reset
git reset
git add Readme.md
# make changes to Readme.md
git commit -m "add readme file"    
```
## Cloning
We can clone using three ways : HTTPS, SSH, GitHub Cli.

Since we are using Github codespace we'll create a temporary directory in our workspace
```sh
mkdir /workspace/temp
cd workspace/temp
```
### 1- HTTPS
```sh
git clone https://github.com/wdmsd/Github-Examples.git
cd Github-Examples/
ls -la
```
> We will need to generate github a personal access token  (PAT) https://github.com/settings/tokens?type=beta

We will use the PAT as our password when we login
- give it access to contents for commits

### 2- SSH

```sh
git clone git@github.com:ExamProCo/Github-Examples.git
cd Github-Examples
```

we will need to create our new ssh key pair

```sh
ssh-keygen -t ed25519 -C "mail@example.com"
```

Then in new powershell window with admin access
```sh
# start the ssh-agent in the background
Get-Service -Name ssh-agent | Set-Service -StartupType Manual
Start-Service ssh-agent
```
In a new cmd window add our private key
```sh
ssh-add c:/Users/YOU/.ssh/id_ed25519
```
If you clone you repository in the beggining using https then you need to access you git config file and modify the url parametre

### 3- Github Cli

Download and install Cli from https://cli.github.com/

Once it's installed add it to your local varial path 
```sh
gh auth login
```



## Commit

When we want to commit code `git commit` which will open up the commit edit message in the editor of choice

```sh
git commit
# commit with a message without opening an editor
git commit -m "add your message here"
```


## ADD
When we want to stage that will be inculded in the commit we can use `.` to add all possible files 

```sh
git add 
```
## Reset
reset allows us to move staged changes to unstaged.
This is usefull when we want to revert all files not to be commited

```sh
git add .
git reset
```
> git reset will revert a git add . 

## Status
`git status`  shows us what files will or will not be commited

## Gitconfig file

the gitconfig file ìs what stores our global configuration for git such as email, name, editor and more

```sh
git config --list
```

## Log
`git log` will show recent git commits to the git tree

## Push

when we want to push a repo to our remote origin

```sh
git push
```
