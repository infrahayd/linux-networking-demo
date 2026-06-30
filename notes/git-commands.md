# Git Commands

## Basic Concepts

### Remote Repository

* A repository hosted on another machine, usually GitHub.
* Your local repository can push changes to and pull changes from a remote repository.

### Branch

* A branch is an independent line of development.
* Think of branches as separate workspaces that can have different commits.
* New commits are added to the branch you currently have checked out.

---

## Initializing a Repository

`git init`

* Initialize the current directory as a Git repository.
* Creates the hidden `.git` directory, which stores all Git metadata and commit history.

Example:

```bash
git init
```

---

## Repository Status

`git status`

* Show:

  * Current branch.
  * Modified files.
  * Staged files.
  * Untracked files.
* Usually the first command to run when checking repository state.

---

## Staging Files

`git add [file]`

* Add a file to the staging area.
* Staged files will be included in the next commit.

Example:

```bash
git add README.md
```

---

## Branch Management

`git branch`

* Show all local branches.
* `*` indicates the currently checked-out branch.

Example:

```text
* master
  docker-notes
```

---

`git branch [branch-name]`

* Create a new branch.
* Does not switch to it.

Example:

```bash
git branch docker-notes
```

---

`git checkout [branch-name]`

* Switch to another branch.

Example:

```bash
git checkout docker-notes
```

---

`git checkout -b [branch-name]`

* Create a new branch and switch to it immediately.

Example:

```bash
git checkout -b docker-notes
```

---

`git switch -c [branch-name]`

* Modern version of `git checkout -b`.

Example:

```bash
git switch -c docker-notes
```

---

## Creating Commits

`git commit`

* Create a commit from the staging area.

---

`git commit -m "message"`

Flags:

* `-m` → Commit message.

Example:

```bash
git commit -m "Add Docker notes"
```

---

`git commit -a -m "message"`

Flags:

* `-a` → Automatically stage modified tracked files before committing.
* Does **not** stage new untracked files.
* `-m` → Commit message.

Example:

```bash
git commit -a -m "Update README"
```

---

## Viewing History

`git log`

* Show commit history.

Useful flag:

```bash
git log --oneline
```

* Display a compact commit history.

---

## Comparing Changes

`git diff`

* Show differences between:

  * Working directory.
  * Staging area.

Think:

```text
What has changed but is not staged yet?
```

---

`git diff --staged`

* Show differences between:

  * Staging area.
  * Most recent commit.

Think:

```text
What will be committed next?
```

---

## Remote Repositories

`git remote -v`

Flags:

* `-v` → Verbose.

* Show all configured remote repositories and their URLs.

Example:

```text
origin  git@github.com:user/repo.git (fetch)
origin  git@github.com:user/repo.git (push)
```

---

`git remote add origin [url]`

* Add a remote repository.
* `origin` is the conventional name for the primary remote.

Example:

```bash
git remote add origin git@github.com:user/repo.git
```

---

`git remote set-url origin [new-url]`

* Replace the URL associated with an existing remote.

Example:

```bash
git remote set-url origin git@github.com:user/new-repo.git
```

---

`git remote remove origin`

* Remove the configured remote named `origin`.

Useful if the remote was configured incorrectly.

---

## Pushing Changes

`git push`

* Upload commits to the configured remote repository.

Works after an upstream relationship has already been configured.

---

`git push -u origin master`

Flags:

* `-u` → Set the upstream tracking relationship.

Arguments:

* `origin` → Remote repository name.
* `master` (or `main`) → Branch being pushed.

Example:

```bash
git push -u origin master
```

Meaning:

```text
Push local master
to remote origin/master
and remember this relationship.
```

Afterward:

```bash
git push
git pull
```

will automatically know which remote branch to use.

---

## Pulling Changes

`git pull`

* Download changes from the remote repository.
* Merge them into the current branch.

Think:

```text
GitHub → Local repository
```

---

## Branch Tracking

`git branch -vv`

Flags:

* `-vv` → Show additional information.

Displays:

* Current branch.
* Upstream (remote) branch.
* Latest commit.
* Whether the local branch is ahead or behind the remote.

Example:

```text
* main 1234567 [origin/main] Initial commit
```

---

## Amending Commits

`git commit --amend`

* Replace the most recent commit.
* Can change:

  * Commit message.
  * Staged content.
* Creates a new commit that replaces the old one.

---

`git commit --amend --reset-author`

* Replace the most recent commit.
* Update author information using the current Git configuration.
* Useful after fixing an incorrect Git username or email.

Think:

```text
Replace the last commit
with the same content
but new author information.
```
