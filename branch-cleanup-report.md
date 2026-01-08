# Remote branch cleanup report (origin)

Date: 2026-01-08  
Repo: `operational-dashboard-and-field-management-system-9156-9165`  
Objective: Remove all remote branches on `origin` except `main` (preserve `origin/main`).

## Remote branches observed (before)
- `origin/cga-cg3d1f8e67`
- `origin/cga-cm57c54f58`
- `origin/kavia-main`
- `origin/main`
- `origin/HEAD -> origin/kavia-main` (symbolic ref)

## Deletion results
### Deleted successfully
- `origin/cga-cg3d1f8e67`
- `origin/cga-cm57c54f58`

### Could not be deleted
- `origin/kavia-main`
  - Remote error: `refusing to delete the current branch: refs/heads/kavia-main`
  - This indicates `kavia-main` is currently the default branch on the remote (GitHub prevents deletion of the default branch).

## Remote branches observed (after)
- `origin/kavia-main`
- `origin/main`
- `origin/HEAD -> origin/kavia-main`

## Notes / required manual step (if you truly need only origin/main to remain)
To delete `origin/kavia-main`, change the default branch in the GitHub repository settings from `kavia-main` to `main`, then retry:
- `git push origin --delete kavia-main`
