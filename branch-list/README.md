# git branch-list

The `git branch-list` command displays a list of local branches, with their associated remote.<br />
The current branch line is rendered as bold, instead of the default `*` prefix.

## Usage

```bash
git branch-list [<remote-name>]
```

## Examples

### List all local branches

<pre><code>$ git branch-list
[dev]      develop
[dev]      feature/implement-test-builder
[prod]     fix/contents-parsing/wrong-ypath-calculation
[prod]     fix/restore-file-ending-blank-lines
<b>[prod]     master</b></code></pre>

_For comparison, here would be the result of the classic `git branch --list` command:_

```
$ git branch --list
  develop
  feature/implement-test-builder
  fix/contents-parsing/wrong-ypath-calculation
  fix/restore-file-ending-blank-lines
* master
```

### Filter local branches by remote

_Additionally, the command accepts one optional argument, allowing to filter on a particular remote name:_

<pre><code>$ git branch-list prod
[prod]     fix/contents-parsing/wrong-ypath-calculation
[prod]     fix/restore-file-ending-blank-lines
<b>[prod]     master</b></code></pre>
