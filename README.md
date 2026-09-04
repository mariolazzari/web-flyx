# Learn Git

## Setup

### Install

```sh
brew update
brew install git
git version
```

### RTFM

[Docs](https://git-scm.com/docs)

```sh
git help git
```

Shortcuts for the manual:

- q: Quits the manual
- j: One line down
- k: One line up
- d: Half page down
- u: Half page up
- /<term>: Search for "term" (e.g. /OPTIONS)
- n: Next search term
- N: Previous search term

### Config

```sh
git config get user.name
git config get user.email
git config set --global user.name "github_username_here"
git config set --global user.email "email@example.com"
cat ~/.gitconfig
```

## Repositories

### Config

```sh
mkdir webflyx
cd webflyx
git init
ls -a # .git
```

### Status

```sh
git status
```

### Staging

```sh
git add contents.md
git status
```

### Commit

```sh
git  commit -m "A: add contents.md"
git status
```

### Log

[Git log](https://git-scm.com/docs/git-log)

```sh
git log 
git --no-pager log -n 10
```
## Internals

### Hashes

[Commit](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects#_git_commit_objects)
[SHA-1](https://en.wikipedia.org/wiki/SHA-1)

Commit hashes are derived from their content changes and:

- The commit message
- The author's name and email
- The date and time
- Parent (previous) commit hashes

```sh
git log -n 10
ls -l .git/objects
ls -al .git/objects/XX/
```

### Object file

[cat](https://man7.org/linux/man-pages/man1/cat.1.html)
[xxd](https://linux.die.net/man/1/xxd)

```sh
cat <path-to-file-from-before>
xxd <path-to-file-from-before>
```

### Cat file

```sh
git log -1
git cat-file -p <hash>
```

### Trees and Blobs

- *tree*: git's way of storing a directory
- *blob*: git's way of storing a file

## Config

### Git config

```sh
git config set --global user.name "ThePrimeagen"
git config set --global user.email "the.primeagen@aol.com"

git config set --local webflyx.ceo  "ThePrimeagen"
git config set --local webflyx.cto "TheLaneagen"
git config set --local webflyx.valuation "mid"

git config list --local
```

### Get

```sh
git config get user.name
git config get webflyx.ceo
git config get webflyx.valuation
```

### Unset

```sh
git config unset webflyx.cto
git config unset webflyx
```

### Duplicates

```sh
git config set --append webflyx.ceo "Warren"
git config set --append webflyx.ceo "Carson"
git config set --append webflyx.ceo "Sarah"
git config list --local
git config unset --all webflyx.ceo
```

### Remove section

```sh
git config remove-section webflyx
```

### Locations

There are several locations where Git can be configured. From more general to more specific, they are:

- system: /etc/gitconfig, a file that configures Git for all users on the system
- global: ~/.gitconfig, a file that configures Git for all projects of a user
- local: .git/config, a file that configures Git for a specific project
- worktree: .git/config.worktree, a file that configures Git for part of a project

## Branching

### Branch

```sh
git branch
```

### Default branch

```sh
git branch -m oldname newname
git config set --global init.defaultBranch main
git branch
```

### New brnch

```sh
git branch my_new_branch
git switch -c my_new_branch
```

### Switching branches

```sh
git switch prime
# or, the old way:
git checkout prime
```

Log flags

As you know, git log shows you the history of commits in your repo. There are a few flags I like to use from time to time to make the output easier to read.

The first is --decorate. It can be one of:
- short (the default)
- full (shows the full ref name)
- no (no decoration)

```sh
git log --oneline
```

## Merge

### Merge

[Doc](https://git-scm.com/docs/git-merge)

```sh
git switch main
git merge feature_1
```

### Fast forward merge

```sh
git branch -d add_classics
git branch update_titles
```
