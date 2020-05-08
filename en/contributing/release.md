# Make MAVSDK Release

These are the instructions on how to get a release out the door.

> **Note** The idea is of course to automate this as much as possible!

1. Check if all open pull requests are merged, that need to go in.
1. Check that CI on `develop` passed.
1. [Generate the docs](build.md#build_api_reference) and update the reference docs.
1. Check or update the examples in the docs.
1. Run link checker and fix any breaks.
1. Merge `develop` into `master`:
   ```
   git switch develop
   git pull
   git switch master
   git pull
   git merge develop
   ```
1. Create a branch off `develop` for the release
   - Create the branch
     ```
     git switch develop
     git pull
     git checkout -b vX.Y.Z
     ```
   - Modify **book.json** in the vX.Y.Z branch to change the value of `github_branch` to match the new branch: `"github_branch": "vX.Y.Z"`
   - Push the branch to the upstream repo
     ```
     git push upstream vX.Y.Z
     ```
1. Add the branch to the version checker in develop branch [book.json](https://github.com/mavlink/MAVSDK-docs/blob/develop/book.json) (see pattern below `versions`).
1. - Generate changelog using `tools/generate_changelog.py --token TOKEN_FROM_GITHUB --verbose --tag vX.Y.Z`.
   - If it finds old/wrong PRs, wait a bit or create the release from the tag in the [GitHub UI](https://github.com/mavlink/MAVSDK/releases).
   - Once it finds the correct PRs it will check all of them for labels. Make sure all merged PRs have sensible labels (e.g. `enhancement`, `bug`, or `feature`).
   - Copy the changelog text to the [release](https://github.com/mavlink/MAVSDK/releases).
1. Check later if all artifacts have been uploaded correctly to the release.
1. Merge `develop` into `master` for MAVSDK-docs as well.
1. Update the Arch AUR repository.
   TODO: how
1. Update the brew repo
   TODO: how
1. Update the branches in
1. Post a note on Slack #mavsdk.
