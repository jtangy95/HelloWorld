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

Finally we should push those changes to Github server repository by `pull`
```
git push origin master
```