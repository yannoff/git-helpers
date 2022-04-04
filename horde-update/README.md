# git horde-update

Update several local branches.

## Usage

### Synopsis

```bash
git horde-update [--rebase] --all
git horde-update [--rebase] branch1 [branch2 ... [branchN]]
```

### Options

#### `-a`, `--all`

_Update all local branches._

#### `-r`, `--rebase`

_Use `git pull --rebase` instead of `git pull` for branch update._

> _In case of rebase/merge conflicts on a given branch, the script will prompt for what to do. See [conflict options](#conflict-options) for details._

### Examples

_Update a given list of branches:_

```bash
(master)$ git horde-update develop feature/add-force-push-option feature/implement-debug-messages
```

_or update all local branches:_

```bash
git horde-update --all
```

_The script will successively checkout on each branch and update it._

## Reference

### Conflict options

- `r` / `resolve`: launch the `git mergetool` command, then continue rebase/merge
- `a` / `abort`: repristine branch to its initial state and abort rebase/merge

## License

Licensed under the [MIT License](../LICENSE).
