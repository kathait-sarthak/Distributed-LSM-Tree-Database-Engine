# GitHub Upload Instructions

Use this bundle as a small, review-friendly commit in your friend repo.

## 1. Copy this folder into the target repository

```bash
cp -R pending_upload /path/to/friend-repo/
```

## 2. Add and commit the files

```bash
git add pending_upload
git commit -m "Add remaining Raft handoff work"
```

## 3. Push to a branch

```bash
git push origin <branch-name>
```

## 4. Open a pull request

Open a PR and mention that this bundle connects the previously completed storage and RPC progress to the still-pending Raft contract layer.

## Notes

This workflow keeps the new work in a standalone folder that is easy to review and merge without disturbing the core implementation.
