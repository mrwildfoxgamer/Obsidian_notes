[[Cloud]] #cloud #prog 
##  setting up local repo 

1. download git 
2. after installing set up the config
3. go to the working directory 
4. `git init` to create a local repo on the directory
5. ` git status `to check the file status 
6. `git add <file_name>` to track a file 
   `git add -all` to add all the files 
   `git rm -- cached <file_name>` to un-track the file  
7. `git commit -m "comment"`  to commit to repo with a msg
8. `git commit -a -m "comment"`  to commit to repo with a msg with out the need to run `git add`
#### branch
- `git branch` to view all the branches 
- `git branch <branch_name>` to create new branch
- `git switch <branch_name>` to select a branch or to make a branch active
- `git merge -m "comment" <name_of_the_branch_to_be_merged>` this will merge the branches together
- `git branch -d <branch_name>` to delete a branch

## setting up cloud repo

1. `git remote add orgin <your git hub link>` this will create a connection to your remote repo
2. `git remote -v` to show the current URL (repo)
3. `git remote set-url origin <new_repo_url>` for updating the URL (repo)
4. `git branch -M main` this will make the current working branch to main
5. `git push -u orgin main` this will upload all the files  that has been tracked to git 
6. `git pull` to sync local with cloud 
