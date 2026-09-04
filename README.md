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
