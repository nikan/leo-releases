# Release Management Best Practices

This document explains how the leo-releases repository is configured to keep binary releases as GitHub Release assets rather than storing them in the git repository.

## Why Keep Binaries Out of the Repository?

1. **Repository Size**: Binary files significantly increase repository size and slow down clone/fetch operations
2. **Git Efficiency**: Git is optimized for text files, not large binaries
3. **Version Control**: Binary files bloat git history permanently, even after deletion
4. **Distribution**: GitHub Releases provides a better user experience for downloading executables
5. **Bandwidth**: Storing binaries in git increases bandwidth costs for all operations

## How This Repository is Configured

### 1. .gitignore File

The `.gitignore` file blocks all common executable and binary formats from being committed:
- Executables: `.exe`, `.dll`, `.so`, `.dylib`, `.app`
- Unix/Linux binaries: `.out`, `.bin`, `leo`, `leo-*`
- Installers: `.dmg`, `.pkg`, `.msi`, `.msix`
- Archives: `.zip`, `.tar.gz`, `.7z`, etc.
- Build directories: `build/`, `dist/`, `target/`, `bin/`

### 2. GitHub Actions Workflow

The `.github/workflows/release.yml` workflow automates release creation:
- Triggers on version tags (e.g., `v1.0.0`)
- Creates a GitHub Release automatically
- Can be extended to upload binary assets

### 3. Documentation

The README clearly states that binaries should be distributed via GitHub Releases.

## Creating a New Release

### Manual Process

1. Build your binaries locally
2. Create a new release on GitHub: https://github.com/nikan/leo-releases/releases/new
3. Choose or create a tag (e.g., `v1.0.0`)
4. Upload your binary files as release assets
5. Publish the release

### Automated Process

1. Tag your commit: `git tag v1.0.0`
2. Push the tag: `git push origin v1.0.0`
3. The GitHub Actions workflow will create the release
4. You can then add binary assets manually or extend the workflow to upload them automatically

## Extending the Workflow

To automatically upload binaries, modify `.github/workflows/release.yml`:

```yaml
- name: Upload Release Asset
  uses: actions/upload-release-asset@v1
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  with:
    upload_url: ${{ steps.create_release.outputs.upload_url }}
    asset_path: ./path/to/your/binary
    asset_name: leo-linux-amd64
    asset_content_type: application/octet-stream
```

## Verification

To verify that binaries are properly ignored:

```bash
# Create some test binaries
touch leo-test.exe leo-linux-amd64 release.zip

# Check git status (should show nothing)
git status --short

# Clean up
rm leo-test.exe leo-linux-amd64 release.zip
```

## Summary

✅ Binary files are blocked by `.gitignore`
✅ Releases are automated via GitHub Actions
✅ Documentation guides users to GitHub Releases
✅ Repository remains lightweight and efficient
