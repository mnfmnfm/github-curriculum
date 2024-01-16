# Day 2 Morning Session

## Agenda

- Review of previous day's content
- Multiplayer GitHub
    - Creating organizations
    - Creating a single repository and adding collaborators
- Code Review
    - Best practices
    - Branch protection
    - Lab: review some code
- Merge Conflicts
    - How they happen
    - Resolving them
    - Lab: resolving merge conflicts
- Advanced Git Topics
    - Rebasing
    - Stashing
    - Cherry picking
- Any extra time: project time

## Working on Teams

There are two main ways to work with other people on GitHub. For larger projects, or especially if you are working with the same people on many different projects or repos, GitHub organizations provide a useful way of organizing people and code. Or, for smaller projects, you can directly add collaborators to a repo.

### Creating Organizations

There are two main benefits to creating an organization on GitHub. One is that repos can be owned by an organization, rather than an individual, which will mean the GitHub URL starts with the organization name, which looks cool. The other benefit is, especially if you are working with the same group of people on many projects/many repos, you can add them to your organization once, and they'll get some access automatically to new repos in that organization.

To create an organization on GitHub, you use the same plus button at the top right of the page as for creating a new repo. You'll need to invite people into your organization, and there are also settings for what permissions people in your organization have by default - note that by default, org members do not have write access to repos, so they will not be able to push code to the repo until you give them permission or change that setting.

### Adding Directly to Repos

Adding collaborators directly to a repo is the lightest-weight, easiest way to work with other people on a one-off coding project.

To add collaborators to a repo, visit the "settings" page for your repo, choose "collaborators" on the left, and enter the email addresses or GitHub usernames of the people you would like to collaborate with. Note that the people you invite will need to check their emails and accept the invitation to be able to collaborate on that repo.

## Code Review

A common practice in software engineering is code review. After an engineer finishes writing code, before they merge it into their main branch or otherwise make that code available to everyone, they get a review of that code from other people on the team. Code review has a few important purposes:

* Ensures code does what it says it does
* Provides a safeguard against malicious code (say, code that puts a vulnerability in the project)
* Allows engineers to learn from each others' coding practices

There are lots of things that engineers might notice in a code review and ask for revisions:

* Style issues: indentation or capitalization issues
* Naming issues: unclear or misleading function or variable names
* Comments: out-of-date, misleading, or missing comments
* Small coding issues: a small inefficiency
* Larger coding issues
* A complete rewrite of the entire project

I have personally seen code reviews with all of these outcomes.

## Merge Conflicts

One issue that arises once you have multiple people working on the same piece of code is merge conflicts. This happens when multiple branches have edits to the same part of the same file. When you attempt to merge those branches together, git doesn't know which version of the file to use as the most up-to-date version, so it needs you to manually step in and show it what the merged version of the code should look like.

## Avoiding Merge Conflicts

There are three main parts to avoiding merge conflicts. One is the obvious solution: try not to have two different people working on the same chunk of code at the same time. Even if you are working in the same file as someone else, as long as you are not touching the same lines of code, you won't cause a merge conflict.

Secondly, each time that a team member merges a change into the main branch, it is the responsibility of *all other team members* to merge that new change into their feature branch. On teams I've worked on in the past, we've done this by having each person on the team yell (or message) "PULL!", at which point everyone pulls the code into their branch by following these steps:

```bash
# you are working on a feature branch, and then someone yells "pull!"
# get to a stopping point in your code, add and commit
git status # make sure you know which branch you're working on
git checkout main # switch to the main branch
git pull # pulls the new code from GitHub's main branch to your computer's main branch
git checkout yourfeaturebranch # switch back to your own branch
git merge main -m "merge" # merge the main branch into your own branch
```
Running that `merge` command is when you might discover a merge conflict; as git tries to combine both versions of the code, that's when it might notice that the new code touches some of the same lines of code that you have already edited. When that happens, you'll need to resolve that merge conflict on your machine before you continue.

## Resolving Merge Conflicts

When a merge conflict happens, don't panic! They are a natural part of a git development lifecycle, and they're resolvable. My best advice: Run `git status` often during a merge conflict, because it will tell you exactly what you need to run next to get out of the merge conflict.

When you have a merge conflict, the first step is to open your text editor and go to the file(s) where the conflict is. You'll find the merge conflict highlighted in VSCode; it'll have less-than and greater-than signs surrounding it, showing the two different versions of the code. Your job is to pick out whether the code SHOULD have one of those versions of code, or both, or something in between, and edit the code to its correct version, including removing the `>>>>` and `<<<<` lines.

## Lab: Creating and Resolving Merge Conflicts

1. Split your team into two halves. Each half will work together.
1. If you have not already done so, create a shared repo among your team members where you will keep your project code, and put a basic README file in that repo. Ensure that the driver-computers have the repo cloned.
1. Simultaneously, on each driver computer, each half should check out a new branch (`git checkout -b newbranchname`), and on that branch, should make an edit to the first paragraph of the README file. Make different changes from each other!
1. Each half should add, commit, and push their changes on their branches.
1. The first half of the team should make a pull request from their branch into the main branch, and merge their new pull request.
1. The second half of the team should now make a pull request. You should notice that GitHub tells you it is "unable to merge" due to a conflict. This is because you did not pull down the code after the first half of the team merged their changes into the main branch.
1. On the second half of the team, use the steps above to check out the main branch, pull the code, and merge it into your feature branch, at which point you will see the merge conflict happening.
1. Resolve the merge conflict by editing the README file to contain the "correct" paragraph. Add and commit it, and push your changes to the same branch you've been working on.
1. Your pull request will automatically update to say that it is mergeable now. Merge the pull request.
1. Check the README file to make sure you haven't accidentally left in any of the merge conflict markers.
1. Switch halves! Let the other half of the team get experience in resolving a pull request.