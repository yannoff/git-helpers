# git cascade-rebase

Recursively rebase each branch on the previous one in the list.

## Usage

> 💡 **IMPORTANT NOTE**<br/>
>  _Only basic rebase commands (namely `pick`, `fixup`, `drop`) are supported for now._

### Synopsis

```bash
git cascade-rebase [--force] branch1 [branch2 ... [branchN]]
```

### Options

#### `-f`, `--force`

_Assume reply is `force` for each branch at push prompt. (See [push options](#push-options) section for details)._

### Examples

_Rebase a given list of branches:_

```bash
git cascade-rebase branch1 [branch2 ... [branchN]]
```

### Use cases

#### Cascade rebase several branch on master

```bash
(master)$ git cascade-rebase develop feature/add-force-push-option feature/implement-debug-messages
```

_Starting from `master`, the script will successively checkout on each branch, rebase it on the previous one, then prompt confirmation before pushing._

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
