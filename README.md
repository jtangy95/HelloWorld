# HelloWorld
This is a repository for me to get used to Github

Hello I am a student majored in statistics and I hope being capable to use Github professionally in order to collaborate with my classmates and implement version control. 

<br>

## From Github server repository to our local computer
Before starting, we should open terminal in VS code and enter the information of user

```
$ git config --global user.name jtangy95
$ git config --global user.email jtangy95@gmail.com
```

First, if we want to access repository in local computer at first, then we should bring it by `clone`. 
```
$ git clone URL   # URL given in github repository
```

More easy way to do in VS Code is that press `cmd`+`shift`+`p` to open command palette and enter "Git:Clone"  
By clicking repository name or pasting url of the repository, we can access it in local computer. This step may involve connecting to Github website to authenticate that you are the owner or coworker for this repository.
Now you can locate your repository in designated folder in your local computer.

If we `clone` the file before, then we should `pull` to work on local computer. `pull` applies changes in repository to local files. 
```
$ git pull origin master
```

 In VS Code, you can edit your file now. 

 <br>

 ## Edit files in local computer and push to Github server repository

 After some editting files in local computer, we should stage those changes. By `status` we can figure out whether there are changes not staged for commit. 
 ```
 $ git status
 ```
 If there are changes not staged for commit, then we should stage those updated files by `add`.
```
 $ git add .  # stage all updated files in current directory
 $ git add README.md  # stage the file "README.md"
```

Then we can check whether changes are staged well to be committed by using `status` again.

Next, we should commit those changes by `commit`
```
$ git commit -m "Update README file" -m "Some description about change"
```

Finally we should push those changes to Github server repository by `push`
```
$ git push origin master
```

## Take advantage of branching

To implement changes with no risk of damaging current files, we can use branch. 

```
$ git branch
```
This command tells us what branches do we have in the repository. `*`  mark is put on the current branch.

To create a new branch, use the command below.
```
$ git checkout -b develop
$ git branch
```
Now new branch called "develop" is created and `$ git branch` command will show that there are two branches in this repository, with "develop" being a current branch. 

To switch the current branch, use the command below
```
$ git checkout master
$ git checkout develop
```
Here we shall implement staging and commiting the changes in file. Note that the current branch is "develop", not "master".

```
$ git status
$ git add .
$ git commit -m "commit changes in new branch"
```

Now we should merge changes in the branch "develop" to the main branch "master".

```
$ git checkout master
$ git merge develop
```

But the more common pattern we are going to see is pushing these changes on new branch up to Github and then making a pull request.
```
$ git push origin develop
$ git push -u origin develop   
# "-u" is a just shorthand for set upstream
```
Then go to Github and check what changes in the new branch have by clicking `compare pull request`. After checking, we should `merge pull request`. Now the changes are applied to the main branch. 

Note that changes are not applied to the main branch in local computer yet. That is because they are only on Github and we need to pull them down to local environment.

```
$ git checkout master
$ git pull origin master
```
At last, if we don't need the new branch anymore, then delte the branch in local computer by the command below
```
$ git branch -d develop
$ git branch
```
