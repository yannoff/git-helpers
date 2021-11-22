# git batch-rebase

Rebase several branches on the current one.

## Usage

_Rebase a given list of branches:_

```
git batch-rebase branch1 [branch2 ... [branchN]]
```

_or rebase all local branches:_

```
git batch-rebase --all
```

### Examples

#### Rebase develop and feature branches on master

```
(master)$ git batch-rebase develop feature/add-force-push-option feature/implement-debug-messages
```

_The script will successively checkout on each branch, rebase it on `master`, then prompt confirmation before pushing._

See [push options](#push-options) for details.

_In case of rebase conflicts on a given branch, the script will prompt for what to do:_

See [conflict options](#conflict-options) for details.

## Reference

### Push options

- `y` / `yes` : push the branch
- `f` / `force` : force-push the branch
- `n` / `no` : don't push the branch (defaults)

### Conflict options

- `r` / `resolve`: launch the `git mergetool` command, then continue rebase
- `a` / `abort`: repristine branch to its initial state and abort rebase
