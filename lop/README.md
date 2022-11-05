# git lop

Delete several branches in one shot.

## Usage

```
git lop [-f|--force]
```

### Examples

_Given the following local branches:_

```
(master) $ git branch --color=never
  bump/yamltools/1.4.6
  develop
* master
  experimental/php-color-output-sanitizer
  feature/check-url-before-download
  feature/implement-composer-compatibility-tools
  feature/move-special-commands-handling-block
  installer/improve-dependency-handling
  installer/support-setup-via-env-vars
  refactor/use-default-name-for-temp-files
  test/support-setup-via-env-vars
```

_The `git lop` command will ask for each branch deletion:_

<pre><code>(master) $ git lop 
Cut-off <b>bump/yamltools/1.4.6</b> branch ? (y/N) y
Cut-off <b>develop</b> branch ? (y/N) 
Cut-off <b>experimental/php-color-output-sanitizer</b> branch ? (y/N) y
Cut-off <b>feature/check-url-before-download</b> branch ? (y/N) y
Cut-off <b>feature/implement-composer-compatibility-tools</b> branch ? (y/N) 
Cut-off <b>feature/move-special-commands-handling-block</b> branch ? (y/N) 
Cut-off <b>installer/improve-dependency-handling</b> branch ? (y/N) y
Cut-off <b>installer/support-setup-via-env-vars</b> branch ? (y/N) y
Cut-off <b>refactor/use-default-name-for-temp-files</b> branch ? (y/N) 
Cut-off <b>test/support-setup-via-env-vars</b> branch ? (y/N)</code></pre>

_Unless invoked with the `--force` flag, the script will ask for confirmation before deleting the selected branch list:_

<pre><code><b>Confirm deletion for the following branches ? (y/N)</b>
- bump/yamltools/1.4.6
- experimental/php-color-output-sanitizer
- feature/check-url-before-download
- installer/improve-dependency-handling
- installer/support-setup-via-env-vars</code></pre>

## Reference

### Options

- `h` / `help` : show usage
- `f` / `force` : don't ask for confirmation before actual branch deletion

## License

Licensed under the [MIT License](../LICENSE).
