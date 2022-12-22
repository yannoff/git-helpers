# git mig-diff

Print all migrations created between two references (tag, commit or branch).

## Usage

### Synopsis

```bash
git mig-diff [--dir=<dir>] [--prefix=<prefix>] [--extension=<ext>] [<from-ref> [<to-ref>]]
```

### Options

#### `--dir`

_Alternative directory for the migration files._ defaults: **migrations**

#### `--prefix`

_Alternative migration filenames prefix._ defaults: **Version**

#### `--extension`

_Alternative migration files extension._ defaults: **php**

### Arguments

#### `<from-ref>`

_Lower bound (tag, branch or commit) for the migration diff._ defaults: **latest tag**

#### `<to-ref>`

_Upper bound (tag, branch or commit) for the migration diff._ defaults: **HEAD**


## License

Licensed under the [MIT License](../LICENSE).
