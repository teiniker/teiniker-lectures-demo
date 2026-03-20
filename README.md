# Git 

Remote changes...

## Introduction

Git is a distributed version control system used to track changes in source code and other text-based files. It allows developers to work on the same project concurrently, keep a history of changes, and return to earlier versions when necessary.

Core concepts:

- `repository`: A directory managed by Git.
- `commit`: A snapshot of tracked files at a specific point in time.
- `branch`: An independent line of development.
- `working tree`: The files currently checked out on disk.
- `staging area`: The set of changes selected for the next commit.
- `remote`: A shared repository hosted on another machine or service such as GitHub or GitLab.

Typical Git workflow:

1. Create or clone a repository.
2. Modify files in the working tree.
3. Stage selected changes with `git add`.
4. Save them in history with `git commit`.
5. Share or integrate changes via a remote repository.

## Local Git Repo

The following commands show a basic local workflow.

Create a new repository:

```bash
mkdir demo-project
cd demo-project
git init
```

Check the current state of the repository:

```bash
git status
```

Create a file and stage it:

```bash
echo "# Demo Project" > README.md
git add README.md
```

Commit the staged change:

```bash
git commit -m "Add initial README"
```

Modify a file and inspect the difference:

```bash
echo "Some description" >> README.md
git diff
```

Stage and commit the update:

```bash
git add README.md
git commit -m "Update README with project description"
```

Review history:

```bash
git log --oneline --graph
```

Create and switch to a feature branch:

```bash
git switch -c feature/add-license
```

Merge the feature branch back into the main branch:

```bash
git switch main
git merge feature/add-license
```


## Remote Git Repo

Remote repositories are used to share work with others and to back up project history.

Clone an existing remote repository:

```bash
git clone https://github.com/example/project.git
cd project
```

Show configured remotes:

```bash
git remote -v
```

Add a remote to an existing local repository:

```bash
git remote add origin https://github.com/example/project.git
```

Push the current branch to the remote for the first time:

```bash
git push -u origin main
```

Fetch changes from the remote without merging them:

```bash
git fetch origin
```

Pull and integrate the latest changes from the remote branch:

```bash
git pull origin main
```

Push local commits to the remote:

```bash
git push origin main
```

Push a feature branch and open it for collaboration:

```bash
git switch -c feature/update-docs
git push -u origin feature/update-docs
```

Useful collaboration commands:

- `git branch -a` lists local and remote-tracking branches.
- `git remote show origin` displays details about the remote.
- `git pull --rebase` replays local commits on top of fetched remote commits.
- `git push --tags` uploads annotated tags.


## References

Useful online references:

- Git documentation: <https://git-scm.com/doc>
- Pro Git book: <https://git-scm.com/book/en/v2>
- Git reference manual: <https://git-scm.com/docs>
- GitHub Git handbook: <https://docs.github.com/en/get-started/using-git/about-git>
- Atlassian Git tutorials: <https://www.atlassian.com/git/tutorials>
