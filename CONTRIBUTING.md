# Contributing

Thanks for helping improve Pi Subscription Limits. Contributions are welcome through GitHub pull requests.

## Development setup

1. Fork the repository and clone your fork.
2. Install Node.js 22 or newer and npm.
3. Run `npm install`.
4. Run `npm run check` before submitting changes. This checks formatting, lint, TypeScript types, and tests.

## Branches and pull requests

The project follows Gitflow. `main` contains released versions; `develop` is the integration branch.

- Create feature and bug-fix branches from `develop`, for example `feature/clearer-errors` or `bugfix/reset-time`, and open a pull request targeting `develop`. Use a Conventional Commit title that describes the change. Merge these pull requests with **Squash and merge**; the squash commit uses the pull request title.
- Promote `develop` to `main` through a pull request titled `chore: promote develop to main`. Merge this pull request with **Create a merge commit** so the individual Conventional Commits remain visible to Release Please. Do not use a `feat:` or `fix:` promotion title; it would add a duplicate release-note entry.
- Merge Release Please's generated release pull request into `main` with **Create a merge commit**. Afterward, sync `main` back into `develop` through a pull request titled `chore: sync main back into develop`, using **Squash and merge**.

GitHub enforces linear history on `develop`, and rebase merging is disabled for the repository. Together, these settings leave squash merging as the only available strategy for pull requests into `develop`; `main` still permits merge commits for promotions and releases.

Keep pull requests focused, describe the user-visible behavior, and add or update tests when behavior changes. All CI checks must pass before a pull request can be merged. Do not commit credentials, access tokens, or personal usage data.

## Commit messages and versions

Use Conventional Commits:

- `feat: add a capability` for a minor release.
- `fix: correct a behavior` for a patch release.
- `feat!:` or a `BREAKING CHANGE:` footer for a major release.
- `docs:`, `test:`, `chore:`, and other standard types for changes that do not independently trigger a release.

Release Please reads Conventional Commits on `main`, updates `CHANGELOG.md` and `package.json`, and opens a release pull request. The repository secret `RELEASE_PLEASE_TOKEN` lets its pull requests trigger CI. Merging a release pull request creates the GitHub release and version tag. The publish workflow uses npm Trusted Publishing through GitHub OIDC; no long-lived npm token is required. The `pi-package` keyword makes the package eligible for discovery in the Pi package catalog.
