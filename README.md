# Git Workshop

> This guide is developed to back the Git and Source Control Fundamentals session for the Insight Accelerated Consulting Experience (ACE) program. 

## Instructions

### Basics

1. Clone the repo using your method of choice. SSH is recommended.
   1. Ensure you have [added your SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).
   1. Clone the repo using `git clone git@github.com:marcdenning/ace-git-workshop.git`.
1. Check the `git status` of the repo.
1. Edit the [`tips.md`](/tips.md) file and commit your change using `git commit -am "Your message"`.
1. Review the `git log`.
1. Share your commit with `git push`.
1. _Optional:_ In another clone of the repo, execute `git fetch` and review the updates.

### Pull Requests

1. Checkout a new branch with `git checkout -b username`.
1. Create a file in [`participants`](/participants/) with your username as the file name and a Markdown extension (ex. `mdenning.md`).
   1. Include your name, a profile picture if one is available, and any other biographical information you are comfortable releasing publicly.
   1. You may use [Gravatar](https://en.gravatar.com/) for a public image. Generate the MD5 hash of your Insight or personal email address, and use URL `https://www.gravatar.com/avatar/HASH?s=200` for your image.
      1. [MD5 Hash Generator](https://www.md5hashgenerator.com/) is an online tool you may use to generate your hash.
1. Add your new file and commit.
1. Push the new branch and commit with `git push -u origin username`.
1. Open the GitHub repository in your browser, create a PR, and complete the PR - merging the code into `main`.
1. Checkout the main branch and use `git pull` to get your the update locally.
1. Delete the branch in GitHub, then on your local machine using `git branch -D username`.

### .gitignore

1. Review the [`.gitignore`](/.gitignore) file.
1. Create a `file.txt`.
1. Add `file.txt` to `.gitignore`.
1. Review `git status`.
1. Hard reset the repo with `git reset --hard`.
1. Follow these next steps to review "ignoring" a file that is already tracked.
    1. Checkout a new branch with `git checkout -b file` and create `file.txt` again.
    1. Add the file and commit with `git add file.txt && git commit -m "Add new file."`.
    1. Edit `.gitignore` to add `file.txt`, then commit the change.
    1. Edit `file.txt` and see if the changes show up in `git status`.
    1. Use `git rm --cached file.txt` to remove the change from the Git index, but not the file system.
        1. _Note:_ this will remove the file from other's machines when the commit is pulled or merged into their system.
    1. Review `git status` and commit the change.
    1. Edit `file.txt` again and check if the changes show up in `git status`.
    1. Checkout the main branch with `git checkout main`, then delete your new branch with `git branch -D file`.

### Merging and Rebasing

1. Create a new branch with `git checkout -b file`.
1. Create a `file.txt` and commit it. Note the commit ID.
1. Checkout yet another branch with `git checkout -b file2`, create `file2.txt` and commit the file.
1. Review `git log` to see both commits.
1. Checkout the main branch and review `git log` - the new files' commits are not present.
1. Merge the second branch with `git merge file2` and review `git log` - everything is now present!
1. Use `git reset --hard <commit-id>` to reset to the first file's commit.
1. Checkout the second branch with `git checkout file2` and then run `git rebase main` and review `git log` to see the first file's commit.
1. Checkout the main branch, delete both file branches, and run `git reset --hard origin/main` to sync back up with the remote.

### Merge Conflicts

1. Checkout a new branch with `git checkout -b file`.
1. Create `file.txt` and add a phrase to the first line.
1. Add and commit `file.txt`.
1. Checkout another branch with `git checkout -b file-mod`.
1. Edit `file.txt` and add a second line with another phrase.
1. Commit the change to `file.txt`.
1. Checkout the first branch `git checkout file`.
1. Edit `file.txt` again to add a third phrase on the second line. Note that your second line from branch `file-mod` is not present.
1. Commit this change to `file.txt`.
1. Attempt to merge the `file-mod` branch with `git merge file-mod`.
1. Git should warn you that there are conflicts.
1. Open `file.txt` and note the lines that Git added to show the conflicts.
1. Edit the file and resolve the conflicts as you see fit, removing the lines Git added for you.
1. Add and commit `file.txt`, this completes the merge.
1. Check `git status` and `git log` to review the results of the changes.
1. Checkout the main branch and delete the two file branches to clean up.
