# Quality Commands - A CLI Guide for Testers

## Intro

Using the command line interface, or CLI, is a great way to get things done. It's very powerful and convenient, but it can also be very intimidating. This README is intended to be used as a quick reference for some basic work to help build confidence in the command line. So open your terminal app and lets get started!

---

## Typing Commands

### Basic Command Structure

CLI commands are comprised of 3 components: the program, arguments and options. For example, the Remove program is used to delete files and directories. The use of the command requires typing the program - `rm` - and the argument, which in this case is the file or directory you would like to delete - `sample.html`. Options can be typed out fully or notated with short hand, if you need to use one. A full option would look like `--force`, while a short option would look like `-f`. Note the used of `--` when typing out a full option rather than a single `-` when using the abbreviated option. A full remove command example:

> `rm sample.html -f`

This will forcefully remove the `sample.html` file, if it exists in your current directory. To remove a file in another directory, simply include the files directory:

> `rm /directory/to/sample.html`

Sometimes there will be sub-commands, as is the case with Git. In the example below, `git` is the command and `status` is the sub-command:

> `git status`

### Combining Commands

Commands can be combined in often useful ways. Using double ampersands `&&` will allow you to execute multiple commands in the order that they are written. A pipe will allow you to "pipe" one command into another, which is useful when the second command will be performing an action on the result of the first.

Here is an example using the `&&` operator to join 2 commands together. The second action is performed after the first. This is useful if there are long running commands that you want to execute sequentially but do not necessarily need to monitor for their duration. A new directory called `development` is being created and then navigated to:

> `mkdir development && cd development`

And this example is using the `|` operator to join 2 commands together than will be executed in order, but the second command is performing an action on the results of the second. Specifically, the list of files are directories are being requested, then a search is being performed to only show those which contain `dev`:

> `ls | grep dev`

---

## Useful Common Commands

- `pwd` : Prints your current directory, also known as the working directory.
- `cd <directory-name>` : Change directory to the specified directory. If no directory is given, then you will be taken to the user's root directory.
- `..` : Navigate to parent directory.
- `ls` : List files and directories in my current directory. Use the `-a` all option will display all files, including files that may be hidden when simply using the `ls` list command alone.
- `cat <file>` : Display the contents of a file on screen.
- `rm <file-name/directory-name>` : Remove file or directory. If a directory contains files, you will need to tack on the `-r` recursive option to recursively delete the directory and all its files. In some cases, tacking on the `-f` force option to force the command is necessary, however, use this cautiously becaus `-f` will delete everything without question.
- `mkdir <directory-name>` : Create a directory
- `touch <file-name>` : Create a file
- `grep` : The `grep` search command is powerful. A simple and useful way to use it is to combine it with `ls` when looking for a specific file or directory.
- `ping <URL/IP address>` : Send a packet to a URL or IP address. Helpful to determine if the URL is reachable if the page does not load in the browser.

## Common Git Commands

- `clear` : Clears the terminal of all visible text.
- `git status` : Displays the status of the current branch.
- `git checkout <branch-name>` : Checks out the branch specified. This command is used
  - `git checkout -b <branch-name>` : When creating a branch for the first time, you will need to use the `-b` new branch option.
  - `git checkout -b <branch> <origin/branch-name>` : When checking out a branch from GitHub for the first time, you will need to use the `-b` new branch option and specify the origin using `origin/branch-name`. Usually, `origin` is literally "origin".
- `git reset` : Sometimes you will want to change branches but existing, uncommitted changes in the current branch will prevent you from switching. If you do not want to keep those changes, `git reset` will discard those changes.
  - `git reset --hard` : Using the `--hard` option will perform a hard reset and is sometimes needed if `git reset` doesn't work.
  - `git reset origin/branch-name` : Adding `origin/branch-name` will reset your branch equal to the state of the remote branch.
- `git add <file-name>` : Stages changed files making them ready to commit. To add all files to staging, use `.` instead of specific file names.
- `git commit` : Commits all staged files to git. You will be prompted to enter a commit message unless this command is followed by `-m "your-commit-message"`.
- `git push` : Pushes the committed changes to the remote server (GitHub). This does command does not have to be run after each commit, however, it is recommend to use it frequently as it preserves a copy of your changes on your remote server.

---

## Additional Resources

[FreeCodeCamp.com Git training](https://www.freecodecamp.org/news/git-and-github-crash-course/)

[Terminal Basics](https://www.youtube.com/watch?v=5XgBd6rjuDQ)
