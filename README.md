# README

This repository adds some additional git commands that I use a lot.

They are basically bash scripts in the format `git-xyz` where xyz is the git
command used to invoke the script.

To use these scripts, clone the repository to a folder and add the full path
to the folder to the PATH.

On Windows, open the global Environment Variables and edit your user variable

    PATH=C:\...\GitToolbox

On macOS, edit your `~/.bash_profile` file and add this line:

    EXPORT PATH=~/GitToolbox:${PATH}

Afterwards you can use the commands.

# git-ahead

`git ahead` shows a log of all the commits you have locally that you have not yet
pushed to the remote.

# git-behind

`git behind` shows a log of all the commits you have not yet merged or pulled into
your local branch.

**Note:** `git behind` does not fetch from your remote, it will only compare your local
branch with the most recent information you got from the remote.

# git-ff

`git ff` first fetches from the remotes to bring your local copy of the remote branches
up to date, and then it attempts to perform a fast-forward merge on the branch
you have checked out in the local folder.

Note that `git ff` will not perform this fast-forward merge if you need to do a regular
merge, nor if you have local uncommitted changes.

# git-ff-all

`git ff-all` first fetches from the remotes to bring your local copy of the remote branches
up to date, and then it attempts to perform a fast-forward merge *on all worktrees* that
you have checked out to local folders.

Note that, just as with `git ff` , if you have locally uncommited changes, or if you need
to perform a regular merge to make the branch up to date then `git ff-all` will not
bring that particular branch up to date but instead leave it in its current state.

# git-lg

`git lg` is a stylized one-line graph log alternative to `git log`. I find this easier
to read unless I need to see more raw information such as author email address and such.

# git-review

`git review` is a combination of `git ahead` and `git behind` that tells you what your
state of your local branch is compared to its remote.

# git-source

`git source` is a specialized command that is mostly used at work. It will try to figure
out which `develop/*` branch the current branch must have originated from so that you can
easily make sure you're not merging a feature branch into the wrong development branch.

# git-suggest

`git suggest` looks at the state of your repository and attempts to give you some suggestions
as to what to do next, be it committing your local changes or pushing or pulling.