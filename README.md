# DVC-demo-



# created env for project dvc_venv
        'conda create -n dvc_venv python==3.9 -y'

created reqiuremnt.txt 
added dvc to install

crated data folder and then data.txt file
added a txt to check first version dvc

# initialising git 
        'git init'

# initialising dvc
        'dvc init' 

 - so now new .dvc file is created with .gitignore, tmp and config file
 - and this initialized the DVC repository
 - if u want to stire details of remote repositry were u need to store data u can give it in config file

# commitng to git
        git commit -m "initialised dvc init"

# Now to track some file in git, we give 'git add filepath' , similarly for dvc also we do same to track 'data.txt'
        'dvc add data/data.txt'

-so that above code will, now crated a new tracking file 'data.txt.dvc' inside 'data' foldder
-so we are now not tracking the big 'data.txt' file but 'data.txt.dvc' hashing file
-so the data corresponding to each hash mapping will be present in '.dvc/cache' folder

# Track the changes with git, run:

      - git add data\data.txt.dvc
      - git add data\.gitignore
- we dont want to add data.txt anymore as git tracking file 



## incase of any git owneship issue for current and owned user, use this cmd below
>       git config --global --add safe.directory '*'



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

## only we can switch to a particular data dvc versioing we done after checkinout that particular git versioing 
## both goes hand in hand

## each time when we go to that particular versioing we can see data/data.txt getting changed to that particular data and that hashing in data/data.txt.dvc getting chnaged to that particlar hash. # 
# This is bcoz the changes from 'git checkout <id>' will chnaes data/data.txt as it is tracked by git and this in turn will fetch that particualr hashing id data from '.dvc/cache' and this wil updated in data/data.txt