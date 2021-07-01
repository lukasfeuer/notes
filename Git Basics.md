# Git

### Tutorial 

https://www.youtube.com/watch?v=RGOj5yH7evk



## Terminal Commands

--> use bash

pwd : show current directory path

cd : change directory ("cd .." to move up/back)

cd ../NameOfOtherSameLevelFolder : moves "up" and then "down" into another folder on the same level

ls : show items in directory 

ls -la : also show hidden folders

clear : clear the terminal 

ls | grep test_key : list objects containing the expression in the directory

ssh-keygen -t rsa -b 4096 -C "github@emailadress" : generates an SSH key, also see: https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

cat filename : print out content of filename (e.g. SSH key)



## Git Commands

--> execute in bash - Terminal 

git --version : install git if not already there

git clone : clone repository to local folder

git add : tell git that changes were made and they should be tracked 

git commit : save changes in git 

git commit -am "message" : if files only modified (they were staged before), -am is a short cut for add and commit 

git push : upload local git to online repo 

git pull : download changes from remote repo to local machine 

git remote -v : shows all remote repos connected to locale git repo

git remote remove origin : to remove the association of local copy to remote repo

git branch : shows branches ("*" indicates the branch currently on) --> press "q" to get out of the command

git branch -M main : renames master branch to "main" --> useful for github

git checkout -b newBranch : create new branch

git branch -d Name : delete Branch

git checkout : to swich between branches (add "-b newName" to create new branch)

git diff : show changes mage on branch 

git reset : e.g. to undo accidental staging of files

git reset HEAD~1 : HEAD is a pointer to the last commit, ~1 means to go back one further

git reset HashOfCommitToGoBackTo : undoes all commits since then. Changes are still there, but nut commited

git reset --hard HashOfCommitToGoBackTo : deletes the changes, not just undoes the commits

git log : show log of all commits 


git branch -m master oldmaster : rename branches


## Example workflow


### Create Repo on GitHub 

* create new repo on Github/Bitbucket e.g. "myrepo"

* create README.md file as description for the project 

* create/select local (empty) folder to pull online repo into 

* set the wd in the terminal to the folder (next step will create a new folder inside)

* clone with HTTPS: git clone https://github.com/lukasfeuer/szenarienmanager.git
  * alternatively with SSH 
  
* "cd" into the folder

--> make changes to the folder, add code etc.

* git status : show untracked files/changes 

* git add . : to add ("stage") all untracked files/changes to git, so git can track them 

* git commit -m "Informative Commit Message as a title" -m "optional more detailed description of the commit" : commit the staged changes to git, optionally with a second -m for more details 

* git push : to push locale git to online repo (if SSH is used, keys have to be created beforehand: 20:40 in the tutorial)

* git push origin master 
  * origin : placeholder for path to directory
  * master : branch to push to



### Create Repo Locale

* create empty locale folder and add some files 

* git init : to initialize Repo

* git status
* git add .
* git commit -m "message"

* create an empty repo on github (e.g. "testrepo")

* copy ssh/https link to repo from github

* git remote add origin https://github.com/lukasfeuer/shiny_szenario.git : add a reference

* git push -u origin main /oder/ master  : first push has to set an "upstream" (-u), after that, git push is enough (origin master is the upstream?) --> -u is short for --set-upstream


## Create Branches

* git branch 

* git checkout -b newBranch : creates new branch (git checkout master : get back to master branch)

* make some changes to code 

* git add & git commit : changes only visible on the one branch

* git diff NameOfBranchToCompareWith: before merge, compare two versions og the code 

* git push -u origin NewBranchName: less common alternative: "git merge NameOfOtherBranch"



### Pull Request (PR)

Request to have code pulled into another branch

#### Adding Locale Changes to Master (typical workflow) 
* see Tutorial around 44 Minutes 

* Merge on git hub

* git checkout 

* git pull origin master : to pull online merge to local 

* git branch -d NameOfBrnachToDelete

#### Merge Branch with Master Local
Useful work flow, if working on side-branch (e.g. feature development), but to regularly pull changes (made by others) from master, so that master-version of the branch does not get to far behind master

* Tutorial around 50 Minutes

* git merge master 



## Undoing

