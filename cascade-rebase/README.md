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

### Use cases

_Cascade rebase a given 3 branches:_

```bash
git cascade-rebase branch1 branch2 branch3
```

_Starting from the current branch, the script will successively checkout on each branch, rebase it onto the previous one, then prompt confirmation before pushing (see [push options](#push-options) section for details)._

> 💡 _In case of rebase conflicts on a given branch, the script will prompt for what to do: see [conflict options](#conflict-options) for details._

### Example

#### Cascade rebase several branch on master

```bash
(master)$ git cascade-rebase develop feature/one feature/two
```

> _The script will rebase successively:_
> - `develop` onto `master`
> - `feature/one` onto `develop`
> - `feature/two` onto ` feature/one`

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
