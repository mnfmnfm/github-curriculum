# Day 1, Morning Session

## Agenda

- Debugging installations
- Intros, icebreakers
- Intro to Git and GitHub
- Using Git on the Command Line
  - Creating Repos
  - Making Commits
  - Pushing Code to GitHub
  - README files
    - Why
    - Markdown syntax
    - Creating and adding to past projects

## Quick Commands

```bash
git init # creates a new repo in the current directory
git add myfile.py #adds a specific file to be committed
git add . # adds all files to be committed
git commit -m "description of my commit" # creates a commit for the added files
git remote add origin https://github.com/myusername/myrepo # creates a connection between your local repository and the GitHub version of your repository
git push origin main # pushes your main branch to the GitHub version of your repository; adding -u will make that the default push for the future
git push # pushes your current branch to its default
```

## Git Vs GitHub

`git` is a command line tool that allows version control on your computer. It can also connect to remote versions of your code, like on GitHub.

GitHub is an online, social place to store `git` repositories.

This means that you can use `git` on your computer to do as much version control as you want, but if you want to make that code visible to other people or work with a team, you'll need GitHub to make that possible.

## Creating Repos

To create a repository on the command line
