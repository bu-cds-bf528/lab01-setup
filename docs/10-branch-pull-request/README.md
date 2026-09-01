# Practice: Branching and Opening a Pull Request

So far you've been committing and merging directly on `main`, which is fine
for small, low-stakes changes you're confident in. But for anything you want
reviewed before it becomes part of the shared history - a larger change, a
collaborator's work, or (increasingly) a change an AI agent made on your
behalf - the standard workflow is to make the change on a separate branch and
merge it in through a pull request (PR) instead. A PR gives you a dedicated
diff view to review before anything lands.

In this exercise you'll practice that full cycle: branch, commit, push, open
a PR, and merge it on Github. This will become an essential habit once
you're using coding agents, as a way to ensure your codebase remains
functional and to enforce that you understand and validate every change
being made on your behalf.

## Steps

1. Make sure `main` is up to date, then create a new branch off of it.

```
git checkout main             # switch to main
git pull                      # bring your local main up to date with the remote
git checkout -b my-first-pr   # create and switch to a new branch off main
```

2. Make a small, easy-to-review change to
   [`merge_conflict.md`](../../merge_conflict.md), for example adding a line
   of text under the `## Status` heading.

3. Stage and commit the change, then push the branch and set it to track the
   remote branch of the same name.

```
git add merge_conflict.md                                  # stage the file's changes
git commit -m "Add some random words to merge_conflict.md"   # commit them on my-first-pr
git push -u origin my-first-pr                              # push the branch and set it to track the remote
```

4. Go to the repository on Github. You should see a banner prompting you to
   open a pull request for the branch you just pushed. Click **Compare &
   pull request**.

5. Fill out a short title and description describing your change, then click
   **Create pull request**.

6. Look over the **Files changed** tab to see the diff exactly as a
   reviewer would. This is the same view you should get in the habit of
   checking before merging any PR, including ones containing AI-generated
   changes.

7. Merge the pull request from the Github UI (**Merge pull request**), then
   confirm the deletion of the remote branch when prompted.

8. Back in VS Code, switch to `main`, pull down the merged change, and clean
   up your local branch.

```
git checkout main       # switch back to main
git pull                # pull down the merge commit Github just made
git branch -d my-first-pr   # delete the now-merged local branch
```

## Checklist

- [ ] Created a new branch off `main`
- [ ] Made and committed a small change on that branch
- [ ] Pushed the branch to Github
- [ ] Opened a pull request
- [ ] Reviewed the diff in the Files changed tab
- [ ] Merged the pull request on Github
- [ ] Pulled the merged change back to `main` and deleted the local branch
