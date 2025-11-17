🔹 1. Initialize an empty Git repository

     git init


🔹 2. Check file status 

    git status

🔹 3. Add files to staging
   #files will br track you can delete if you don't want your file to be track

    git add <file name>

    git add .

🔹 4. Commit changes with a message

    git commit -m <message>

🔹 5. Configure Git user details

    git config --global user.name

    git config --global user.email

🔹 6. Create a new branch

    git checkout -b dev

🔹 7. Switch to another branch

    git switch to main

🔹 8. Local vs Remote Branches

    Local repo → Stored on your system (main or older master)

    Remote repo (GitHub) → Usually uses main

🔹 9. Clone a Remote Repository

     git clone <repo url>

🔹 Step 10 — Add the remote GitHub URL

    git remote add origin https://github.com/YOURNAME/YOURREPO.git 


🔹 Step 11 — Add credential at one time
    
     git config --global credential.helper cache

     
🔹 Step 12 — Push branch from local to main
     
     git push origin <branch name>
     #this is when you clone repo from remote to local then after making changes you will use this command

    
