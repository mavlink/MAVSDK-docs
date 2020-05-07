# Make MAVSDK Release

These are the instructions on how to get a release out the door.

> **Note** The idea is of course to automate this as much as possible!

1. Check if all open pull requests are merged, that need to go in.
2. Check that CI on `develop` passed.
3. [Generate the docs](build.md#build_api_reference) and update the reference docs.
4. Check or update the examples in the docs.
5. Merge `develop` into `master` and tag the release:
   ```
   git switch develop
   git pull
   git switch master
   git pull
   git merge develop
   git tag vX.Y.Z
   git push origin master vX.Y.Z
   ```
6. - Generate changelog using `tools/generate_changelog.py --token TOKEN_FROM_GITHUB --verbose --tag vX.Y.Z`.
   - If it finds old/wrong PRs, wait a bit or create the release from the tag in the [GitHub UI](https://github.com/mavlink/MAVSDK/releases).
   - Once it finds the correct PRs it will check all of them for labels. Make sure all merged PRs have sensible labels (e.g. `enhancement`, `bug`, or `feature`).
   - Copy the changelog text to the [release](https://github.com/mavlink/MAVSDK/releases).
7. Check later if all artifacts have been uploaded correctly to the release.
8. Merge `develop` into `master` for MAVSDK-docs as well.
9. Update the Arch AUR repository.
   TODO: how
10. Update the brew repo
   TODO: how
11. Update the branches in
12. Post a note on Slack #mavsdk.
