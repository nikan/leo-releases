# Security Policy

## Supported Versions

We take the security of the Leo VSCode extension seriously. The following versions are currently supported with security updates:

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| < Latest| :x:                |

We recommend always using the latest version of the Leo extension to ensure you have the latest security patches.

## Reporting a Vulnerability

If you discover a security vulnerability in Leo, please report it responsibly. We appreciate your efforts to disclose the issue in a coordinated manner.

### How to Report

**Please DO NOT report security vulnerabilities through public GitHub issues.**

Instead, please report security vulnerabilities using one of the following methods:

#### Option 1: GitHub Security Advisories (Preferred)

1. Go to the [Security Advisories](https://github.com/nikan/leo-releases/security/advisories) page
2. Click "Report a vulnerability"
3. Fill out the form with details about the vulnerability

#### Option 2: Direct Contact

If GitHub Security Advisories are not available, you can open a private discussion or create an issue marked as security-related.

When reporting, include the following information:
- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact of the vulnerability
- Any suggested fixes (if available)

### What to Expect

When you report a vulnerability, you can expect:

1. **Acknowledgment**: We will acknowledge receipt of your vulnerability report within 48 hours.

2. **Assessment**: We will investigate and assess the reported vulnerability within 7 days.

3. **Updates**: We will keep you informed about our progress in addressing the vulnerability.

4. **Resolution**: Once the vulnerability is fixed:
   - We will release a security update
   - We will publicly disclose the vulnerability (after users have had time to update)
   - We will credit you for the discovery (unless you prefer to remain anonymous)

### Security Update Process

When a security vulnerability is confirmed:

1. A fix will be developed and tested
2. A security advisory will be published
3. A new version will be released with the fix
4. Users will be notified through:
   - GitHub Security Advisories
   - Release notes
   - Changelog updates

## Security Best Practices

When using the Leo VSCode extension, we recommend:

1. **Keep Updated**: Always use the latest version of the extension
2. **Verify Downloads**: When installing from VSIX files, always verify checksums
3. **Secure Systems**: Use Leo on systems with up-to-date security patches
4. **Review Permissions**: Be aware of the permissions the extension requires in VSCode
5. **Report Issues**: Report any suspicious behavior immediately

## Known Security Considerations

### Extension Verification

When manually installing from VSIX files, always verify the integrity of downloaded packages using the provided SHA256 checksums. See the [README](./README.md) for verification instructions.

### Update Notifications

We recommend keeping auto-updates enabled in VSCode, or regularly checking for updates:

- In VSCode, go to Extensions view and look for updates
- Visit the [releases page](https://github.com/nikan/leo-releases/releases/latest) for the latest version

### Build Source

**Important**: The Leo extension is built in a private repository. Release artifacts in this public repository are the official, trusted distribution method. Only install the extension from:
- The official VSCode Marketplace
- Official releases from this GitHub repository (`.vsix` files)

## Scope

This security policy applies to:

- Official Leo VSCode extension releases distributed through this repository
- The extension packages (`.vsix` files) and associated documentation

For issues related to the Leo source code or development (which occurs in a private repository), security reports should still be submitted through this repository's security reporting mechanism.

## Contact

For general security questions or concerns (not vulnerability reports), you can:

- Open a discussion in the GitHub Discussions section
- Contact the maintainers through GitHub

Thank you for helping keep Leo and its users safe!
