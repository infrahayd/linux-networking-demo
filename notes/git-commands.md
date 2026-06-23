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

## Repository Status

`git status`

* Show:

  * Current branch
  * Modified files
  * Staged files
  * Untracked files
* Usually the first command to run when checking repository state.

---

## Staging Files

`git add [file]`

* Add a file to the staging area.
* Staged files will be included in the next commit.

Example:

```bash id="g1"
git add README.md
```

---

## Branch Management

`git branch`

* Show all local branches.
* `*` indicates the currently checked-out branch.

Example:

```text id="g2"
* master
  docker-notes
```

---

`git branch [branch-name]`

* Create a new branch.
* Does not switch to it.

Example:

```bash id="g3"
git branch docker-notes
```

---

`git checkout [branch-name]`

* Switch to another branch.

Example:

```bash id="g4"
git checkout docker-notes
```

---

`git checkout -b [branch-name]`

* Create a new branch and switch to it immediately.

Example:

```bash id="g5"
git checkout -b docker-notes
```

---

`git switch -c [branch-name]`

* Modern version of `git checkout -b`.

Example:

```bash id="g6"
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

```bash id="g7"
git commit -m "Add Docker notes"
```

---

`git commit -a -m "message"`

Flags:

* `-a` → Automatically stage modified tracked files before committing.
* Does **not** stage new untracked files.
* `-m` → Commit message.

Example:

```bash id="g8"
git commit -a -m "Update README"
```

---

## Viewing History

`git log`

* Show commit history.

Useful flags:

`git log --oneline`

* Compact commit history.

---

## Comparing Changes

`git diff`

* Show differences between:

  * Working directory
  * Staging area

In other words:

```text id="g9"
What changed since the last git add?
```

---

`git diff --staged`

* Show differences between:

  * Staging area
  * Most recent commit

In other words:

```text id="g10"
What will be committed next?
```

---

## Pushing Changes

`git push`

* Upload commits to the remote repository.

Works after an upstream relationship has already been configured.

---

`git push -u origin master`

Flags:

* `-u` → Set upstream tracking relationship.

Arguments:

* `origin` → Remote repository name.
* `master` → Branch being pushed.

Example:

```bash id="g11"
git push -u origin master
```

Meaning:

```text id="g12"
Push local master
to remote origin/master
and remember this relationship
```

Afterward:

```bash id="g13"
git push
git pull
```

will automatically know which branch to use.

---

## Remote Repositories

`git remote -v`

Flags:

* `-v` → Verbose.

* Show remote repository URLs.

Example:

```text id="g14"
origin  git@github.com:user/repo.git (fetch)
origin  git@github.com:user/repo.git (push)
```

---

## Pulling Changes

`git pull`

* Download changes from the remote repository.
* Merge them into the current branch.

Think:

```text id="g15"
GitHub → Local repository
```

---

## Amending Commits

`git commit --amend`

* Replace the most recent commit.
* Can change:

  * Commit message
  * Staged content
* Creates a new commit that replaces the old one.

---

`git commit --amend --reset-author`

* Replace the most recent commit.
* Update author information using current Git configuration.
* Useful after fixing incorrect name or email settings.

Think:

```text id="g16"
Replace last commit
with same content
but new author information
```

