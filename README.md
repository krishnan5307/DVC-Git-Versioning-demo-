# DVC-demo-



# created env for project dvc_venv
        'conda create -n dvc_venv python==3.9 -y'

created reqiuremnt.txt 
added dvc to install

crated data folder and then data.txt file
added a txt to check first version dvc

# initialising git 
      - git init

# initialising dvc
      - dvc init 

 - so now new .dvc file is created with .gitignore, tmp and config file
 - and this initialized the DVC repository
 - if u want to stire details of remote repositry were u need to store data u can give it in config file

# commitng to git
      -  git commit -m "initialised dvc init"

# Now to track some file in git, we give 'git add filepath' , similarly for dvc also we do same to track 'data.txt'
      - dvc add data/data.txt

-so that above code will, now crated a new tracking file 'data.txt.dvc' inside 'data' foldder
-so we are now not tracking the big 'data.txt' file but 'data.txt.dvc' hashing file
-so the data corresponding to each hash mapping will be present in '.dvc/cache' folder

# Track the changes with git, run:

      - git add data\data.txt.dvc
      - git add data\.gitignore
- we dont want to add data.txt anymore as git tracking file 



## incase of any git owneship issue for current and owned user, use this cmd below
>      - git config --global --add safe.directory '*'



## add a new text to data/data.txt file 

      - dvc add data/data.txt
      - git add data/data.txt.dvc
      - git commit -m "updated for new data versining of text"

repeat this step for n number of data modified in data/data.txt 

## to go to that particualar chekout or data versinoing or branch 

      - git log   ## to see the versioning id in git and copy that id
      - git checkout <versioining id copied earlier: eg :14a8427d26b3041da94f44a1db322b6ebcc6245e >
      - dvc checkout 

now in data/data.txt we can see the data during till that particular versnioing
means hash will change to that particualr one from .dvc/cache folder 

## to switch back to main branch in git

      - git checkout main

only we can switch to a particular data dvc versioing we done after checkinout that particular git versioing 
both goes hand in hand

each time when we go to that particular versioing we can see data/data.txt getting changed to that particular data and that hashing in data/data.txt.dvc getting chnaged to that particlar hash. # 
This is bcoz the changes from 'git checkout <id>', will chnaes data/data.txt as it is tracked by git and this in turn will fetch that particualr hashing id data from '.dvc/cache' and this wil updated in data/data.txt


Below steps has to be used inorder to push changes while woriking form new feature branch to main/master/remote repo

# incase u need to create a feature branch and later push it to remote repo or main/master branch

# Create a New Branch:
      - git branch new-branch-name
# Switch to the New Branch:
      - git checkout new-branch-name
# single command to create and switch to the new branch:
      - git checkout -b new-branch-name
# Make Changes and Commit:
      - git add .
      - git commit -m "Your commit message here"
# Push the New Branch to the Remote Repository:
      - git push origin new-branch-name 
This step is optional, and you can skip it if you are working locally

 the remote main branch has changes that your local branch (new_branch) does not have. To resolve this, you need to fetch the changes from the remote main branch, merge them into your local branch, and then push your changes again. Here's the sequence of commands you can use:
# Switch to your feature branch
 - git checkout new_branch

# Fetch the latest changes from the remote repository
 - git fetch

# Merge the changes from the remote main branch into your feature branch
 - git merge origin/main
Resolve any merge conflicts if there are any

# Push your changes to the remote main branch
 - git push origin new_branch:main




# Set the New Branch as Default:
      - git branch -m main
      - git push -u origin main
If you want to make the new branch your "master" branch, you can rename it locally and push the changes:
Replace "main" with the desired name for your default branch.


# if ur feature branch is behind chnages reflected in main , then u need to pull the changes from main into feature branch
Your branch is behind 'origin/main' by 8 commits, and can be fast-forwarded. (use 'git pull' to update your local branch)" means that your local main branch is not up-to-date with the remote main branch. There have been 8 new commits on the remote main branch that you don't have in your local branch.

To update your local main branch with the latest changes from the remote repository, you can use the following commands:

       - git pull origin main
After this step both feature and main branch will have all changes    

# you might want to make sure your feature branch is also up-to-date with the latest changes from the main branch everytime u r swithcing the branches, all branhches should be updated. 
       - - git pull origin main


