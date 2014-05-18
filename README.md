edmv
====

A small tool for bulk-renaming files using the editor of your choice.

WARNING: May delete everything on your computer. Read the LICENSE file and don't sue me.

Use it like this:

`edmv foo bar baz`

It will invoke your editor on a list of the files provided, in this case `foo`, `bar`, and `baz`. Once you're done editing the files it will try to rename them to match any changes that you've made. Be careful!

You can tell `edmv` which editor to use by:
- Supplying an argument to the `--editor` flag
- Setting the `$EDMV_EDITOR` environment variable
- Setting the `$EDITOR` environment variable
- Not doing anything, in which case edmv will default to `vi`

If you would like to use an OS X application for your editor, for example Sublime Text 2, you can put something like the following in your shell rc file: `export EDMV_EDITOR='open -Wa "Sublime Text 2"'`. This has not been well tested at all.

todo
----

- better cli:
  - --help, with a better help message, mention $EDITOR and $EDMV_EDITOR
  - --version

- add an extra newline at the end of the file, then remove it

- add sanity checks, atomic operation, only rename files if they all pass for every file:
  - refuse to add trailing whitespace to a file name if it didn't already have it
  - check that the source file exists
  - check that the source file can be removed
  - check that the destination directory exist
  - check that the destination file does not exist
  - check that all destination files and source files are unique

- add tests:
  - create a bunch of files
  - small commands to filter text
  - check that files are where expected
  - check that if there are problems the operation is aborted
  - do this all with a permissionless user or in a chroot

- nicer post-move reporting:
  - line up pre and post names

- better demo video:
  - more complex renames
  - multiple editor types: command line, sed filter, os x app, vim, emacs

- better readme:
  - linux example
  - os x app example: `export EDMV_EDITOR='open -Wa "Sublime Text 2"'`

- better temporary file name

- accept arguments from stdin
  - should it do it via an '-' argument, a flag, or just if anything is available on stdin?
