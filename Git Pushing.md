## Contents
* [Setting up first time](#setting-up-first-time)
* [Push changes from Local to Remote Repo](#push-changes-from-local-to-remote-repo)
* [Create new branch](#create-new-branch)
* [Delete existing branch](#delete-existing-branch)
* [Git Merge from a branch to another](#git-merge-from-a-branch-to-another)
* [Difference between git push & git push -u](#difference-between-git-push--git-push--u)
* [To simply use git push](#to-simply-use-git-push)
* [See name of Remote Repo](#see-name-of-remote-repo)
* [Add tags](#add-tags)
* [EXTRA TIPS](#📝-extra-tips-📝)


## Setting up first time
```
git config --global user.name <username>
git config --global user.email  <email>
```
* First go to target folder
* To start tracking
```
git init
```

* Telling who is target repo
```
git remote add <nickname> <git_repo_url>
```


## Push changes from Local to Remote Repo

1. Open Git Bash in the folder where file is. (Right Click - Open with Git Bash/Terminal/Powershell)

2. Add the desired file(s) to git
```
git add file1 file2 file3
# To add all files,
git add .
```

3. Add a commit message
```
git commit -m "Commit Message"
```

(Totally OPTIONAL) Can check if the file is staged or not

```
git status
```

4. Finally push the file
```
git push origin main
```

### Create new branch
```
git checkout -b <name>
```

### Delete existing branch
1. First switch to another branch.
```
git checkout <name>
```
2. Delete !!!
```
git branch -d <branch_name>
```
or 
```
git push <remote_name> --delete <branch_name>
```


## Git Merge from a branch to another
```
git checkout <destination_branch>
git merge <pickup_branch>
git add .
git commit -m "Commit message"
git push origin <destination_branch>
```

## Difference between *git push* & *git push -u*

### git push -u (or git push --set-upstream):

* The -u or --set-upstream option is used to set up a tracking relationship between the local branch and the remote branch. 
* When you run `git push -u`, Git not only pushes the changes to the remote repository but also sets up the tracking information. 
* This means that in the future, you can **simply use git push without specifying the remote branch name** or any other arguments.

### git push:

* The basic `git push` command is used to upload local branch commits to a remote repository. 
* When you run git push without any additional arguments, Git attempts to push the changes from the current local branch to the corresponding branch on the remote repository.

## To simply use `git push`
1. 
```
git push -u origin main
```
2. Tracking will be set to origin/main.
3. Then simply git add, commit
4. Now you can simply do 
```
git push
```

## See name of Remote Repo
```
git remote -v
```

## Add tags

Can add tags after pushing also
```git
git add .
git tag -a v1.0.3 -m "checks meter ID"
git push --tags

git commit
git push


```

## 📝 EXTRA TIPS 📝 
* If you changed the name of repository, no affect in local repo.
* Make sure no .git folder inside a subfolder

If there, delete , then git rm --cached \<foldername>
