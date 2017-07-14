
Github containes all of the below
---------------------------------
$ git init
Initialized empty Git repository in /home/hgarcia/Github/.git/

$ git add .
# Adds the files in the local repository and stages them for commit. 
# To unstage a file use:
# 'git reset HEAD YOUR-FILE'

$ git commit -m "First commit"
# Commits the tracked changes and prepares them to be pushed to a remote repository. 
# To remove this commit and modify the file use:
# 'git reset --soft HEAD~1' 
# and commit and add the file again.

$ git remote add origin git@github.com:hernando-garcia/my_project.git
# In Terminal, add the URL for the remote repository where your local repository will be pushed.

$ git remote -v
origin  git@github.com:hernando-garcia/my_project.git (fetch)
origin  git@github.com:hernando-garcia/my_project.git (push)

# Now, if everything is ok in github.com then the following just works:
$ git push origin master
# Pushes the changes in your local repository to remote repository specified as the origin

# Or, it will error with something like:
To git@github.com:hernando-garcia/my_project.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:hernando-garcia/my_project.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first merge the remote changes (e.g.,
hint: 'git pull') before pushing again.

# The following fixes it:
$ git pull git@github.com:hernando-garcia/my_project.git master
From github.com:hernando-garcia/my_project
 * branch            master     -> FETCH_HEAD
Merge made by the 'recursive' strategy.
 Jenkinsfile |  11 ++
 LICENSE     | 674 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 2 files changed, 685 insertions(+)
 create mode 100644 Jenkinsfile
 create mode 100644 LICENSE

# Now you can run the command that failed before
$ git push origin master
Counting objects: 15, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (13/13), done.
Writing objects: 100% (14/14), 2.45 KiB | 0 bytes/s, done.
Total 14 (delta 0), reused 0 (delta 0)
To git@github.com:hernando-garcia/my_project.git
   a81e9f2..7352e02  master -> master
