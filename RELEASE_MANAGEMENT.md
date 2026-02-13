# Release Management for Leo VSCode Extension

This document explains the release process for the Leo VSCode extension and how this repository is configured to distribute releases.

## Build and Release Process

### Build Location

**Important**: The Leo VSCode extension is built and compiled in a **private repository**. The source code, build scripts, and compilation process are not publicly available.

This public repository (`nikan/leo-releases`) serves as:
- A distribution point for release binaries
- A public location for documentation
- An issue tracker for user feedback and bug reports

### Why Keep Binaries Out of the Repository?

1. **Repository Size**: Binary files significantly increase repository size and slow down clone/fetch operations
2. **Git Efficiency**: Git is optimized for text files, not large binaries
3. **Version Control**: Binary files bloat git history permanently, even after deletion
4. **Distribution**: GitHub Releases provides a better user experience for downloading extensions
5. **Bandwidth**: Storing binaries in git increases bandwidth costs for all operations

## How This Repository is Configured

### 1. .gitignore File

The `.gitignore` file blocks all common executable and binary formats from being committed:
- VSCode extension files: `.vsix`
- Executables: `.exe`, `.dll`, `.so`, `.dylib`, `.app`
- Unix/Linux binaries: `.out`, `.bin`
- Installers: `.dmg`, `.pkg`, `.msi`, `.msix`
- Archives: `.zip`, `.tar.gz`, `.7z`, etc.
- Build directories: `build/`, `dist/`, `target/`, `bin/`, `out/`

### 2. GitHub Actions Workflow

The `.github/workflows/release.yml` workflow automates release creation:
- Triggers on version tags (e.g., `v1.0.0`)
- Creates a GitHub Release automatically
- Release assets (`.vsix` files) are uploaded manually from the private build repository

### 3. Documentation

The README clearly states that this is a VSCode extension and that builds are created in a private repository.

## Creating a New Release

### Process Overview

Since builds are created in the private repository, the release process follows these steps:

1. **Build in Private Repo**: 
   - The extension is built and packaged as a `.vsix` file in the private repository
   - Build artifacts include the extension package and checksums

2. **Create Release in Public Repo**:
   - Create a new release on GitHub: https://github.com/nikan/leo-releases/releases/new
   - Choose or create a tag (e.g., `v1.0.0`)
   - Upload the `.vsix` file and `checksums.txt` from the private build
   - Publish the release

3. **Automated Workflow**:
   - Tag the commit in this repository: `git tag v1.0.0`
   - Push the tag: `git push origin v1.0.0`
   - The GitHub Actions workflow will create the release structure
   - Manually upload the `.vsix` and checksums files from the private build

## VSCode Extension Specifics

### Extension Package Format

The Leo extension is distributed as a `.vsix` file, which is the standard VSCode extension package format.

### Installation Methods

Users can install the extension:
1. From the VSCode Marketplace (recommended)
2. By downloading the `.vsix` file from GitHub Releases and installing manually

### Version Compatibility

Each release should specify:
- Minimum VSCode version required
- Supported operating systems
- Any platform-specific considerations

## Verification

To verify that binaries are properly ignored:

```bash
# Create some test files
touch leo-extension.vsix checksums.txt test-binary

# Check git status (binary files should be ignored)
git status --short

# Clean up
rm leo-extension.vsix checksums.txt test-binary
```

## Summary

✅ Extension built in private repository
✅ Binary files are blocked by `.gitignore` in public repo
✅ Releases distributed via GitHub Releases
✅ Public repository remains lightweight and efficient
✅ Documentation guides users to proper installation methods
