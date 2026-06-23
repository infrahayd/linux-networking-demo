# Do "gh [command] [subcommand] --help" for more info.

# Authentication
gh auth login
- logs you in

gh auth status
- displays authentication status

# Repository Management
gh repo create [name]
- creates a repository

gh repo clone [owner/repo]
- clone a repository

gh repo view
- show repository information

gh repo view --web
- open repository in a browser

# Pull Requests
gh pr create
- --base [branch] to merge into the specified branch
- create a pull request

gh pr list 
- list pull requests

gh pr view
- view pull request details

- list pull requests in browser

gh pr merge
- merge a pull request

# Issues
gh issue list
- listst issues

gh issue create
- creates an issue

gh issue view [number]
- view issue details

# Help
gh help
- displays help

gh help pr
- displays help for pull request commands

gh help repo
- displays help for repository commands
