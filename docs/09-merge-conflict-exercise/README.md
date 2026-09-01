# Practice: Creating and Resolving a Merge Conflict

Merge conflicts happen whenever git can't automatically reconcile changes to
the same lines of a file made on two different branches. This is extremely
common when working in teams, and even more common now that you may be
reviewing and merging LLM-generated changes alongside your own. Knowing how
to read and resolve a conflict calmly is an essential git skill.

You don't need a collaborator to see this happen - it's just as common (and
just as easy to reproduce) when you make a change on a branch, then forget
about it and also edit the same line directly on `main` before merging.

In this exercise you will intentionally create a conflict in
[`merge_conflict.md`](../../merge_conflict.md) and resolve it using the
built-in merge editor in VS Code.

## Steps

1. Make sure your local `main` branch is up to date.

```
git checkout main   # switch to the main branch
git pull             # bring your local main up to date with the remote
```

2. Create a branch and edit the file.

```
git checkout -b conflict-branch   # create and switch to a new branch off main
```

Open `merge_conflict.md` and change the line under `## Status` to your own
text, for example `Edited on conflict-branch`. Save the file, then commit.

```
git add merge_conflict.md                        # stage the file's changes
git commit -m "Edit status line on conflict-branch"   # commit them on conflict-branch
```

3. Go back to `main` and edit the **same line** directly, without creating
   another branch. This simulates forgetting about your branch and
   continuing to work on `main` in the meantime.

```
git checkout main   # switch back to main (conflict-branch's commit stays on conflict-branch)
```

Edit the same line under `## Status` again, but this time to something
different, for example `Edited directly on main`. Save and commit.

```
git add merge_conflict.md                       # stage the file's changes
git commit -m "Edit status line directly on main"   # commit them directly on main
```

4. Now merge your branch into `main`. Because both `main` and
   `conflict-branch` edited the same line since they diverged, git will not
   be able to merge automatically.

```
git merge conflict-branch   # merge conflict-branch into main; will report a conflict
```

You should see a message that includes `CONFLICT (content): Merge conflict
in merge_conflict.md`.

5. Open `merge_conflict.md` in VS Code. In the Source Control panel, or in
   the banner above the conflict in the editor, click **Resolve in Merge
   Editor**. This opens a three-pane view: **Current Change** (your `main`
   commit) on the left, **Incoming Change** (`conflict-branch`) on the
   right, and the combined **Result** at the bottom.

   Hover over the conflicting block in the **Incoming Change** pane and
   click **Accept Change** to keep the `conflict-branch` version and send it
   into the Result. Once the conflict is resolved, click **Complete Merge**
   in the top right.

6. Stage the resolved file and complete the merge commit.

```
git add merge_conflict.md                                       # stage the resolved (conflict-marker-free) file
git commit -m "Merge conflict-branch, resolve status line conflict"   # complete the merge commit
```

7. Confirm the repo is clean and push your resolved `main` branch.

```
git status   # confirm there are no uncommitted changes or conflicts left
git push     # publish the merge commit to the remote
```

## Checklist

- [ ] Edited the same line of `merge_conflict.md` on a branch and on `main`
- [ ] Merged the branch into `main` and triggered a conflict
- [ ] Used VS Code's merge conflict UI to resolve the conflict
- [ ] Completed the merge commit
- [ ] Pushed the resolved `main` branch
