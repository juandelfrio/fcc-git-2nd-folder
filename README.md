# Free Code Camp Git & GitHub Intro cont'd

A. Start git repo locally (on my computer)  
   * Command:  Change parallel level directories:  
   1. In PowerShell, type:    
         * cd ../directoryToGoTo      
   2. Make a folder a git repo:  
      i. Check that the folder is not git repo:  
         * git status    
     ii. If "not a git repo" prints in terminal then:  
    iii. Type:   
         * git init    
     iv. Checking git status again will show untracked files, if a file, such as this README.md, is in the folder  
      * Again, type:     
         * git add README.md     
      * Or    
         * git add .     
      v. Checking status again will show README.md as a new file  
     vi.  WAIT TO DO git commit    
   3. Add new repo in GitHub  
      i. Name the new empty repo the same name as new local git repo folder in section A.1., above.  
     ii. Copy SSH link to new repo.  
   4. In local (computer) terminal, notify local git of remote repo in GitHub:  
      i. Type in terminal:    
         * git remote add origin <pasted_GitHub_ssh_link.git>   
     ii. Check the remote worked. Type:    
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

## Branch Intro

A. Purpose: Branching sets storage for new code testing and dev separate from earlier versions of the code that are known to work.  
   * Branches can be made along any point in the main code as testing grounds for debugging or modification.  

B. Correcting push errors: 
   1. No master in GitHub to push to:  
      * "error: src refspec main does not match any"    
      * "error: failed to push some refs to"  
      i. These errors mean GitHub has no branch to place commits.  So a new "master" branch is required.  
      *  Reference: https://stackoverflow.com/questions/65173291/git-push-error-src-refspec-main-does-not-match-any-on-linux  
     ii. Type in PowerShell:  
         * git push origin master
      * Or, to create a new name for the master branch, type:  
         *  git branch -m master <yourBranchNameBUTNOTmain>  
      * If the master branch is named "main" or not named at all, an error occurs.  
   2. Unsaved files in git repo.  
      i. Save the files, then check git status

C. Delete and create (non-master) Branch  
   1. Delete a remote branch:  
         * git push origin --delete myBranchName 
   * Reference: https://www.git-tower.com/learn/git/faq/delete-local-branch/   
   2. Create a new non-master branch: name it descriptively:  
         * git checkout -b yourBranchName
   3. To change to a new branch in terminal:  
         * git checkout yourBranchName  

D. Working with branches  
   1. To add a repo or isolated update to the branch:  
      i. Confirm you're in the branch you want  
         * git branch  
   2. Review repo or isolated update status in main branch and new branch:  
      i. git add myRepoName or git add .  
     ii. Check main branch:  
         * git checkout mainBranch  
      * Message at bottom says, "Branch up to date with 'origin/main'.  
    iii. Check new branch:  
         * git checkout newBranch  
      * Modified fileName should appear, with M in front.  
     iv. Compare new branch file changes to main branch file:  
         * git diff  
      * Displayed in terminal: fileName, subheader, and changes to file.  
   3. If ready, you could merge new branch with main branch, but more commonly, push new branch and contents to GitHub  
      i. GitHub needs a new branch for new local branch to push to.  
     ii. Hence, 'git push' alone results in error  
         * git push -u origin newBranchName

E. Pull requests and Merging  
   0. Merge conflicts:  Refer to E.3., below.
   1. The new branch and its new file or isolated update should be on GitHub.  
   2. PR (Pull Request) on GitHub and Terminal  
      i. GitHub: "Pull Requests" tab.  
     ii. Select "New Pull Request".  
    iii. Comparing changes: select "base" branch.  
     iv.  Select "Compare" branch.  
      v. GitHub may say in green: "Able to merge."  
     vi. Type description, Click "Start Pull Request"  
    vii. New page may say: "Update re: branching ##, with four tabs:  
         * Conversation  
         * Commits  
         * Checks  
         * File changes  
   viii. In "File changes", all changes are visible  
      * Press "+" on any line of code to comment.  
      * Reply to comments, click "Resolve conversation".  
      * If you don't have permissions on branch, must "Resolve conversation" before merging.  
     ix.  In "Conversation" tab, click "Merge pull request"  
      x. Merge successful  
      * GitHub options deleting new branch.  Delete it: Generally, delete off branches on GitHub and locally after merging them to main code.  
     xi. In local terminal, delete off branch:  
         * git branch  
         * git branch -d branchToDelete  
   3. Merge Conflicts  
      * When? Many people changes same files simultaneously.  
      * Manual merge required  
     ii. Create new sub-branch in git and check it.  
         * git branch newBranchName  
         * git status  
         * git diff   
    iii. Conflict occurs after new code entered in master branch on same line as code in sub-branch AND THEN attempt switch branch to newBranchName without committing modified file to master branch.  
      * Option: "stash" changes without committing them, not shown in this tutorial.  
      * Hence, commit modified file to master, check status first:  
         * git status  
     iv. To "commit" an update, include "-am" - add message - (instead of "-m") to modify a file.  
      * Commit the update to master branch:  
         * git commit -am "Your update message here."  
      v. Switch to newBranchName  
         * git checkout newBranchName  
     iv. Compare newBranchName changes with master branch  
         * git diff master  



   n. Completed merge in GitHub?  
         i. In local repo:  
         * git pull  
         * Or, if upstream not set
         * git pull origin master
         * Or, git pull origin yourMasterBranchName
