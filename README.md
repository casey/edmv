edmv
====

A small tool for bulk-renaming files using the editor of your choice.

Demo here: http://youtu.be/EzhbTEh-7Fk

WARNING: May delete everything on your computer. Read the source code, then the LICENSE file, and then don't sue me.

Use it like this:

`edmv foo bar baz`

It will invoke your editor on a list of the files provided, in this case `foo`, `bar`, and `baz`. Once you're done editing the filenames it will try to rename them to match any changes that you've made. Be careful!

You can tell `edmv` which editor to use by:
- Supplying an argument to the `--editor` flag
- Setting the `$EDMV_EDITOR` environment variable
- Setting the `$EDITOR` environment variable
- Not doing anything, in which case edmv will default to `vi`, just as Bill Joy intended

If you would like to use an OS X application for your editor, for example Sublime Text 2, it is speculated that you could put something like the following in your shell rc file: `export EDMV_EDITOR='open -Wa "Sublime Text 2"'`.

todo
----

* add tests to provide the illusion of safety:
  - create a bunch of files
  - small commands to filter text
  - check that files are where expected
  - check that if there are problems the operation is aborted
  - do this all with a permissionless user or in a chroot

* better demo video:
  - carmina burana
  - more complex renames
  - multiple editor types: command line, sed filter, os x app, vim, emacs
