# playground
=========================
This is my GIT playground
========================
#Create Repository

I created a new repository called playground on github via browser

#Clone the repository, do some edits and write them back

The next commands are written local on my computer  

Cloning the repo 
* `git clone https://github.com/hagengraf/playground.git`

The folder playground was created and I have to go in
* `cd playground/`

Status check
* `git status`

I edit a file in the editor nano
(Markup cheat sheet https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* `nano README.md`

Status Check
* `git status`

I commit the changes to origin/master
* `git commit -a`

Status Check
* `git status`

Push changes to repo
* `git push`

#Create a new branch, do some edits and write them back
* `git checkout -b newbranch`
* `nano README.md`
* `git push --set-upstream origin newbranch`

Now you have to make a pull request, merge the changes and delete the branch (if you don't need it anymore)

#Cherry Picking
Imagine you have the master branch and 2 others, let's say newbranch and stable10.
You change something in newbranch and push it to master, create a pull request and merge it.
Now master and newbranch are the same, stable10 is different.
Now comes the cherry picking


* git fetch origin stable10
* git checkout stable10
* git checkout -b backport-<pull request id> (without #)
* git cherry-pick <commit id>
* git push origin backport-<pull request id>


* git checkout -b backport-3
* git cherry-pick 0a59db5
* git push origin backport-3
* git checkout stable10
* pull origin stable10
* git branch -v
* git branch -d backport-3
