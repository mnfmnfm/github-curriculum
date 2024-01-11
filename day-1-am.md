# Day 1 Morning Session

## Agenda

- Debugging installations
- Intros, icebreakers
- Command Line Review
- Intro to Git and GitHub
- Using Git on the Command Line
  - Creating Repos
  - Making Commits
- Using Git with GitHub
  - Pushing Code to GitHub
  - README files
    - Why
    - Markdown syntax
    - Creating and adding to past projects


## Cheat Sheet

```bash
# General Terminal Commands

pwd # prints the current (working) directory
ls # lists the contents of the current directory
cd directoryname # change into the named directory
code . # opens the current directory in VSCode (if this does not work on Mac, open VSCode, use Shift-Cmd-P, type "path", and select "install", then try again)

# Git Commands

git status # prints out the current status of your git repo
git init # creates a new repo in the current directory
git add myfile.py # adds a specific file to be committed
git add . # adds all files to be committed
git commit -m "description of my commit" # creates a commit for the added files
git remote add origin https://github.com/myusername/myrepo # creates a connection between your local repository and the GitHub version of your repository
git push origin main # pushes your main branch to the GitHub version of your repository; adding -u will make that the default push for the future
git push # pushes your current branch to its default
```

## Command Line Review

We will do an interactive demo together.

## Intro to Version Control

*Version control* is the general term for a program that helps you track different versions of your code through time. This works similarly to something like a Google doc or Microsoft Word's version history features - it helps you see what was updated, when, and by who. The main difference is that, with most software version control systems, you have to explicitly create each timestamp when you have a version of your code that you want to save and be able to access later. Each of those checkpoints is called a *commit* in git, and your main git workflow revolves around setting up and creating commits.

A typical basic workflow involves setting up your version control repository to contain all the files involved in a particular project. As you work on your code, anytime that you finish a task or a feature in that code, that's a good time to make a commit - a snapshot of your code that you will be able to access later if everything else breaks. Once you've made a commit, you can continue working on code until you've finished your next feature, at which point you might make another commit.

## Git Vs GitHub

`git` is a command line tool that allows version control on your computer. It can also connect to remote versions of your code, like on GitHub.

GitHub is an online, social place to store `git` repositories.

This means that you can use `git` on your computer to do as much version control as you want, but if you want to make that code visible to other people or work with a team, you'll need GitHub (or another remote) to make that possible.

## Creating Repos

To create a repository on the command line, use `cd` to open the director that you want to turn into a git repository. Run `git init` to turn that folder into a git repository. By making that folder a git repository, git will be able to track version history for the files in that directory.

To create a repository on GitHub, click on the '+' button in the upper righthand corner, and choose "new repository".


