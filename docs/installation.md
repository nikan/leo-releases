# Installation Guide for Leo VSCode Extension

This guide provides detailed installation instructions for the Leo AI Workflow Assistant extension for Visual Studio Code.

## Prerequisites

### System Requirements

- **Visual Studio Code**: Version 1.60.0 or higher
- **Operating System**: Windows 10+, macOS 10.14+, or Linux (kernel 3.10+)
- **Architecture**: 64-bit (x86_64 or ARM64)
- **RAM**: 256 MB minimum (512 MB recommended)
- **Disk Space**: 50 MB for the extension

## Installation Methods

### Method 1: VSCode Marketplace (Recommended)

This is the easiest and recommended method for most users.

1. **Open Visual Studio Code**

2. **Open Extensions View**:
   - Click the Extensions icon in the Activity Bar (left sidebar)
   - Or press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (macOS)

3. **Search for Leo**:
   - Type "Leo AI Workflow Assistant" in the search box
   - Look for the official Leo extension

4. **Install**:
   - Click the "Install" button
   - Wait for installation to complete

5. **Verify Installation**:
   - The extension should appear in your installed extensions list
   - You should see Leo commands when opening the Command Palette

### Method 2: Manual Installation from VSIX File

Use this method if you want to install a specific version or if the Marketplace is unavailable.

#### Download the VSIX File

1. **Visit the Releases Page**:
   - Go to [https://github.com/nikan/leo-releases/releases](https://github.com/nikan/leo-releases/releases)
   - Find the latest release or the specific version you want

2. **Download the VSIX**:
   - Download the `.vsix` file (e.g., `leo-vscode-1.0.0.vsix`)

3. **Download Checksums** (optional but recommended):
   - Download `checksums.txt` from the same release

#### Verify the Download (Optional but Recommended)

**On Linux/macOS**:
```bash
# Verify the download
sha256sum leo-vscode-1.0.0.vsix
cat checksums.txt | grep leo-vscode
# Compare the two hashes - they should match
```

**On Windows (PowerShell)**:
```powershell
# Compute hash
CertUtil -hashfile leo-vscode-1.0.0.vsix SHA256

# Compare with checksums.txt
Get-Content checksums.txt | Select-String "leo-vscode"
```

#### Install the VSIX File

**Option A: Using VSCode UI**
1. Open Visual Studio Code
2. Open Extensions view (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Click the "..." (Views and More Actions) menu at the top of the Extensions view
4. Select "Install from VSIX..."
5. Navigate to and select the downloaded `.vsix` file
6. Wait for installation to complete
7. Reload VSCode if prompted

**Option B: Using Command Line**
```bash
# Navigate to the directory containing the .vsix file
cd ~/Downloads

# Install the extension
code --install-extension leo-vscode-1.0.0.vsix

# Verify installation
code --list-extensions | grep -i leo
```

**On Windows (Command Prompt)**:
```cmd
cd %USERPROFILE%\Downloads
code --install-extension leo-vscode-1.0.0.vsix
code --list-extensions | findstr /i leo
```

## Post-Installation

### First Run

After installation:

1. **Open Command Palette**: `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS)
2. **Look for Leo Commands**: Type "Leo" to see available commands
3. **Configure if needed**: Go to Settings → Extensions → Leo

### Configuration

You can configure Leo through VSCode Settings:

1. Open Settings: `File → Preferences → Settings` or `Ctrl+,` / `Cmd+,`
2. Search for "Leo"
3. Adjust settings as needed

Configuration may be stored in:
- VSCode user settings: `settings.json`
- Workspace settings (if configured per workspace)

### Verifying Installation

To verify Leo is installed correctly:

1. Open Extensions view (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Search for "Leo" in installed extensions
3. Check that the extension is enabled
4. Open Command Palette and search for Leo commands

## Updating the Extension

### Automatic Updates (Marketplace Installation)

If you installed from the VSCode Marketplace:
- VSCode will automatically check for updates
- You'll see an update notification when a new version is available
- Click "Update" to install the latest version

### Manual Updates (VSIX Installation)

If you installed from a VSIX file:
1. Download the latest `.vsix` from the [releases page](https://github.com/nikan/leo-releases/releases)
2. Follow the manual installation steps above
3. The new version will replace the old one

## Uninstallation

### Using VSCode UI

1. Open Extensions view (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Find "Leo" in your installed extensions
3. Click the gear icon next to the extension
4. Select "Uninstall"
5. Reload VSCode if prompted

### Using Command Line

```bash
code --uninstall-extension <extension-id>
```

Replace `<extension-id>` with Leo's extension identifier (found in the Extensions view).

### Removing Configuration (Optional)

To completely remove Leo configuration:

**Linux/macOS**:
```bash
# Remove VSCode extension data
rm -rf ~/.vscode/extensions/*leo*/
rm -rf ~/.config/Code/User/globalStorage/*leo*/
```

**Windows (PowerShell)**:
```powershell
# Remove VSCode extension data
Remove-Item -Recurse -Force "$env:USERPROFILE\.vscode\extensions\*leo*"
Remove-Item -Recurse -Force "$env:APPDATA\Code\User\globalStorage\*leo*"
```

## Troubleshooting

### Extension Not Showing in Marketplace

If you can't find Leo in the VSCode Marketplace:
- Check your internet connection
- Try reloading VSCode
- Install manually from a `.vsix` file

### Installation from VSIX Fails

If VSIX installation fails:
1. Check that the `.vsix` file is not corrupted (verify checksums)
2. Ensure you have the latest version of VSCode
3. Try closing and reopening VSCode
4. Check VSCode logs: `Help → Toggle Developer Tools → Console`

### Extension Not Loading

If the extension installs but doesn't load:
1. Check that the extension is enabled in Extensions view
2. Look for error messages in: `Help → Toggle Developer Tools → Console`
3. Try disabling other extensions to check for conflicts
4. Reinstall the extension

### Command Not Found

If Leo commands don't appear in Command Palette:
1. Verify the extension is installed and enabled
2. Reload VSCode: `Developer: Reload Window` from Command Palette
3. Check for error messages in the Output panel (`View → Output`)

### Compatibility Issues

If you experience compatibility issues:
- Check the [releases page](https://github.com/nikan/leo-releases/releases) for version requirements
- Ensure your VSCode version meets the minimum requirements
- Check for known issues in the release notes

## Platform-Specific Notes

### Windows

- No special configuration required
- Windows Defender may scan the extension on first install (this is normal)

### macOS

- No special configuration required
- Gatekeeper security should not affect VSCode extensions

### Linux

- No special configuration required
- Ensure VSCode has necessary permissions

## Getting Help

If you encounter issues:

1. Check this installation guide
2. Review the [FAQ](./README.md#frequently-asked-questions)
3. Search existing [GitHub Issues](https://github.com/nikan/leo-releases/issues)
4. Create a new issue with:
   - Your VSCode version (`Help → About`)
   - Your operating system and version
   - Leo extension version (if installed)
   - Complete error message or description
   - Steps to reproduce

## Next Steps

After successful installation:

- Read the [User Guide](./README.md#user-guide)
- Explore Leo commands in the Command Palette
- Configure Leo settings to match your preferences
- Check the [documentation](./README.md) for usage examples
