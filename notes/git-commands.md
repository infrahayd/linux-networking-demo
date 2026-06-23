A remote repository is a repository stored on GitHub.
Branches are workspaces to commit changes.

git status
- lists branch, changes, stage (what will be commited)

git add [file]
- adds file to stage to be commited

git branch
- displays current branch
- asterisk (*) means current branch

git branch [new name]
- creates a new branch, like a test branch as an example

git checkout [branch name]
- switch to new branch, commits now to go to whichever branch name was specified

git checkout -b [branch name]
- creates a new branch and switches to it at the same time

git switch -c [branch name]
- the modern version of git checkout -b <branch name>

git commit
- -a -> automatically stage changed files before commit
- -m -> message e.g. "This is a message"


git log
- displays commit history

git diff
- shows changes in the working directory versus the stage

git diff --staged
- shows differences in the staging area vs the latest commit

git push
- uploads the current repo to github

git push -u origin master (or main)
- origin is usually the name of the remote repository
- master or main is typically the current branch
- -u memorizes the relationship between the two so you can just do git push in the future, same for git pull

git remote -v
- -v -> meaning verbose as per usual
- shows information about the remote repo

git pull
- downloads changes from github to local repo

git commit --amend --reset-author
- replaces the most recent commit with new author metadata
