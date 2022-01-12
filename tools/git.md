# Git

#### Add changes to last (local) commit  
`git add file(s)`  
`git commit --amend`  

#### Show remote URL
Without Network `git config --get remote.origin.url`  
With Network `git remote show origin`

#### Stash changes away you're not ready to commit yet  
`git stash save "save message"`  
Retrieve them later with  
`git stash list`  
`git stash pop <stash_item_hash>`  

#### Stop tracking and ignore changes to a file/ apply .gitignore to the present/future
Source: [Stackoverflow](https://stackoverflow.com/questions/936249/how-to-stop-tracking-and-ignore-changes-to-a-file-in-git/58208920#58208920)  
commit up-to-date .gitignore (if not already existing), this command must be run on each branch  
`git add .gitignore`  
`git commit -m "Create .gitignore"`  

apply standard git ignore behavior only to current index, not working directory (--cached)  
if this command returns nothing, ensure /.git/info/exclude AND/OR .gitignore exist    
this command must be run on each branch    
`git ls-files -z --ignored --exclude-standard | xargs -0 git rm --cached`  

optionally add anything to the index that was previously ignored but now shouldn't be:    
`git add *`  

commit again, optionally use the --amend flag to merge this commit with the previous one instead of creating 2 commits.`

`git commit -m "re-applied modified .gitignore"`  

other devs who pull after this commit is pushed will see the  newly-.gitignored files DELETED  

#### Links/ Misc
* [A collection of .gitignore templates](https://github.com/github/gitignore)