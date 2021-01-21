![Warning!](https://cdn.searchenginejournal.com/wp-content/uploads/2017/05/shutterstock_389230123-760x400.jpg)

# Instructions

Please follow these guided set of instructions thoroughly for getting yourself as a contributor.

## Submitting a Pull Request

### Best Practices to send Pull Requests:
  - Fork the [project](https://github.com/shobhi1310/contributions) on GitHub
  - Clone the project locally into your system.
```console
$ git clone https://github.com/your-username/contributions.git
```
  - Make sure you are in the `master` branch.
```console
$ git checkout master
```
  - Create a new branch with your name as name of the branch before adding and commiting your changes.
  - Make necessary changes in [this](./Template.html) format
```console
$ git checkout -b branch-name
```
  - Add the files you changed. (avoid using `git add .`)
```console
$ git add file-name
```
  - Follow the style conventions for a [meaningful commit message](COMMIT_MESSAGE.md).
```console
$ git commit
```
  - If you forgot to add some changes, you can edit your previous commit message.
```console
$ git commit --amend
```
  - Squash multiple commits to a single commit. (example: squash last two commits done on this branch into one)
```console
$ git rebase --interactive HEAD~2 
```
  - Push this branch to your remote repository on GitHub.
```console
$ git push origin branch-name
```
  - If any of the squashed commits have already been pushed to your remote repository, you need to do a force push.
```console
$ git push origin remote-branch-name --force
```
  - Follow the Pull request template and submit a pull request with a motive for your change and the method you used to achieve it to be merged with the `master` branch.
  - If you can, please submit the pull request with the fix or improvements including tests.
  - During review, if you are requested to make changes, rebase your branch and squash the multiple commits into one. Once you push these changes the pull request will edit automatically.


## Configuring remotes
When a repository is cloned, it has a default remote called `origin` that points to your fork on GitHub, not the original repository it was forked from. To keep track of the original repository, you should add another remote called `upstream`.

1. Set the `upstream`.
```console
$ git remote add upstream https://github.com/shobhi1310/contributions.git
```
2. Use `git remote -v` to check the status. The output must be something like this:
```console
  > origin    https://github.com/your-username/contributions.git (fetch)
  > origin    https://github.com/your-username/contributions.git (push)
  > upstream  https://github.com/openMF/contributions.git (fetch)
  > upstream  https://github.com/openMF/contributions.git (push)
```
3. To update your local copy with remote changes, run the following: (This will give you an exact copy of the current remote. You should not have any local changes on your master branch, if you do, use rebase instead.)
```console
$ git fetch upstream
$ git checkout master
$ git merge upstream/master
```
4. Push these merged changes to the master branch on your fork. Ensure to pull in upstream changes regularly to keep your forked repository up to date.
```console
$ git push origin master
```
5. Switch to the branch you are using for some piece of work.
```console
$ git checkout branch-name
```
6. Rebase your branch, which means, take in all latest changes and replay your work in the branch on top of this - this produces cleaner versions/history.
```console
$ git rebase master
```
7. Push the final changes when you're ready.
```console
$ git push origin branch-name
```

## After your Pull Request is merged
After your pull request is merged, you can safely delete your branch and pull the changes from the main (upstream) repository.

1. Delete the remote branch on GitHub.
```console
$ git push origin --delete branch-name
```
2. Checkout the master branch.
```console
$ git checkout master
```
3. Delete the local branch.
```console
$ git branch -D branch-name
```
4. Update your master branch with the latest upstream version.
```console
$ git pull upstream master
```

## Navigation Links
- [About the author](./About_Me)
- [Contributors](./Contributors)
- [Ideology](./Ideology)
- [Home](./)