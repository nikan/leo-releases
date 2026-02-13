# Leo VSCode Extension - Releases

Welcome to the official releases repository for Leo, your AI-powered workflow assistant for Visual Studio Code.

## 📥 Installation

Leo is a Visual Studio Code extension. To install:

### From VSCode Marketplace (Recommended)

1. Open Visual Studio Code
2. Go to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
3. Search for "Leo AI Workflow Assistant"
4. Click Install

### Manual Installation from Release

1. Visit the [Releases](https://github.com/nikan/leo-releases/releases) page
2. Download the latest `.vsix` file
3. In VSCode, go to Extensions view
4. Click the "..." menu at the top
5. Select "Install from VSIX..."
6. Choose the downloaded `.vsix` file

## 🔒 Verification

Each release includes checksums for verification. Download the `checksums.txt` file from the release page to verify the integrity of the `.vsix` file.

### Verify on Linux/macOS

```bash
# Download checksums
curl -LO https://github.com/nikan/leo-releases/releases/latest/download/checksums.txt

# Verify the download
sha256sum leo-vscode-extension.vsix
cat checksums.txt | grep leo-vscode-extension.vsix
```

### Verify on Windows

```powershell
# Download checksums.txt first, then:
CertUtil -hashfile leo-vscode-extension.vsix SHA256
# Compare the output with the hash in checksums.txt
```

## 📚 Documentation

- [User Guide](./docs/README.md)
- [Security Policy](./SECURITY.md)
- [Changelog](./CHANGELOG.md)

## 🏗️ Build Process

**Note**: The Leo extension executables and builds are created in a private repository. This public repository is used solely for distributing releases to end users.

## 🤝 Contributing

This repository contains release binaries only. For bug reports and feature requests, please open an issue in this repository. Source code contributions are managed in the private development repository.

## 📄 License

Leo is distributed as freeware. See [LICENSE](./LICENSE) for details.

## 🔐 Security

For reporting security vulnerabilities, please see our [Security Policy](./SECURITY.md).
