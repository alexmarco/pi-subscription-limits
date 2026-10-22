# Contributing

Thanks for helping improve Pi Subscription Limits. Contributions are welcome through GitHub pull requests.

## Development setup

1. Fork the repository and clone your fork.
2. Install Node.js 22 or newer and npm.
3. Run `npm install`.
4. Run `npm run check` before submitting changes. This checks formatting, lint, TypeScript types, and tests.

## Branches and pull requests

The project follows Gitflow. `main` contains released versions; `develop` is the integration branch. Create feature and bug-fix branches from `develop`, for example `feature/clearer-errors` or `bugfix/reset-time`, then open a pull request targeting `develop`. Release changes flow from `develop` to `main` through a release pull request.

Keep pull requests focused, describe the user-visible behavior, and add or update tests when behavior changes. All CI checks must pass before a pull request can be merged. Do not commit credentials, access tokens, or personal usage data.

## Commit messages and versions

Use Conventional Commits:

- `feat: add a capability` for a minor release.
- `fix: correct a behavior` for a patch release.
- `feat!:` or a `BREAKING CHANGE:` footer for a major release.
- `docs:`, `test:`, `chore:`, and other standard types for changes that do not independently trigger a release.

Release Please reads commits on `main`, updates `CHANGELOG.md` and `package.json`, and opens a release pull request. Configure the repository secret `RELEASE_PLEASE_TOKEN` with a fine-grained GitHub token that can write repository contents and pull requests; this lets checks run for release pull requests created by the workflow. Merging a release pull request creates the GitHub release and version tag. When a GitHub release is published, the publish workflow publishes the package to npm. Configure `NPM_TOKEN` with an npm publishing token before the first release. The `pi-package` keyword makes it eligible for discovery in the Pi package catalog.
