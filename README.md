*Interactive Rebase: Tool for optimizing & cleaning up your commit history:*
change a commit's message | delete commits | reorder commits | combine multiple | commits into one | edit/split an existing commit into new ones'

git rebase -i HEAD~3        // ~3 signifies how far a commit we are going back

*Note:* Do not use interactive rebase you've already pushed/shared on a remote repository. Instead use it to clear local commit history before merging into a shared team branch

*#2 Cherry-Picking: Allows you to select individual commits* 
Here we commit only c2 and not c4

c1 --------- c3 ---------- c2 (Branch-A)
\    _______________________|
 \  /
  c2 -------------- c4 ---------- (Branch-B)

Eg. if we commit to the wrong branch: 

*Step 1: Checkout to the branch*

git checkout <branch-name>

*Step 2: got to the particular commit*

git cherry-pick <commit-hash>

To cleanUp the master Branch:

*Step 1:*
git checkout <master_branch>

*Step 2:*
git reset --hard HEAD ~1  // This will cleanUp the last commit


*#3 Reflog: A protocol of Head movement pointers*

*To remove last commits and a particular commit the last one:*

git reset --hard <commit_hash>

*Now to get back those deleted commits, we get into:*

git reflog

*To undo the last action:*

git reset <commit_hash> 


*#4 Submodules: Git repo inside a git repo*  

Use it to download third party lib and keep it separated from your own code

*#5 Search & find:*

Filtering your commit history: 

*by date --before / --after:* git log --after="2024-7-1" 

*Also we can combine:* git log --after="2024-7-1" --before="2024-7-5" 

*by message --grep:* git log --grep="refactor" 

*by author --author:* git log --grep="author_name" --before="2024-7-5"    

*by file --<filename>:* git log -- <file-name>

*by branch <branch-A>:* git log <branch-name>..main




















