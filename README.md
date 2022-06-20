# Git Workshop

> This guide is developed to back the Git and Source Control Fundamentals session for the Insight Accelerated Consulting Experience (ACE) program. 

## Instructions

### Basics

1. Clone the repo using your method of choice. SSH is recommended.
1. Check the `status` of the repo.
1. Edit the [`tips.md`](/tips.md) file and commit.
1. Review the log.
1. Push the commit.
1. In another clone of the repo, `fetch` and review updates.

### Pull Requests

1. Checkout a new branch.
1. Create a file in [`participants`](/participants/) with your username as the file name and a Markdown extension (ex. `mdenning.md`).
   1. Include your name, a profile picture if one is available, and any other biographical information you are comfortable releasing publicly.
   1. You may use [Gravatar](https://en.gravatar.com/) for a public image. Generate the MD5 hash of your Insight or personal email address, and use URL `https://www.gravatar.com/avatar/HASH?s=200` for your image.
      1. [MD5 Hash Generator](https://www.md5hashgenerator.com/) is an online tool you may use to generate your hash.
1. Add your new file and commit.
1. Push the new branch and commit.
1. Open the GitHub repository in your browser, create a PR, and merge.
1. Checkout the main branch and pull the update.
1. Delete the feature branch.

### .gitignore

1. Review the [`.gitignore`](/.gitignore) file.
1. Create a `file.txt`.
1. Add `file.txt` to `.gitignore`.
1. Review `git status`.
1. Hard reset the repo.
1. Checkout a new branch and create `file.txt` again.
1. Add the file and commit.
1. Edit `.gitignore` to add `file.txt` and commit.
1. Edit `file.txt` and see if the changes show up in `git status`.
1. Use `git rm --cached file.txt` to remove the change from the Git index, but not the file system.
   1. Note: this will remove the file from other's machines when the commit is pulled or merged into their system.
1. Review `git status` and commit the change.
1. Edit `file.txt` again and check if the changes show up in `git status`.
1. Delete your new branch.

### Merging and Rebasing

1. Create a new branch.
1. Create a `file.txt` and commit. Note the commit ID.
1. Checkout yet another branch, create `file2.txt` and commit.
1. Review `git log` to see both commits.
1. Checkout the main branch and review `git log` - the new files' commits are not present.
1. Merge the second branch and review `git log` - everything is now present!
1. Use `git reset --hard <commit-id>` to reset to the first file's commit.
1. Checkout the second branch and run `git rebase main` and review `git log` to see the first file's commit.
1. Delete both branches, checkout the main branch and run `git reset --hard origin/main` to sync back up with the remote.
