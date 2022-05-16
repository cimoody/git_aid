# git references

## create repository
1. Create repository on GitHub with a new name
2. In local location where you want the folder use, do

* ``git init``


## add a change to git
* ``git add <filename>``
* ``git commit -m "comment on change added"``

## add change to github repo
* ``git push origin <main>``
** ``<main>`` is the branch name

## add a new remote to git repo
* ``git remote add <unique-remote-name> <remote-url>``
* from https://articles.assembla.com/en/articles/1136998-how-to-add-a-new-remote-to-your-git-repo#:~:text=To%20add%20a%20new%20remote%2C%20use%20the%20git%20remote%20add,tab%20of%20your%20Git%20repo

## origin and upstream differences on git with branches
* https://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github
* https://devconnected.com/how-to-set-upstream-branch-on-git/
* Set upstream branch using `git push -u`:
    `git push -u <remote> <branch>`
* Alternatively, use `--set-upstream`:
    `git push --set-upstream <remote> <branch>`
* Switching to new branch `'branch'`:
    `git checkout -b branch`
* Check tracking of all branches:
    `git branch -vv`

## change the URL on a remote git repository
* https://stackoverflow.com/questions/2432764/how-to-change-the-uri-url-for-a-remote-git-repository
        
        git remote -v
        # View existing remotes
        # origin  https://github.com/user/repo.git (fetch)
        # origin  https://github.com/user/repo.git (push)
        
        git remote set-url origin https://github.com/user/repo2.git
        # Change the 'origin' remote's URL
        
        git remote -v
        # Verify new remote URL
        # origin  https://github.com/user/repo2.git (fetch)
        # origin  https://github.com/user/repo2.git (push)

## tutorials and more advanced branching
* 'Git Feature Branch Workflow' https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow
* 'Git Branching - Basic Branching and Merging' https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging
## editing .gitignore
* https://www.atlassian.com/git/tutorials/saving-changes/gitignore
* `echo file >> .gitignore`

## removing deleted file from `git status`
* https://stackoverflow.com/questions/12987907/git-how-to-commit-a-manually-deleted-file
* `git rm file`
