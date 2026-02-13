# leo-releases
Executables of the leo AI Workflow Assistant

## Release Distribution

This repository uses **GitHub Releases** to distribute executables and binaries. Binary files are **NOT** stored directly in the git repository to keep the repository lightweight and efficient.

### How to Download

Visit the [Releases page](https://github.com/nikan/leo-releases/releases) to download the latest version of leo for your platform.

### How to Create a New Release

Releases are created using GitHub Actions workflows or manually via the GitHub interface:

1. Create a new tag: `git tag v1.0.0`
2. Push the tag: `git push origin v1.0.0`
3. The automated workflow will build and upload release assets
4. Alternatively, create a release manually and upload assets via the GitHub UI

**Note**: Do not commit binary files or executables to this repository. All releases should be distributed as GitHub Release assets.
