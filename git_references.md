# git references

## basic glossary commands
* `git init` : Initializes current directory as Git repository
* `git status` : Shows status of a tree, including modified files
*  `git add` : Adds files to staging area
*  `git commit` : Records changes of files from staging area to repository
*  `git log` : Shows record of commits with messages and SHA identifiers
*  `git reset` : Resets `HEAD` to a specific commit
*  `git checkout` : Resotrs working tree files
*  reference https://www.varonis.com/blog/revert-a-commit-in-git

## create repository
1. Create repository from command line https://www.howtogeek.com/devops/how-to-create-and-manage-a-github-repository-from-the-command-line/ OR
1. Create repository on GitHub with a new name
2. In local location where you want the folder use, do

* ``git init``

## add a change to git
* ``git add <filename>``
* ``git commit -m "comment on change added"``

## how to revert a commit
*   `git reset <git-commit-log-hash>` Find commit log hash with `git log`
* refence https://www.varonis.com/blog/revert-a-commit-in-git


## add change to github repo
* ``git push origin <main>``
** ``<main>`` is the branch name

## add a new remote to git repo
* ``git remote add <unique-remote-name> <remote-url>``
* from https://articles.assembla.com/en/articles/1136998-how-to-add-a-new-remote-to-your-git-repo#:~:text=To%20add%20a%20new%20remote%2C%20use%20the%20git%20remote%20add,tab%20of%20your%20Git%20repo
* https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes - very helpful stuff


## origin and upstream differences on git with branches
* https://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github
* https://devconnected.com/how-to-set-upstream-branch-on-git/ - found this one very helpful
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
* 'Git Feature Branch Workflow' https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow - very helpful
* 'Git Branching - Basic Branching and Merging' https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging
* 'Git Branching and Merging: A Step-By-Step Guide' https://www.varonis.com/blog/git-branching
* 'How to Merge in Git: Remote and Local Git Repositories Tutorial' https://www.varonis.com/blog/how-to-merge-in-git

## merging branches after fetch
* https://stackoverflow.com/questions/14513278/git-merge-after-fetch-how-exactly
* `git merge origin/master` should work. Since  master   is usually a tracking branch, you could also do `git pull` from that branch and it will do a fetch & merge for you.

    If you have local changes on your `master` that aren't reflected on `origin`, you might want `git rebase origin/master` to make sure your commits are 'on top'.
    Do one or the other, not both. Which to choose depends on the outcome you're after, but rebase is usually what you want.
    
## mergin select files or folders from one branch to another
* `git checkout source_branch <path on source branch>`
* reference https://jasonrudolph.com/blog/2009/02/25/git-tip-how-to-merge-specific-files-from-another-branch/
* `git checkout dev -- path/to/your/file` # for one or two files - assuming you are in another branch than dev
* `git checkout dev -- path/to/your/folder` # for a folder
* `git checkout <commit_hash> <relative_path_to_file_or_dir>` # files and folder from commit hash of another branch
* reference https://www.tutsway.com/how-to-copy-file-or-folder-from-one-branch-to-another-in-git.php

## push/pull from multiple remote locations
* https://stackoverflow.com/questions/849308/how-can-i-pull-push-from-multiple-remote-locations
* You can configure multiple remote repositories with the `git remote` command:

            git remote add alt alt-machine:/path/to/repo
    To fetch from all the configured remotes and update tracking branches, but not merge into `HEAD`, do:

            git remote update
    If it's not currently connected to one of the remotes, it will take time out or throw an error, and go on to the next. You'll have to manually merge from the fetched repositories, or `cherry-pick`, depending on how you want to organize collecting changes.
    To fetch the master branch from alt and pull it into your current head, do:
    
            git pull alt master
    So in fact `git pull` is almost shorthand for `git pull origin HEAD` (actually it looks in the config file to determine this, but you get the idea).
    For pushing updates, you have to do that to each repo manually. A push was, I think, designed with the central-repository workflow in mind.



## editing .gitignore
* https://www.atlassian.com/git/tutorials/saving-changes/gitignore
* `echo file >> .gitignore`

## removing deleted file from `git status`
* https://stackoverflow.com/questions/12987907/git-how-to-commit-a-manually-deleted-file
* `git rm file`

## deleting git branch
* To delete a local branch in Git, you simply run:
        
        git branch -d <branch-name>  
        git branch -D <branch-name>  # Unmerged changes d -> D
        git push --delete <remote name> <branch name>  # delete a remote branch
* Example
        mkdir demo
        cd demo
        git init
        
        echo hello world > file.txt
        git add file.txt
        git commit -m “Add first file” 
        
        # create second branch called 'new'
        git branch new 
        git branch -d new # delete right away
        # returns 'Deleted branch new (was c9bd965).'
        
        # Create new branch and switch to it
        git switch -c newer
        # add some commits to 'newer'
        echo hello world > file2 && git add . && git commit -m "Add file2"
        echo hello world > file3 && git add . && git commit -m "Add file3"
        
        # Go back to original branch
        git switch main
        
        # Try to delete 'newer'
        git branch -d newer
        # returns 'error: The branch ‘newer’ is not fully merged. If you are sure you want to delete it, run 'git branch -D newer.’'
        git branch -D newer # delete 'newer'
        
        # to delete remote branch see reference
* reference https://www.cloudbees.com/blog/git-delete-branch-how-to-for-both-local-and-remote


## clearing git history
* https://www.systutorials.com/how-to-clear-git-history-in-local-and-remote-branches/
