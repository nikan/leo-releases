# Installation Guide

This guide provides detailed installation instructions for Leo on all supported platforms.

## System Requirements

### Minimum Requirements

- **Operating System**: Windows 10+, macOS 10.14+, or Linux (kernel 3.10+)
- **Architecture**: 64-bit (x86_64 or ARM64)
- **RAM**: 256 MB minimum
- **Disk Space**: 50 MB for the executable

### Recommended

- **RAM**: 512 MB or more
- **Disk Space**: 100 MB or more (for executable and data)

## Installation Methods

### Method 1: Manual Installation (Recommended)

This is the recommended method for most users.

#### Linux

1. **Download the binary**:
   ```bash
   curl -LO https://github.com/nikan/leo-releases/releases/latest/download/leo-linux-amd64
   ```

2. **Download checksums** (optional but recommended):
   ```bash
   curl -LO https://github.com/nikan/leo-releases/releases/latest/download/checksums.txt
   ```

3. **Verify the download**:
   ```bash
   sha256sum leo-linux-amd64
   cat checksums.txt | grep leo-linux-amd64
   # Compare the two hashes - they should match
   ```

4. **Make executable**:
   ```bash
   chmod +x leo-linux-amd64
   ```

5. **Install to system path** (optional):
   ```bash
   sudo mv leo-linux-amd64 /usr/local/bin/leo
   ```

6. **Verify installation**:
   ```bash
   leo --version
   ```

#### macOS

1. **Download the binary**:
   ```bash
   # For Intel Macs
   curl -LO https://github.com/nikan/leo-releases/releases/latest/download/leo-darwin-amd64
   
   # For Apple Silicon (M1/M2/M3)
   curl -LO https://github.com/nikan/leo-releases/releases/latest/download/leo-darwin-arm64
   ```

2. **Download checksums** (optional but recommended):
   ```bash
   curl -LO https://github.com/nikan/leo-releases/releases/latest/download/checksums.txt
   ```

3. **Verify the download**:
   ```bash
   # For Intel
   shasum -a 256 leo-darwin-amd64
   
   # For Apple Silicon
   shasum -a 256 leo-darwin-arm64
   
   # Compare with checksums.txt
   cat checksums.txt | grep leo-darwin
   ```

4. **Remove quarantine attribute**:
   ```bash
   # For Intel
   xattr -d com.apple.quarantine leo-darwin-amd64
   
   # For Apple Silicon
   xattr -d com.apple.quarantine leo-darwin-arm64
   ```

5. **Make executable**:
   ```bash
   # For Intel
   chmod +x leo-darwin-amd64
   
   # For Apple Silicon
   chmod +x leo-darwin-arm64
   ```

6. **Install to system path** (optional):
   ```bash
   # For Intel
   sudo mv leo-darwin-amd64 /usr/local/bin/leo
   
   # For Apple Silicon
   sudo mv leo-darwin-arm64 /usr/local/bin/leo
   ```

7. **Verify installation**:
   ```bash
   leo --version
   ```

#### Windows

1. **Download the binary**:
   - Visit the [releases page](https://github.com/nikan/leo-releases/releases/latest)
   - Download `leo-windows-amd64.exe`
   - Or use PowerShell:
     ```powershell
     Invoke-WebRequest -Uri "https://github.com/nikan/leo-releases/releases/latest/download/leo-windows-amd64.exe" -OutFile "leo.exe"
     ```

2. **Download and verify checksums** (optional but recommended):
   ```powershell
   # Download checksums
   Invoke-WebRequest -Uri "https://github.com/nikan/leo-releases/releases/latest/download/checksums.txt" -OutFile "checksums.txt"
   
   # Compute hash
   CertUtil -hashfile leo.exe SHA256
   
   # Compare with checksums.txt
   Get-Content checksums.txt | Select-String "leo-windows"
   ```

3. **Choose installation location**:

   **Option A: User directory** (no admin required)
   - Create a directory: `mkdir C:\Users\%USERNAME%\leo` (uses your current username automatically)
   - Move `leo.exe` to this directory
   - Add to PATH: Search for "Environment Variables" → Edit user PATH → Add `C:\Users\%USERNAME%\leo`

   **Option B: System directory** (requires admin)
   - Move `leo.exe` to `C:\Windows\System32` or `C:\Program Files\leo`
   - If using `C:\Program Files\leo`, add it to system PATH

4. **Verify installation**:
   ```cmd
   leo --version
   ```

### Method 2: Using Package Managers (Coming Soon)

Support for package managers is planned for future releases:

- **Homebrew** (macOS/Linux): `brew install leo`
- **Chocolatey** (Windows): `choco install leo`
- **apt** (Debian/Ubuntu): `apt install leo`
- **yum/dnf** (RHEL/CentOS/Fedora): `yum install leo`

## Post-Installation

### First Run

After installation, run Leo for the first time:

```bash
leo --version
leo help
```

### Configuration

Leo may create configuration files in your home directory. Check:

- Linux/macOS: `~/.leo/` or `~/.config/leo/`
- Windows: `%APPDATA%\leo\` or `%USERPROFILE%\.leo\`

### Uninstallation

To remove Leo:

1. Delete the binary from where you installed it:
   ```bash
   # Linux/macOS
   sudo rm /usr/local/bin/leo
   
   # Windows
   # Delete leo.exe from its installation directory
   ```

2. Remove configuration files (optional):
   ```bash
   # Linux/macOS
   rm -rf ~/.leo ~/.config/leo
   
   # Windows (PowerShell)
   Remove-Item -Recurse -Force $env:APPDATA\leo
   ```

## Troubleshooting

### Linux/macOS: Permission Denied

If you get "Permission denied" when running Leo:
```bash
chmod +x leo-linux-amd64  # or leo-darwin-amd64/leo-darwin-arm64
```

### macOS: "Cannot be opened because it is from an unidentified developer"

Remove the quarantine attribute:
```bash
xattr -d com.apple.quarantine leo-darwin-amd64
```

Or go to System Preferences → Security & Privacy → General, and click "Open Anyway".

### Windows: "Windows protected your PC"

Click "More info" and then "Run anyway". This is expected for new executables.

### Command Not Found

If `leo` is not found after installation:

1. Check that the binary is in your PATH
2. Try using the full path to the binary
3. Restart your terminal/command prompt
4. On Linux/macOS, check with: `which leo`
5. On Windows, check with: `where leo`

### Verification Failed

If checksum verification fails:

1. Re-download the binary (the download may have been corrupted)
2. Ensure you're comparing the correct file against the correct checksum
3. Report the issue if the problem persists

## Updating Leo

To update Leo:

1. Download the latest version using the installation instructions above
2. Replace the old binary with the new one
3. Verify the new version: `leo --version`

## Getting Help

If you encounter issues:

1. Check this installation guide
2. Review the [FAQ](./README.md#frequently-asked-questions)
3. Search existing GitHub Issues
4. Create a new issue with:
   - Your operating system and version
   - Leo version (if installed)
   - Complete error message
   - Steps to reproduce

## Next Steps

After successful installation:

- Read the [User Guide](./README.md#user-guide)
- Run `leo help` to see available commands
- Check the [documentation](./README.md) for usage examples
