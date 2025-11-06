# MERGE POSTMORTEM
## Summary
- Used `git bisect` to find a buggy commit (commit `ca9419b`) that replaced `+` with `-` in the addition logic.
- Fixed the bug and used `git revert` to record the undo (created the revert commit).
- Demonstrated stash workflow: `git stash`, `git pull`, `git stash apply` and reapplied local edits to `app.js`.
- Commit graph preserves both the original buggy commit and the revert commit (no history rewriting).
- **Scenario:** repo-A and repo-B edited same line in README.md.
  - **Conflict:** Git showed conflict markers.
  - **Resolution:** Kept both lines:
  - this line is added by beta repo
  - this line is added by alpha repo
  - **Commands used:** git add README.md; git commit -m "merge: keep both Alpha and Beta edits in readme.md"; git push


![alt text](image-1.png)


![alt text](image-2.png)


![alt text](image.png)# MERGE POSTMORTEM
