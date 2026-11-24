# Github-connected-

This repository is configured for GitHub Pages and Lovable-compatible repository
updates.

## Why Lovable/GitHub connections can return 404

A 404 from the Lovable GitHub App means the Lovable OAuth/app installation
cannot reach the exact repository path stored for a project. GitHub Pages has
separate 404 behavior and requires a valid entry file. Common causes are:

- the Lovable GitHub App was uninstalled or lost access to selected repositories;
- a repository was renamed, transferred, or excluded after it was connected;
- GitHub Pages has no `index.html`, or the workflow has not deployed it; and
- an SPA route is being refreshed without a Pages 404 fallback.

## Repair and reconnect

1. Restore the repository's original owner/name if it was renamed or transferred.
2. In GitHub, open **Settings → Integrations → GitHub Apps**, ensure the Lovable
   app is installed and granted access to this repository.
3. Merge changes pushed to `main`, or run the **Deploy GitHub Pages** workflow
   manually. The workflow forces a fresh deployment on every push to `main`.
4. Reconnect Lovable from the project only after GitHub App access is restored.
   Lovable reconnects by creating a repository; changing Lovable's app settings
   does not replace a missing or invalid repository path.
