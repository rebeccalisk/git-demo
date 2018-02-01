# Welcome!

Welcome to CS51! You'll learn a lot this semester, not just about OCaml but about writing beautiful code, version control, and designing programs. I'm excited to be your Teaching Fellow for the semester, and want to serve as a resource to help all of you get the most out of this class.

This code review (modified from Kevin Zhang's original [git demo](https://github.com/kevinzhang96/git-demo) -- thanks, Kevin!) is designed to get you up-to-speed on how to use Git. 

# Using Git

Git is a version control system that allows you (and your coworkers) to keep track of your code, the changes you're making to it, and keep backups. Since downloading, working on, and submitting your problem sets will involve use of Git, we're going to cover it here.

## Downloading Git

First, if you haven't already, download and install ``git``. you can find downloads at git-scm.com/downloads.  If you install GitHub's native client at https://desktop.github.com, `git` will automatically be installed.

Next, if you don't have a GitHub account yet, go to https://github.com and sign up for an account.  Once you're done, visit https://github.com/ariannacodes/git-demo, and hit "Fork" on the top right.  This creates a copy of this repository for your own use; you'll be able to pull updates from this repository while making changes to your own copy.  Once you're done, visit your own copy.

## Getting Started

Go back to your copy of this repository, and note the URL listed on the page (looks like `git@github.com:ariannacodes...`). Copy this URL.  In your Terminal, `cd` into a directory that you want to store your code in; type `git clone` into your Terminal then paste the URL.  Hit enter.  After `git`'s done, you should see a new folder (type `ls`) called `git-demo`!  `cd` into it; note that it only contains a README.md file so far.  We're going to add more files and submit something called a pull request to the main repository (more on that later).

In your terminal, type `touch <your-name>.txt`, then `open .` (replace `<your-name>` with your name, of course).  You should see a folder open up on your computer; this is the `git-demo` folder!  Open up `<your-name>.txt`, and type in something about yourself (let's say, how much programming experience you've had up until now).  Save the file, and close it.  Go back into your Terminal, type `git add -A`, then `git commit -am "added name file"`, and `git push`.  This will push the new file to your copy of this repository!

## Branches

Now we'll go over a simple example of branching.  Branching is mostly useful for when you're working on a feature that you don't want integrated into the main codebase yet - sometimes new code can break functionality in a repository, so it's safer to put that code somewhere else until it's finished.

Go into your terminal and type `git checkout -b new_branch` (you can replace `new_branch` with whatever you want).  This creates a new *local* branch called `new_branch` and switches to it.  Here, add a new file and call it whatever you want; you don't have to put anything in it (although that would be preferred), just create a new file.  Now, commit it!  You can refer to "Getting Started" above; however, you'll notice that `git push` won't work!  This is because GitHub doesn't recognize your new branch yet; it only knows about the main branch (called `master`).  To tell GitHub about the new branch, run `git push --set-upstream origin new_branch`.  You can revisit your copy of the repository; you should now see that a new branch has been created (click on `master` on the page, you should be able to select your new repository in the dropdown that shows).

You know how to create new branches now; however, you don't know how to merge your changes between branches yet!  In your terminal, run `git checkout master`.  If `git` complains that you have unstashed changes, you made changes that you haven't committed yet; either commit it or run `git reset --hard` (NOTE: DO NOT RUN THIS COMMAND ARBITRARILY.  This drops ALL changes you have made since your last commit, and you will NOT be able to get them back).  `git checkout master` switches you back to the main codebase (the `master` branch).  From here, run `git merge new_branch`; this pulls the changes from your other branch into the main base.  If you forget what your branch was called, you can run `git branch` to see a list of active branches.  Push the updated master branch to your repository!

## Pull Requests

The last thing we'll cover is pull requests.  Pull requests are designed to allow you to contribute to repositories that you don't have write access to, while providing a buffer so that the owners of the original repository can review any changes you make before integrating them into the main codebase.

Revisit https://github.com/ariannacodes/git-demo.  You should see a "New pull request" button on the screen; hit it.  On the new page, hit "compare across forks" - this allows you to integrate changes from separate copies of the original repository into the original.  On the right, select your copy of the repository along with the master branch; on the left, select the original copy (ariannacodes/git-demo) and the master branch.  Once you've done that, hit "Create pull request"; you should be done!  

I can now view your changes and integrate them into my repository; if everyone's done everything correctly, the original repository will eventually contain a lot of text files, with one for each member of the class.  You can revisit this repository afterwards to see a list of your classmates' names, along with any other files people have created.  Congrats; you're now acquainted with almost all features of `git` you'll ever need!

# Other Setup

## The Terminal

Since you'll be using the terminal a lot over the course of the semester, it doesn't hurt to make it pretty! To add some colors, you can start by opening ~/.bash_profile () and adding in the following lines:

```
export PS1="\033[36m\]\u\[\033[m\]:\[\033[33;1m\]\w\[\033[m\]\$ "
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced
```

To make your shell a bit easier to use, you might also want to add some aliases, which map one command to another. One alias that I find useful is mapping `..` to `cd ..`, so I can easily go back a directory. I also like to alias `ls` to `ls -GFh`, so when I list out the contents of a folder they display nicely. One alias might look like:

```
alias ls='ls -GFh'
```

# Resources

Though CS51 does a bit less hand-holding than CS50, that doesn't mean there aren't resources available to you!

* [Piazza](https://piazza.com/class/i55hhqy3vmr1xk) should be your go-to place for any questions you have about problem sets, concepts, or logistics. Not only are all the instructors ready to answer questions on Piazza, but other students can see and answer your questions as well. Chances are, someone has had the same problem as you already! I also highly encourage you to answer others' questions, if you can, since explaining things to others helps you solidify your own understanding of the material. :)

* Office Hours (held in the Northwest Labs basement from 7 to 11pm on Mondays and Tuesdays) are a great place to work on problem sets with other CS51 students, and get help from TFs when you get stuck!

* Teaching Fellows are available to help as well! We will be at Office Hours and Labs, but you should also feel free to email me, or come to speak with me before code review, to talk about your problem sets or conceptual problems.
