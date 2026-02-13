# Leo - AI Workflow Assistant

Welcome to the official releases repository for Leo, your AI-powered workflow assistant.

## 📥 Download

Download the latest version of Leo for your platform:

### Latest Release

Visit the [Releases](https://github.com/nikan/leo-releases/releases) page to download the latest version for your operating system:

- **Windows**: `leo-windows-amd64.exe`
- **macOS**: `leo-darwin-amd64` (Intel) or `leo-darwin-arm64` (Apple Silicon)
- **Linux**: `leo-linux-amd64` (64-bit) or `leo-linux-arm64` (ARM)

### Using curl or wget

```bash
# Linux (x86_64)
curl -LO https://github.com/nikan/leo-releases/releases/latest/download/leo-linux-amd64

# macOS (Intel)
curl -LO https://github.com/nikan/leo-releases/releases/latest/download/leo-darwin-amd64

# macOS (Apple Silicon)
curl -LO https://github.com/nikan/leo-releases/releases/latest/download/leo-darwin-arm64
```

## 🔒 Verification

Each release includes checksums for verification. Download the `checksums.txt` file from the release page.

### Verify on Linux/macOS

```bash
# Download checksums
curl -LO https://github.com/nikan/leo-releases/releases/latest/download/checksums.txt

# Verify the download (Linux example)
sha256sum -c checksums.txt --ignore-missing

# Or manually compare
sha256sum leo-linux-amd64
cat checksums.txt | grep leo-linux-amd64
```

### Verify on Windows

```powershell
# Download checksums.txt first, then:
CertUtil -hashfile leo-windows-amd64.exe SHA256
# Compare the output with the hash in checksums.txt
```

## 📦 Installation

### Linux

```bash
# Make executable
chmod +x leo-linux-amd64

# Move to system path (optional)
sudo mv leo-linux-amd64 /usr/local/bin/leo

# Verify installation
leo --version
```

### macOS

```bash
# Make executable
chmod +x leo-darwin-amd64  # or leo-darwin-arm64

# Remove quarantine attribute (macOS security)
xattr -d com.apple.quarantine leo-darwin-amd64

# Move to system path (optional)
sudo mv leo-darwin-amd64 /usr/local/bin/leo

# Verify installation
leo --version
```

### Windows

1. Download `leo-windows-amd64.exe`
2. Rename to `leo.exe` (optional)
3. Add the directory containing `leo.exe` to your PATH environment variable
4. Open a new command prompt and verify: `leo --version`

Alternatively, place `leo.exe` in a directory already in your PATH (e.g., `C:\Windows\System32`).

## 🚀 Quick Start

After installation, run:

```bash
leo help
```

For detailed usage and examples, see the [documentation](./docs/README.md).

## 📚 Documentation

- [Installation Guide](./docs/installation.md)
- [User Guide](./docs/README.md)
- [Security Policy](./SECURITY.md)
- [Changelog](./CHANGELOG.md)

## 🤝 Contributing

This repository contains release binaries only. For bug reports, feature requests, and contributions to the source code, please visit the main repository.

## 📄 License

Leo is distributed as freeware. See [LICENSE](./LICENSE) for details.

## 🔐 Security

For reporting security vulnerabilities, please see our [Security Policy](./SECURITY.md).
