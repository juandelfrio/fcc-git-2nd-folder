# Free Code Camp Git & GitHub Intro cont'd

A. Start git repo locally (on my computer)  
    * Command:  Change parallel level directories:  
    1. In PowerShell, type:  
        * cd ../directoryToGoTo  
    2. Make a folder a git repo:  
        i. Check that the folder is not git repo:  
        * git status  
       ii. If "not a git repo" prints in terminal, then:  
       iii. Type:  
        * git init  
        iv. Checking git status again will show untracked files, if a file, such as this README.md, is in the folder  
        * Again, type:  
        * git add README.md  
        * or  
        * git add .  
        v. Checking status again will show README.md as a new file  
        vi.  WAIT TO DO git commit...  
    3. Add new repo in GitHub  
        i. Name the new empty repo the same name as new local git repo folder in section A.1., above.  
        ii. Copy SSH link to new repo  
    4. In local (computer) terminal, notify local git of remote repo in GitHub:  
        i. Type in terminal:  
        * git remote add origin <pasted_GitHub_ssh_link.git>   
        ii. Check the remote worked.  Type:  
        * git remote -v  
        * A list of local repos with a key to same GitHub repo appear  
    5. Push new repo to GitHub.  
        i. Type:  
        * git push origin main  
    6. Push minimization:  
        i. To avoid retyping "origin main", set an upstream marker, -u.  
        ii. Type:  
        * git push -u origin main  
        * Now, only "git push" need be typed  
    7. 
        
