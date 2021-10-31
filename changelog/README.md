# git changelog

Prints a fancy changelog to standard output.

## Usage

```
git changelog [<previous-tag> [<current-tag>]]
```

### Examples

_Given the following git history:_

```
$ git log --oneline
99ad738 (HEAD -> master, origin/develop, origin/HEAD, develop) [encoder] Better JSON exception message
915d648 (tag: 1.4.3) Release 1.4.3
12f86e7 [bump] Bump `yannoff/y-a-m-l` => `1.1.5`
79521d4 [composer] Upgrade offenbach lock file contents
f1a24e1 (tag: 1.4.2) Release 1.4.2
098f5e2 [builder] Add smoke test
4c2da01 [comments] Fix standard output EOF
09944bf [converter] Fix standard output EOF
6a8fa65 [converter] Always add a new line as output EOF
23df972 Bump yannoff/console from 1.2.3 to 1.2.4
377480b [dependabot] Customize commit message prefix
780f173 [distribution] Add `export-ignore` rules
c44d9eb [composer] Implement post-dependabot hook
de34677 [composer] Configure distributable binaries
32ee2ec [documentation] Amend README
4be788f (tag: 1.4.1) Release 1.4.1
```

#### Changes since last release

*Build a changelog between the latest release and `HEAD`*

```
$ git changelog
- 99ad738 [encoder] Better JSON exception message
```

#### Changes since a given release

*Build a changelog between the given release and `HEAD`*

```
$ git changelog 1.4.2
- 79521d4 [composer] Upgrade offenbach lock file contents
- 12f86e7 [bump] Bump `yannoff/y-a-m-l` => `1.1.5`
- 915d648 Release 1.4.3
- 99ad738 [encoder] Better JSON exception message
```

#### Changes between two releases

*Build a changelog between the two given releases*

```
$ git changelog 1.4.1 1.4.2
- 32ee2ec [documentation] Amend README
- de34677 [composer] Configure distributable binaries
- c44d9eb [composer] Implement post-dependabot hook
- 780f173 [distribution] Add `export-ignore` rules
- 377480b [dependabot] Customize commit message prefix
- 23df972 Bump yannoff/console from 1.2.3 to 1.2.4
- 6a8fa65 [converter] Always add a new line as output EOF
- 09944bf [converter] Fix standard output EOF
- 4c2da01 [comments] Fix standard output EOF
- 098f5e2 [builder] Add smoke test
- f1a24e1 Release 1.4.2
```
