# Make MAVSDK Release

These are the instructions on how to get a release out the door.

> **Note** The idea is of course to automate this as much as possible!

## MAVSDK part

1. Check if all open pull requests are merged that need to go in.
1. Check that CI on `develop` passed.
1. Merge `develop` into `master`:
   ```
   git switch develop
   git pull
   git switch master
   git pull
   git merge develop
   git tag vX.Y.Z
   git push origin master vX.Y.Z
   ```
1. The new `master` branch needs to be merged into `develop` so that we have the release tag in the history.
   ```
   git switch develop
   git merge master
   ```
1. - Generate changelog using `tools/generate_changelog.py --token TOKEN_FROM_GITHUB --verbose --tag vX.Y.Z`.
   - If it finds old/wrong PRs, wait a bit or create the release from the tag in the [GitHub UI](https://github.com/mavlink/MAVSDK/releases).
   - Once it finds the correct PRs it will check all of them for labels. Make sure all merged PRs have sensible labels (e.g. `enhancement`, `bug`, or `feature`).
   - Copy the changelog text to the [release](https://github.com/mavlink/MAVSDK/releases).
1. Check later if all artifacts have been uploaded correctly to the release.
1. Update the Arch AUR repository. This depends on the AUR maintainter's credentials (currently julianoes).
   - Use the repo: `ssh://aur@aur.archlinux.org/mavsdk.git`.
   - Bump the version in `pkgver=X.Y.Z`.
   - Check PKGBUILD: `namcap PKGBUILD`.
   - Try to make pkg: `makepkg`.
   - Update `.SRCINFO`: `makepkg --printsrcinfo > .SRCINFO`.
   - Commit and push.
1. Update the brew repo. Steps for macOS:
   - `export HOMEBREW_GITHUB_API_TOKEN=<GITHUB API TOKEN>`
   - `brew bump-formula-pr mavsdk --tag=vX.Y.Z --revision=<GIT HASH>`
   - This should then open the browser with the pull request already created.

## MAVSDK-docs part

1. [Generate the docs](build.md#build_api_reference) and update the reference docs.
1. Check or update the examples in the docs.
1. Create a branch off `develop` for the release
   - Create the branch
     ```
     git switch develop
     git pull
     git switch -c vX.Y.Z
     ```
   - Modify **book.json** in the vX.Y.Z branch to change the value of `github_branch` to match the new branch: `"github_branch": "vX.Y.Z"`
   - Push the branch to the upstream repo
     ```
     git push origin vX.Y.Z
     ```
1. Add the branch to the version checker in develop branch [book.json](https://github.com/mavlink/MAVSDK-docs/blob/develop/book.json) (see pattern below `versions`).

## Other

1. Post a note on Slack #mavsdk.
