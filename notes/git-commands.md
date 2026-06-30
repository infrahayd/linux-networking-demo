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

## Viewing Branch Tracking Information

`git branch -vv`

Flags:

* `-vv` → Show additional information.

* Display:

  * Current branch.
  * Upstream (remote) branch.
  * Latest commit.
  * Whether the local branch is ahead or behind the remote.

Example:

```text
* main 1234567 [origin/main] Initial commit
```

---

## Adding a Remote Repository

`git remote add origin [url]`

* Add a remote repository.
* `origin` is the conventional name for the primary remote.

Example:

```bash
git remote add origin git@github.com:user/repo.git
```

---

## Changing a Remote URL

`git remote set-url origin [new-url]`

* Replace the URL associated with an existing remote.

Example:

```bash
git remote set-url origin git@github.com:user/new-repo.git
```

---

## Removing a Remote

`git remote remove origin`

* Remove the configured remote named `origin`.

Useful if the remote was configured incorrectly.

---

## Checking the Current Remote

`git remote -v`

* Show all configured remotes and their URLs.

Example:

```text
origin  git@github.com:user/repo.git (fetch)
origin  git@github.com:user/repo.git (push)
```
