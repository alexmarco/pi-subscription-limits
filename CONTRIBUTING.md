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

Release Please reads commits on `main`, updates `CHANGELOG.md` and `package.json`, and opens a release pull request. Merging that pull request creates the GitHub release and version tag. Release Please does not publish an npm package; install the extension through Pi using the GitHub repository URL.
