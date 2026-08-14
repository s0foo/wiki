# Commits & History

## Commits

- List files changed by last commit: `git show --stat`
- Show diff of last commit: `git show`
- Remove last local commit: `git reset --soft HEAD~1`

## Staging

- Stage only tracked files: `git add -u`

## Amend last commit and push

1. Amend: `git commit --amend`
2. Force push: `git push --force`

## Remove last push commit

1. Start interactive rebase: `git rebase -i HEAD~1`
2. Select `drop` on the commit to remove.
3. Force push: `git push --force`

## Diff

- List files changed between two commits:
  `git diff --name-only <hash> HEAD`
- Diff a specific file between two commits:
  `git diff <hash> HEAD <file>`

## Blame

- Show origin of lines in a file: `git blame -L <start>,<end> <file>`

## Search

- Search in current branch: `git grep <regexp>`
- Search in all branches: `git grep <regexp> $(git rev-list --all)`

# Branches & Worktrees

## Branch

- Create new branch: `git checkout -b <branch>`
- Delete branch locally: `git branch -d <branch>`

## Worktree

Work on two branches of the same repo simultaneously without cloning twice.
Worktrees share the same `.git` directory — objects, history, and fetches
are shared.

### Basic commands

```bash
# Check out an existing branch into a new directory
git worktree add ../my-repo-feature feature/foo

# Create a new branch and check it out
git worktree add -b feature/bar ../my-repo-bar main

# List active worktrees
git worktree list

# Remove a worktree when done
git worktree remove ../my-repo-feature
```

### Directory layout

```
~/projects/
├── my-app/               ← branch: main  (contains .git/)
├── my-app-hotfix/        ← branch: hotfix/login
└── my-app-dashboard/     ← branch: feature/dashboard
```

Each extra worktree is a plain directory with no `.git` folder - just a
pointer back to the shared `.git`.

### Notes

- You cannot check out the **same branch** in two worktrees at once.
- `git fetch` run in any worktree updates refs for all of them.
- Commits made in one worktree are immediately visible in the others via
  `git log <branch>`.

# Repository

## Clone

- Clone with submodules: `git clone --recurse-submodules`
- Clone delayed submodules: `git submodule update --init --recursive`

## Submodules

- Update all submodules to latest remote version: `git submodule update --remote`
- Sync all submodules to pinned commit: `git submodule update`

### Update a single submodule to latest

```bash
# Pull the submodule's remote HEAD (or its configured tracking branch)
git submodule update --remote packages/services/cns-cbom-id

# Commit the updated pointer
git add packages/services/cns-cbom-id
git commit -m "chore(RD-2498): Update cns-cbom-id submodule to latest"
```

### Track a specific branch

Set the tracking branch before updating so `--remote` follows it:

```bash
git config -f .gitmodules submodule.packages/services/cns-cbom-id.branch main
git submodule update --remote packages/services/cns-cbom-id
```

The branch is stored in `.gitmodules` and should be committed alongside the pointer update.

## Tags

- List tags: `git tag`
- Create tag: `git tag "<name>"`
- Push all tags: `git push --tags`

## Clean

- Prune local branches deleted on remote: `git fetch --all --prune`
