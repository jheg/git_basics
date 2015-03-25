# MY GIT BASICS edited by jheg locally #


This repo is used to for the sole purpose of me learning git and github.

I've:
- created a directory<br /> 
$ mkdir git_basics<br />

- added a readme and license<br />
$ echo '# README #' > README.md<br />
$ echo '# LICENSE #' > LICENSE.md<br />

- Initialised the local root directory as a repo<br /> 
$ git init<br />

- created a sub dir called db<br />
$ mkdir db<br />
- created an empty database file<br />
$ touch development.sqlite3<br q/>

- added a .gitignore file<br />
$ touch .gitignore<br />
- added the db file to .gitignore<br />

db/*.sqlite3<br />

- added the files for staging <br />
$ git add .gitignore README.md LICENSE.md<br />
- committed the files <br />
$ git commit -m 'committing initial project files'<br />

- Viewed the commit log file<br />
$ git log<br />

- Viewed the current git status of my repo<br />
$ git status (git s for short if you have written the alias in ~/.gitconfig:<br />
[alias]<br />
s = status<br />

- Created a remote repo on github and then linked it to my local repo<br />
$ git remote add origin [repo_url.git]<br />
- pushed my local repo to the remote repo and set up to track so i can just do git push<br />
$ git push -u origin master<br />

- fetched the remote repo to and checked for changes<br />
$ git fetch<br />
$ git diff master origin/master<br />

- pulled any changes from remote into my local repo (merged)<br />
$ git pull<br />

- made changes locally, added, committed and pushed to remote repo <br />
$ git add README.md<br />
$ git commit -m 'added progress to README.md'<br />
$ git push<br />

- learned that when wanting to pull a remote repo that you don't yet have a repo set up locally to use<br />
$ git clone [url_of_repo.git] [whatever_you_name_your_local_repo]<br />
- clones the rails remote repo to a local dir called rails as i didnt specify a dir<br />
$ git clone https://github.com/rails/rails.git<br />

<h1>Branching</h1>

- create and switch to new branch<br /> 
$ git checkout -b feature_x<br />

- Switch back to master<br />
$ git checkout master<br />

- view all branches locally<br />
$ git branch<br />

- push new branch to remote repo<br />
$ git push origin feature_x<br />

- delete a branch LOCALLY<br />
$ git branch -d feature_x<br />
- delete a branch on REMOTE<br />
$ git push origin --delete feature_x<br />

<h2>Merge a newly created branch back into master when both have changed since the branch</h2>

- create a branch<br />
$ git checkout -b add_headline_to_readme<br />

- added headline to readme.md file in new branch and committed and pushed to remote<br />
$ git s<br />
$ git add README.md<br />
$ git commit -m 'added headline to readme.md'<br />
$ git push origin add_headline_to_readme<br />

- switched back to master branch<br />
$ git checkout master<br />

- added footer text to readme.md in master and committed and pushed to remote repo<br />
$ git add README.md<br />
$ commit -m 'added footer text to readme.md'<br />
$ git push<br />

<h2>The merge</h2>
<p>At this point there are two branches that are slightly different and both have something the other has not. I'll merge the two into master and delete the add_headline_to_readme branch</p>
<h3>LOCAL MERGE</h3>
- from the master branch<br /> 
$ git merge add_headline_to_readme<br />
- 1. press 'i'
- 2. enter merge message
- 3. press 'esc'
- 4. type ':wq' and press enter

<p>at this point the local branch master says something like 'Your branch is ahead of origin/master by 2 commits'</p>

<h3>update REMOTE</h3>
- from the merged local master branch<br />
$ git add readme.md<br />
$ git commit -m 'updated readme'<br />
$ git push<br />
- deleted the add_headline_to_readme branch locally and remotely<br />
$ git branch -d add_headline_to_readme<br />
$ git push origin --delete add_headline_to_readme<br />

<h1>Merge conflicts</h1>
<p>The scenario is that I'm working on master and have made a change (I've changed the readme headline again) and a friend has done the same albeit with a different headline. I'm going to simulate this by editing the file on github and then editing the file locally on my master repo and see what happens. I'm expecting to get a merge conflict and have to manually decide which merge wins.</p>

- first off i'll get my local repo upto date and in sync with remote<br />
- next on github I edited the readme file to # MY GIT BASICS edited by friend # and commited<br />
- I then made a similar change locally altering the title to # MY GIT BASICS edited by jheg locally # added, committed and TRIED to push but got an rejected message:<br />

<p>To https://github.com/jheg/git_basics.git<br />
 ! [rejected]        master -> master (fetch first)<br />
error: failed to push some refs to 'https://github.com/jheg/git_basics.git'<br />
hint: Updates were rejected because the remote contains work that you do<br />
hint: not have locally. This is usually caused by another repository pushing<br />
hint: to the same ref. You may want to first integrate the remote changes<br />
hint: (e.g., 'git pull ...') before pushing again.</p>

<h2>Dealing with the conlict</h2>
- Fetch the remote<br />
$ git fetch<br />
- pull the remote<br />
$ git pull<br />

<p>back in my editor I now see something like this:</p>


<p><<<<<<< HEAD<br />
# MY GIT BASICS edited by jheg locally #<br />
=======<br />
# MY GIT BASICS edited by friend #<br />
>>>>>>> 1013e80aad96485365264f8540611210c657ee52</p>

<p>dealing with the conflict is just a case of deleting what I didn't want and then add/commit/push to update the branch and decide the fate of the conflicts</p>

<hr>
<footer>because it's so painfull not knowing</footer>









