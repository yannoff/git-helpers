# git batch-rebase

Rebase several branches on the current one.

## Usage

> 💡 **IMPORTANT NOTE**<br/>
>  _Only basic rebase commands (namely `pick`, `fixup`, `drop`) are supported for now._

### Synopsis

```bash
git batch-rebase [--force] --all
git batch-rebase [--force] branch1 [branch2 ... [branchN]]
```

### Options

#### `-a`, `--all`

_Rebase all local branches on the current one._

#### `-f`, `--force`

_Assume reply is `force` for each branch at push prompt. (See [push options](#push-options) section for details)._

### Examples

_Rebase a given list of branches:_

```bash
git batch-rebase branch1 [branch2 ... [branchN]]
```

_or rebase all local branches:_

```bash
git batch-rebase --all
```

### Use cases

#### Rebase develop and feature branches on master

```bash
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

## License

Licensed under the [MIT License](../LICENSE).
