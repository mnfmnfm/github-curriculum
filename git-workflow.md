# Full Git Workflow

This is the full Git workflow that we will build to by day 2 of the workshop. Note that before day 2, we will not know all of the commands in this document, so it might still be helpful, but 

## Setting Up Your Project

* One member of your team goes onto GitHub and creates a new repo with a README file.
* That team member adds all team members as collaborators. Collaborators check their emails to accept the invitation.
* All team members run `git clone <repo URL>` to clone the repo onto their machines.

## Ongoing Coding

* Check out a new branch to work on each new feature: `git checkout -b <featurebranchname>`
* Write code on that branch
    * Each time you finish a sub-task and want to make a commit:
    * `git add .`
    * `git commit -m "commit description"`
* When you finish working on that feature: `git push -u origin <featurebranchname>`
* Using the link in the terminal, or via the repo on GitHub, create a pull request, and ask a teammate to review the request
* If your teammate has requested changes, make those changes on the same feature branch, `add, commit, push`, and ask your teammate to review again
* Once your teammate has approved the pull request, merge it into your main branch
* Yell "PULL!"

## When Someone Yells "PULL!" (Including Yourself)

* Finish up your current subtask; get your code into a stable enough state that you're willing to commit it. `add, commit`.
* Switch to the main branch: `git checkout main`
* Pull down the new code: `git pull`
* Switch back to your feature branch: `git checkout <featurebranchname>`
* Merge in the new changes to your feature branch: `git merge main`
* Read your terminal messages! This will either:
    * Open a text editor for you to enter a commit message - hooray! The default message is generally fine, and it all worked
    * Tell you there is a merge conflict - boo! See instructions below

## Merge Conflict on the Terminal

* First order of business, `git status` is your friend and will help you navigate the merge conflict process. Use `git status` often while resolving merge conflicts.
* Open your text editor and navigate to the files where the merge conflict is happening. (If you're not sure, `git status` will tell you which files have a conflict.)
* Find a merge conflict - it will be surrounded by lines of code with less-than and greater-than signs, like `>>>>>>>>` and `<<<<<<`.
* Look at the two different sections of code there - one was written by you, and the other was written by your teammate. Decide whether you need just one of those pieces of code, or both of them, and edit the code to look correct. While you're editing, also remove the `>>>>>` and `<<<<<` lines.
* There might be multiple merge conflicts in the same file - scroll through the file and make sure you've fixed them all!
* Mark that file as complete by adding it with `git add <filename.ext>`
* When you've finished resolving merge conflicts, test that your code is working as expected, to make sure you haven't missed any of the merge conflicts.
* Once you have marked all files as complete and tested your code, run `git commit -m "description of fixing the merge conflict"`. You have now resolved the merge conflict.

## Merge Conflict When Trying to Create Pull Request

* If you are trying to merge a pull request on GitHub and it says that there is a merge conflict, that means you have not pulled all of the recent changes into your branch on your computer - likely, you missed doing a "PULL!" step. Follow the directions in `When Someone Yells "PULL!"`, above.
