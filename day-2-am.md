# Workshop Day 2

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

