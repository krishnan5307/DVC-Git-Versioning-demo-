# DVC-demo-



created env for project dvc_venv
        'conda create -n dvc_venv python==3.9 -y'

created reqiuremnt.txt 
added dvc to install

crated data folder and then data.txt file
added a txt to check first version dvc

initialising git 
        'git init'

initialising dvc
        'dvc init' 

 - so now new .dvc file is created with .gitignore, tmp and config file
 - and this initialized the DVC repository
 - if u want to stire details of remote repositry were u need to store data u can give it in config file

commitng to git
        git commit -m "initialised dvc init"

Now to track some file in git, we give 'git add filepath' , similarly for dvc also we do same to track 'data.txt'
        'dvc add data/data.txt'

-so that above code will, now crated a new tracking file 'data.txt.dvc' inside 'data' foldder
-so we are now not tracking the big 'data.txt' file but 'data.txt.dvc' hashing file
-so the data corresponding to each hash mapping will be present in '.dvc/cache' folder

Track the changes with git, run:

        'git add data\data.txt.dvc' 
        'git add data\.gitignore'
- we dont want to add data.txt anymore as git tracking file 



## incase of any git owneship issue for current and owned user, use this cmd below
>       git config --global --add safe.directory '*'

