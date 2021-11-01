# git batch-rebase

Rebase several branches on the current one.

## Usage

```
(master)$ git batch-rebase branch1 [branch2 ... [branchN]]
```

### Examples

#### Rebase develop and feature branches on master

```
(master)$ git batch-rebase develop feature/add-force-push-option feature/implement-debug-messages
```

_The script will successively checkout on each branch, rebase it on `master`, then prompt confirmation before pushing._

**Push options**

- `y` / `yes` : push the branch
- `f` / `force` : force-push the branch
- `n` / `no` : don't push the branch (defaults)
