# [Solved] Debugging Lefthook Issue: Linted files during pre-commit are not committed

Issue: https://github.com/evilmartians/lefthook/issues/628

✅ **Solution**: Use [`stage_fixed: true`](https://github.com/evilmartians/lefthook/blob/master/docs/configuration.md#stage_fixed) with each `commands` where you need to commit linted files.

## Problem

During commit, the Lefthook runs pre-commit commands. But, the changes made by the pre-commit command (especially `stylelint`) are not included in the commit.

## Steps to reproduce

1. Clone this repo locally.
2. Install NPM packages using `npm install`.
3. Open the file `css/styles.css`, delete the comment on line 7, and save.
4. Stage the file `css/styles.css`, and commit.
5. You should see the commit completed, and file `css/styles.css` with new changes. The changes that were made by pre-commit `stylelint` command.
