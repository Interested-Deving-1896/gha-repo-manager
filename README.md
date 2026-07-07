[update-readmes]   Mode: rewrite — migrating to template structure...
# gha-repo-manager

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/gha-repo-manager)

<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/gha-repo-manager.git
cd gha-repo-manager
```

## Usage


This action manages your repo from a yaml file. You can manage:

* branch protection
* labels
* repos
* secrets
* repo settings
* Files

See [examples/settings.yml](./examples/settings.yml) for an example config file. The schemas for this file are in [repo_manager.schemas](./repo_magager/schemas).

### File Management -- Experimental

File management can copy files from your local environment to a target repo, copy files from one location to another in the target repo, move files in the target repo, and delete files in the target repo.

File operations are performed using the Github BLOB API and your PAT. Each file operation is a separate commit.

This feature is helpful to keep workflows or settings file in sync from a central repo to many repos.

### Example workflow

```yaml
name: Run Repo Manager
on: [workflow_dispatch]
jobs:
  repo-manager:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    name: Checkout
    - name: Run RepoManager
      uses: andrewthetechie/gha-repo-manager@main
      with:
        # Apply your settings to the repo, can also be check to just check repo settings vs your file or validate, to validate your
        # file is valid
        action: apply
        settings_file: .github/settings.yml
        # need a PAT that can edit repo settings
        token: ${{ secrets.GITHUB_PAT }}

```

<!-- action-docs-inputs -->

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/gha-repo-manager`](https://github.com/Interested-Deving-1896/gha-repo-manager) and mirrored through:

```
Interested-Deving-1896/gha-repo-manager  ──►  OpenOS-Project-OSP/gha-repo-manager  ──►  OpenOS-Project-Ecosystem-OOC/gha-repo-manager
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream fork._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
[MIT](https://github.com/Interested-Deving-1896/gha-repo-manager/blob/main/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
