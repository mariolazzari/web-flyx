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
