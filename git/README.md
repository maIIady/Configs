1. * `git push origin --delete bad-branch-name` deletes the branch from origin
2. When working with `https` use `git config --global credential.helper cache`
3. Setting up `upstream` branch is made with one of commands:
  * `git branch -u <remote>/<branch>`
  * `git checkout -b <branch> <remote>/<branch>`
  * `git checkout --track <remote>/<branch>`
  * If the branch name you’re
trying to checkout (a) doesn’t exist and (b) exactly matches a name on only one remote

    `git checkout <branch>`
***
5. Upstream branch can be referenced as `@{upstream}` or `@{u}`, i.e. `git merge origin/main` can be replaced with `git merge @{u}`
***
6.  `git rebase --onto <target> <parent> <child>`
  
    If `child` is subbranch of `parent` this command will rebase all commits from `child`, ignoring commits, presented in parent onto `target`

7. Commit can be references by at least four chars of its SHA-1 hash, but there has to be an ambiguous reference. `git log --abbrev-commit` will show log with shorter values, but keep them unique (7 chars by default)
8. Parent referencing can be done in two ways: using `~` and `^`. The difference between them become clear when number in specified, e.g. `HEAD~2` means parent of parent, `HEAD^2` means _second_ parent of the commit (only useful with merge commits, where the _first_ parent is commit from the merge target branch and the _second_ parent is from the merging branch). The following syntaxes are correct - `HEAD~~~`, `HEAD~2^2`.
9. In command is like `git log origin/main..` the argument after two dots is substituted with `HEAD`
10. The following commands are aliases:
```shell
$ git log refA..refB
$ git log ^refA refB
$ git log refB --not refA
```