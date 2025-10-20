# Programming Cheat Sheets

# Shell Commands

* Remember that *directories* are another name for folders.  `.` (a single
  period, usually pronounced "dot") means "the directory you're currently in",
  and `..` ("dot-dot") means "the directory that *contains* the directory
  you're currently in" (known as the *parent directory*).
* Save yourself some typing by using *tab completion*!  In git-bash, if you're
  about to type the name of a file or directory, type only as much as you need
  to make it unambiguous, and then hit TAB.  git-bash will finish typing it
  for you!
* <pre>cd <b><i>NewDirectory</i></b>`</pre>
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
* <pre>mkdir <b><i>NewDirectory</i></b></pre>
  Make a new directory called ***NewDirectory***.  If ***NewDirectory***
  doesn't start with a slash, then it's created in a location relative to
  the working directory.
* <pre>rm <b><i>JunkFileName</i></b></pre>
  Remove (delete) the file named ***JunkFileName***.  BE CAREFUL!  There is
  no trash can or recycling bin -- this can't be undone!  (Unless the file
  has been committed in Git.)
* <pre>rmdir <b><i>JunkDirectoryName</i></b></pre>
  Remove (delete) the directory named ***JunkDirectoryName***.  That directory
  must be empty, or the `rmdir` command will fail.
  

# Robotpy Commands

* All robotpy commands start with the following:
```
  py -3 -m robotpy --main code ...
```
  Depending on what you want robotpy to do, other stuff goes where the `...`
  appears above.  It's useful to memorize the start of all robotpy commands!

* Sync (`py -3 -m robotpy --main code sync`)

  This downloads and updates all the libraries you need, including:
  * WPILib and related libraries
  * all the libraries that you've specified in `pyproject.toml`
  * the version of robotpy
  * files that you'll need to deploy onto the RoboRIO

  You'll need to do this when you create a new robot project, when you
  change `pyproject.toml` because you're using new hardware, and when any
  library files update (which you can't actually know!).

  Because this command has to download a lot of data from the internet, it
  can take a while to run, especially if you're in the robotics classrooms
  tethered to your phone.  Fortunately you don't have to run it often, but
  it's a slow and annoying part of setting up a new robot project.

* Test (`py -3 -m robotpy --main code test`)

  This runs some very simple tests on your robot code.  (Basically it just
  checks for syntax errors, missing functions, and other basic slips like
  that.)  But it's surprising how often even running simple tests can save
  a lot of time, even for professional programmers!  You should run tests
  often, such as whenever you edit a function in your code.  Running tests
  every 5-10 minutes that you're writing code is a good goal.

* Deploy (`py -3 -m robotpy --main code deploy`)

  This runs tests, and then deploys code to the robot.  (Obviously you need
  a robot or a test board to run this.)  You'll need to be connected to the
  RoboRIO with a USB-B cable.
  ([USB connector types](https://www.iofast.com/images/usb-connector-id-guide.jpg))
  When you run this, watch the output carefully for errors.  Just because it
  ran, doesn't mean it ran successfully!

