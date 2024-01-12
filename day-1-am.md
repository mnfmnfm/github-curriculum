# Day 1 Morning Session

## Agenda

- Debugging installations
- Intros, icebreakers (30 mins)
- Command Line Review (15 mins)
- Intro to Git and GitHub (5 mins)
- Using Git on the Command Line (20 mins)
  - Creating repos
  - Obtaining existing repos
  - Making commits
- Using Git with GitHub (20 mins)
  - Pushing Code to GitHub
  - README files
    - Why
    - Markdown syntax
    - Creating and adding to past projects
- Lab: Working with Git (45 minutes)
- Branches (15 minutes)
  - What
  - Creating a branch and making commits
  - Merging from a feature branch into the main branch
- Lab: Practicing with branches (30 minutes)

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

## Git on the Command Line

### Creating Repos

To create a repository on the command line, use `cd` to open the director that you want to turn into a git repository. Run `git init` to turn that folder into a git repository. By making that folder a git repository, git will be able to track version history for the files in that directory.

To create a repository on GitHub, click on the '+' button in the upper righthand corner, and choose "new repository".

### Getting Existing Repos Onto Your Computer

If you want to get an existing repo from GitHub onto your computer - for example, to work on an open-source project, or because you're working on a team and your teammate created the git repo - you can use the `clone` command. On GitHub, the clone link is listed when you click on the green "Code" button on the top right of a repo. If you copy that link, then you can open your terminal to the location on your computer where you want to copy the code, and run:

```bash
git clone pasted-url-here
```

That will copy the existing code onto your computer.

### Making Commits

When you've written some code or made edits that you want to save, it's time to make a commit! A good first step is always to run `git status` so you can see wht git thinks the status of your repo is; you can run this command as often as you want and it will not break anything, so especially as you're getting started, I encourage you to run `git status` at every step of the process, to follow along with the changes you're making.

When you're ready to get started, you'll run `git add filename.py` which adds that file to be part of your next commit. This doesn't actually commit the file; it just allows you to pick which files are part of the commit and which aren't. You can run this as many times as you need to add all the files you want to commit.

Instead of adding files one by one, if you check `git status` and realize that you want to add EVERY file you have changed, you can do that in a single command with `git add .`. (Or, you can add every file in a directory by specifying which directory.)

Then, once you've added all the changed files that you want to commit, you'll run `git commit -m "description of the commit"`. For that description, put something useful to you - you want this commit message to have a good enough description that you can use it to track down this set of changes later.

## Connecting Git and GitHub

Once you have at least one commit on your local repo, you're ready to connect your code to GitHub!

First, you'll need a repo on GitHub to connect to. Go to GitHub and click the `+` button in the upper right corner of the page to create a "New repository". Give it a nice name with no spaces - this will often match the name of the directory where your code for the project lives. Any of UpperCamelCase, lowerCamelCase, kebab-case, or snake_case are acceptable; you'll usually choose based on the conventions of the language your project is written in (python often in snake_case, Java often in lowerCamelCase, etc). You'll leave all the other defaults as-is, and click "Create repository" at the bottom of the page.

Once you've made your empty repo on GitHub, it's time to link that empty repo up with your local repo. On GitHub, it will provide you with quickstart steps, and you want the second option: "... or connect to an existing repo". Copy those lines of code and paste them in your terminal. This will include two lines of setup, and then one line that sends the code from your computer to GitHub: `git push -u origin main`. Once you've run that line, you should be able to refresh the page and see your code on GitHub. Woohoo!

## README files and Markdown

One of the goals of putting code on GitHub is to allow recruiters and hiring managers to see your code. But imagine looking at a code file and diving into reading it with no context - it would be hard to figure out what the point even was, let alone if the code was good. That's where a README file comes in - it's a place where you can explain what your code is. It's also the first thing that recruiters and hiring managers will see when they look at your code, so it's important to make a good first impression!

You should include enough information in your README file that if someone was linked directly to that repo with no other information, they would know what the purpose of the code in the repo was, and would have some understanding of the purpose of the project. [Here is an example](https://gist.github.com/DomPizzie/7a5ff55ffa9081f2de27c315f5018afc) of a simple but effective README template.

README files are written with Markdown syntax - it's a simplified formatting language. It's simple enough that, after you see a few examples, it's easy to write by referencing a cheat sheet - [this](https://www.markdownguide.org/cheat-sheet/) is the cheat sheet that I tend to use.

As one example, this file (and all the files in this curriculum) are Markdown files rendered by GitHub.


Some of the Markdown tools I use most often:
~~~md
# Big heading
## Smaller heading
### Even smaller (these go down to 6)

[This is link text](https://google.com)

* bullet points
* making a list

1. numbered lists
1. you can use 1 for all the numbers
1. markdown replaces the 1's with the correct numbers

A small piece of code goes in backticks: `git init`

A larger piece of code goes in three backticks with the language specified, like this:

```javascript
console.log('This is some javascript code!');
```

~~~

And the non-headings as rendered by Markdown:

[This is link text](https://google.com)

* bullet points
* making a list

1. numbered lists
1. you can use 1 for all the numbers
1. markdown replaces the 1's with the correct numbers

A small piece of code goes in backticks: `git init`

A larger piece of code goes in three backticks, like this:

```javascript
console.log('This is some javascript code!');
```

## Complete Basic Workflow

- Initial Setup
  - `git init` or `git clone`
- Ongoing
  - write some code
  - `git status`
  - `git add filename` or `git add .`
  - `git commit -m "descriptive message"`
- To take the commits you've made locally and put them on GitHub
  - `git push`

## Lab: Working with Git

1. Choose a project that you want to put on GitHub and, using the directions above and the basic workflow reminder, create a git repo for that project, commit all of your existing code, connect your local repo to a GitHub repo, and push your existing code to GitHub. Refresh the page on GitHub to ensure that you can see your code.
2. Add a README file to your existing project. Name it `README.md` and place it at the root of your repo. Inside, add a header and a brief description of your project. Add, commit, and push to GitHub, and ensure that you can see your README file on GitHub.
3. [Stretch goal] Add more context to your README file. Include sections like screenshots, lists of the technologies used, collaborators, links to references, future work, or anything else that is relevant to your project.
4. [Stretch goal] Challenge yourself to use more Markdown features in your README file. Add in a table, a numbered list, a bulleted list, an image, and links.

