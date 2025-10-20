# Programming Cheat Sheets

# Shell Commands

* Remember that *directories* are another name for folders.  "." (a single
  period, usually pronounced "dot") means "the directory you're currently in",
  and ".." ("dot-dot") means "the directory that *contains* the directory
  you're currently in" (known as the *parent directory*).
* Save yourself some typing by using *tab completion*!  In git-bash, if you're
  about to type the name of a file or directory, type only as much as you need
  to make it unambiguous, and then hit TAB.  git-bash will finish typing it
  for you!
* <pre>cd ***NewDirectory***`</pre>
  Change directory to ***NewDirectory***.  ***NewDirectory*** will now be the
  working directory, if it exists.  (If you made a typo and ***NewDirectory***
  doesn't exist, you stay in the old directory.  Look at the output!)  If you
  don't give a ***NewDirectory*** parameter, `cd` with no parameters will
  change to your home directory.  (Usually `C:\Users\something` on a Windows
  machine, but it depends on your installation.)

  If your working directory is `/c/Users/Jon/repos` and you type `cd ..`,
  then your new working directory is `/c/Users/Jon` -- do you understand why?
* <pre>ls</pre>
  List files and directories.  With no parameters, it lists everything in the
  working directory.  You can give `ls` any number of files or directories
  as parameters, and it will list only those.  You can also give `ls`
  "command-line flags", parameters that start with a dash.  `-l` (lowercase L)
  is a useful one: it gives a long listing.

  `ls ..` will list everything in the parent directory of your
  working directory.
* <pre>pwd</pre>
  Print the working directory.  ("Where am I?")  This command doesn't take
  any parameters.
* <pre>mkdir ***NewDirectory***</pre>
  Make a new directory called ***NewDirectory***.  If ***NewDirectory***
  doesn't start with a slash, then it's created in a location relative to
  the working directory.
* <pre>rm ***JunkFileName***</pre>
  Remove (delete) the file named ***JunkFileName***.  BE CAREFUL!  There is
  no trash can or recycling bin -- this can't be undone!  (Unless the file
  has been committed in Git.)
* <pre>rmdir ***JunkDirectoryName***</pre>
  Remove (delete) the directory named ***JunkDirectoryName***.  That directory
  must be empty, or the `rmdir` command will fail.
  

# Robotpy Commands

* All robotpy commands start with the following:
```
  py -3 -m robotpy --main code ...
```
  Depending on what you want robotpy to do, other stuff goes where the `...`
  appears above.
