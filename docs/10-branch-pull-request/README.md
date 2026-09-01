# Practice: Branching and Opening a Pull Request

In practice, when you begin to utilize agentic coding harnesses, we will
have you try to avoid committing directly to `main`. Instead, changes are
made on a separate branch and merged in through a pull request (PR), which
gives you (and your collaborators) a chance to review a diff
before it becomes part of the shared history. In this exercise you'll
practice that full cycle: branch, commit, push, open a PR, and merge it on
GitHub. This will become an essential cycle when you are utilizing coding
agents to actually ensure that your codebase remains functional and a way of
enforcing that you understand and validate all changes being made on your behalf.

## Steps

1. Make sure `main` is up to date, then create a new branch off of it.

```
git checkout main             # switch to main
git pull                      # bring your local main up to date with the remote
git checkout -b my-first-pr   # create and switch to a new branch off main
```

2. Make a small, easy-to-review change to
   [`merge_conflict.md`](../../merge_conflict.md), for example adding a line
   with some random words under ##status.

3. Stage and commit the change, then push the branch and set it to track the
   remote branch of the same name.

```
git add merge_conflict.md                                  # stage the file's changes
git commit -m "Add some random words to merge_conflict.md"   # commit them on my-first-pr
git push -u origin my-first-pr                              # push the branch and set it to track the remote
```

4. Go to the repository on GitHub. You should see a banner prompting you to
   open a pull request for the branch you just pushed. Click **Compare &
   pull request**.

5. Fill out a short title and description describing your change, then click
   **Create pull request**.

6. Look over the **Files changed** tab to see the diff exactly as a
   reviewer would. This is the same view you should get in the habit of
   checking before merging any PR, including ones containing AI-generated
   changes.

7. Merge the pull request from the GitHub UI (**Merge pull request**), then
   confirm the deletion of the remote branch when prompted.

8. Back in VS Code, switch to `main`, pull down the merged change, and clean
   up your local branch.

```
git checkout main       # switch back to main
git pull                # pull down the merge commit GitHub just made
git branch -d my-first-pr   # delete the now-merged local branch
```

## Checklist

- [ ] Created a new branch off `main`
- [ ] Made and committed a small change on that branch
- [ ] Pushed the branch to GitHub
- [ ] Opened a pull request
- [ ] Reviewed the diff in the Files changed tab
- [ ] Merged the pull request on GitHub
- [ ] Pulled the merged change back to `main` and deleted the local branch
