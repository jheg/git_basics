# README #

This repo is used to for the sole purpose of me learning git and github.

I've:
- created a directory 
$ mkdir git_basics

- added a readme and license
$ echo '# README #' > README.md
$ echo '# LICENSE #' > LICENSE.md

- Initialised the local root directory as a repo 
$ git init

- created a sub dir called db
$ mkdir db
- created an empty database file 
$ touch development.sqlite3

- added a .gitignore file
$ touch .gitignore
- added the db file to .gitignore
# ignore all db files with the .sqlite3 file extension
db/*.sqlite3

- added the files for staging 
$ git add .gitignore README.md LICENSE.md
- committed the files 
$ git commit -m 'committing initial project files'

- Viewed the commit log file
$ git log

 - Viewed the current git status of my repo
 $ git status (git s for short if you have written the alias in ~/.gitconfig:
 [alias]
  s = status

- Created a remote repo on github and then linked it to my local repo
$ git remote add origin [repo_url.git]
- pushed my local repo to the remote repo and set up to track so i can jsut do git push
$ git push -u origin master

- fetched the remote repo to and checked for changes
$ git fetch
$ git diff master origin/master

- pulled any changes from remote into my local repo (merged)
$ git pull

- made changes locally, added, committed and pushed to remote repo 
$ git add README.md
$ git commit -m 'added progress to README.md'
$ git push



