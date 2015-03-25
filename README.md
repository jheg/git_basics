# README #

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
$ touch development.sqlite3<br />

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

- delete a branch LOCALLY<br />
$ git branch -d feature_x<br />
- delete a branch on REMOTE<br />
$ git push origin --delete feature_x<br />











