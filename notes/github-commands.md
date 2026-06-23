# GitHub CLI (gh)

## Getting Help

`gh [command] [subcommand] --help`

* Show detailed help for a specific command.

Examples:

```bash
gh pr --help
gh repo create --help
```

---

`gh help`

* Show general help.

---

`gh help pr`

* Show help for pull request commands.

---

`gh help repo`

* Show help for repository commands.

---

# Authentication

`gh auth login`

* Log into GitHub.
* Connect the GitHub CLI to your GitHub account.

---

`gh auth status`

* Show authentication status.
* Display which account is currently logged in.

---

`gh auth logout`

* Log out of GitHub CLI.

---

# Repository Management

`gh repo create [name]`

* Create a new GitHub repository.

Example:

```bash
gh repo create linux-networking-demo
```

Useful flags:

`--public`

* Create a public repository.

`--private`

* Create a private repository.

`--source .`

* Create a repository from the current directory.

`--push`

* Push local commits immediately after creation.

---

`gh repo clone [owner/repo]`

* Clone a GitHub repository.

Example:

```bash
gh repo clone infrahayd/linux-networking-demo
```

---

`gh repo view`

* Show repository information.

---

`gh repo view --web`

* Open the repository in your default browser.

---

# Pull Requests

## Creating Pull Requests

`gh pr create`

* Create a pull request.

Useful flags:

`--base [branch]`

* Branch you want to merge into.

`--head [branch]`

* Branch containing your changes.

Example:

```bash
gh pr create --base master --head docker-notes
```

---

## Viewing Pull Requests

`gh pr list`

* List pull requests.

Useful flags:

`--state open`

* Show open pull requests.

`--state closed`

* Show closed pull requests.

---

`gh pr view`

* View pull request details.

---

`gh pr view --web`

* Open the pull request in a browser.

---

## Merging Pull Requests

`gh pr merge`

* Merge a pull request.

Useful flags:

`--merge`

* Create a merge commit.

Think:

```text
Preserve all commits exactly as they happened.
```

---

`--squash`

* Combine all PR commits into a single commit.

Think:

```text
Turn:
Fix typo
Fix typo again
Update notes

into:

Update notes
```

---

`--rebase`

* Replay commits on top of the target branch.
* Creates a linear history without merge commits.

---

Example:

```bash
gh pr merge --squash
```

---

# Issues

`gh issue list`

* List repository issues.

---

`gh issue create`

* Create a new issue.

Example:

```bash
gh issue create
```

---

`gh issue view [number]`

* View issue details.

Example:

```bash
gh issue view 5
```

---

`gh issue close [number]`

* Close an issue.

Example:

```bash
gh issue close 5
```

---

# Useful Commands

`gh workflow list`

* List GitHub Actions workflows.

---

`gh workflow run [workflow]`

* Run a GitHub Actions workflow manually.

---

`gh release list`

* List repository releases.

---

`gh release create [tag]`

* Create a GitHub release.

Example:

```bash
gh release create v1.0
```

---

# Commands You'll Use Most

`gh auth login`

* Log in.

---

`gh repo create`

* Create a repository.

---

`gh repo view --web`

* Open repository in browser.

---

`gh pr create`

* Create a pull request.

---

`gh pr list`

* List pull requests.

---

`gh pr view`

* View pull request details.

---

`gh pr merge --squash`

* Merge pull request as a single commit.

---

`gh issue list`

* List issues.

---

`gh issue create`

* Create an issue.

