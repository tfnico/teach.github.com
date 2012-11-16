---
layout: bare
title: Deutsche ePost Git Presentation
description: Deutsche ePost Git presentation notes and resources
tags: [notes, inperson, class]
eventdate: 2012-11-13
---

# {{ page.title }}
2012-11-13

## Instructors
* Matthew McCullough ([Twitter](http://twitter.com/matthewmccull), [GitHub](https://github.com/matthewmccullough))
* Kevin Sawicki ([Twitter](http://twitter.com/kevinsawicki), [GitHub](https://github.com/kevinsawicki))
* Thomas Ferris Nicolaisen ([Twitter](http://twitter.com/tfnico), [GitHub](https://github.com/tfnico), [homepage](http://www.tfnico.com))

## Resources

* [The Git Parable (Git Described Non-technically)](http://tom.preston-werner.com/2009/05/19/the-git-parable.html)
* [GitHub Basics Webinar Recording](http://teach.github.com/classnotes/2012-11-05-git-github-basics-online)
* [Ask questions of the GitHub Training team](https://github.com/githubtraining/feedback)
* [GitSlave - An Alternative to Git Submodules](http://gitslave.sourceforge.net)
* [Free Online Classes from GitHub Training](http://training.github.com/web/free-classes/)


## Git Basics
* New, modified, moved, renamed, and deleted files are all added to the "shopping cart"
* Add by patch
    * `git add -p <filenamepattern>`
* Git commit is transactional

## IDEs, Platforms, Tools

* [Excellent Git support in Eclipse with JGit (Library) and EGit (UI)](http://eclipse.github.com)
* IntelliJ also has excellent Git support.
* Emacs Git mode (the most popular is [magit](http://philjackson.github.com/magit/)).
* There's [fugitive.vim](https://github.com/tpope/vim-fugitive) for Vim, which is included in [Vim-Janus](https://github.com/carlhuda/janus)

## Git GUIs
* [Catalog of Git GUIs](http://pinboard.in/u:matthew.mccullough/t:git+gui)
* EGit for Eclipse
* Smart Git for cross-platform consistency
* GitX on Mac

## Sharing Changes other than through the network
* `git bundle create <filename> <refspec>`
* `git format-patch <refspec>`

## Graph of Commits
* `git log`
* `git log --date-order`
* `git log --topo-order`
* `git log --graph`

Handy `git logtree` alias:
* `git config alias.logtree "log --graph --oneline --decorate --all"`

(Awesome command line tool for browsing log: [Tig](http://jonas.nitro.dk/tig/))

## Navigating to the Tree of a Commit
* `git cat-file -p HEAD^{tree}`

## Rebasing

Configure branch "master" to be rebased when pulling:
* `git config branch.master.rebase true`

Configure automatic rebasing on remote branches (in effect configures rebase=true on any remote branches
that are tracked from now on):
* `git config --global branch.autosetuprebase remote`

## GitHub
* Primary place for open source projects to host code, site
* SpringSource, VMWare, Twitter Bootstrap, Groovy, Eclipse (Mirrored) on GitHub

## Gerrit
* Tool for code review from Google
* Eclipse foundation uses Gerrit for EGit, JGit
* Comparable to pull request on GitHub

## Pull Request
* `request-pull` command in core of Git
* Are you using `git pull --rebase`?
* Can be configured to be default.
* Might want to configure it on a per-project basis.

## Work Flexibility
* Share work in progress
    * Leaving for weekend? Just commit it.
    * Handing work in progress to the person best equipped to handle it.
* Pairing oriented
* Code in alternative locations
    * Train time
    * Cafes
    * Creative workspaces

## Identifying Small Units of Work
* `git cherry-pick <refspec>`
* `git cherry <branchname>` shows what patches from that branch are on this one
* `git show-branch` shows state of merging

## SVN Bridge
* Might prefer cherry picking instead of merging on to Git-mirrored/Subversion branches
* [Thomas' videos and notes on Git + Subversion use](http://www.tfnico.com/presentations/git-and-subversion)

## Branching
* `git merge --no-ff` to preserve the merge commit
* `git checkout feature; git merge master` as a "reverse merge" to bring fixes into the feature branch
* Control the merge message; make it well crafted, not the default
* Maintain linear, especially if syncing back to SVN
* Rebasing supports history clarity

## Rebasing
* Rebase
* Rebase on pull
* Rebase interactive
    * Clean code to history
    * Stitch in time saves nine

## Continuous Integration
* Tooling
    * "Office Talk"
    * http://flurfunk.github.com
    * Jenkins
    * Branch builds
    * Pull request concept
    * Test before merge to 

## Repo Size
* Size
* Performance
* Git Submodules
* Repo tool from Android
* Release cycle loosely linked
* Per OS for 
* [gitslave](http://gitslave.sourceforge.net) (limited Windows support)
* Large binaries
    * git-annex
    * git-media
    * https://github.com/schacon/agitmemnon
    * Submodules
* Installers
    * JDK
    * Assets
    * Postgres

* Deliverable
    * Web app
    * WAR?
    * Integration

## Testing, Metadata

* `git notes
* bisect

## Stash
* `git stash`
* `git stash save "Name of the stash"`
* `git stash apply`
* `git stash pop`

## Fun: Find most frequently use Git command

* [Git Command Frequency of Use](https://coderwall.com/p/-o1nda)

## Command Line History

    git init project1
    cd .git
    touch first.txt
    git commit -m "My first commit"
    
    git ls-files -s --debug
    echo Hello >> first.txt
    git commit -m "My second small change"
    subl first.txt
    git reset HEAD first.txt
    git add -p first.txt
    git commit -m "Part of the changes"
    git add first.txt
    git commit -m"The remainder of the changes"
    
    git log --graph --abbrev-commit --decorate --relative
    git log --graph --abbrev-commit --decorate --relative --order-by-graph
    git help liog
    git help log

    cd project1
    git l2
    git graphlive 10
    git branch feature3
    generaterandomchanges 3 masterbugfix txt
    generaterandomchanges 3 feature txt
    gitx .
    git rebase master
    git log master..feature3
    git merge --no-ff feature3
    git reflog
    git reset --hard 941b046
    git checkout feature3
    git rebase -i 941b046
    git merge feature3
    brew install git-extras
    git summary
    generaterandomchanges 4 sample txt
    git rebase -i HEAD~4
    git show d505
    git show d505:sample4.txt
    git cherry-pick d505
    git commit
    git orphank
    git cherry-pick 43312
    git log -2
    cd ../hellogitworld
    git graphlive 5
    git graphlive 25
    
    generaterandomchanges 2 master txt
    git checkout -b bluecustomer
    git commit -a -m"Blue feature addition"
    git commit -a -
    git commit -a -m"Bug fix"
    git commit -a -m"Feature 2"
    git cherry-pick 88b6481
    git diff
    git mergetool
    git diff --staged
    vim src/Division.groovy
    git commit 
    git log -1 --format=raw
    git cherry
    git cherry bluecustomer
    git checkout -b redcustomer
    git commit -a -m"Red branding 1"
    git commit -a -m"Remove darn swemicolons as a fix"
    git commit -a -m "Red branding again"
    git cherry-pick --abort
    git s
    mate cherrypickexample.txt
    git add cherrypickexample.txt
    git commit -m"On master"
    git cherry-pick 654da80
    gitx
    git log --oneline master..origin/master
    git log --oneline origin/master..master
    git log --graph --all --decorate --oneline --abbrev-commit
    git remote show origin
    
    cp -r hellogitworld hgw1
    cd hgw1
    git remote -v
    git clone https://github.com/githubtrainer/hellogitworld hgw2
    cd hgw2
    generaterandomchanges 2 other txt
    git fetch
    git branch -vvv
    git diff origin/master..master
    git difftool origin/master..master
    git log -p origin/master..master
    git pull
    git reflog 
    git reset --hard 58a6625
    git pull --rebase
    git log --graph --all --decorate --oneline --abbrev-commit
    git rebase -i origin/master
    git stash pop
    git stash save "This is good stuff"
    git stash list
    
    cd eclipse
    vim fix.txt
    git stash save
    cd localclone
    git checkout master
    git reset --hard 
    git status
    git stash branch shouldhavebeenabranch
    git stash apply stash@{3}
    git stash apply stash@{2}
    git stash
    git log --all
    git log --all --graph --oneline
    git log --all --graph --oneline --decorate
    git notes add -m "So you like removing semicolons eh"
    git log
    cd hellogitworld
    git gc
    hub browse
    git notes add -m "One more note for the team"
    git push
    
    git push origin 'refs/notes/*'
    history | grep svn
    git svn clone --stdlayout http://ambientideas.unfuddle.com/svn/ambientideas_sample11-svnscm     exit
    open .
    cd hgwsubexit
    git branch -a
    generaterandomchanges 2 getbeers txt
    git svn dcommit
    git svn info
    git log -4
    git dcommit
    git config --global alias.pushsvn "svn dcommit"
    git pushsvn
    git config --global alias.pullsvn "svn rebase"
    git pullsvn
    cd ..
    svn checkout https://github.com/matthewmccullough/test1/trunk insvnformat
