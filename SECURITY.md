# Security Policy

## Supported Versions

We provide security updates for the following versions:

| Version | Supported          |
| ------- | ------------------ |
| 1.1.x   | :white_check_mark: |
| 1.0.x   | :x:                |

## Reporting a Vulnerability

The LinkedIn Queens Solver team takes security seriously. If you discover a security vulnerability, please follow these steps:

### 🔒 Private Reporting
1. **DO NOT** create a public GitHub issue for security vulnerabilities
2. Email security concerns to the repository owner via GitHub's private vulnerability reporting feature
3. Or create a private security advisory through GitHub's interface

### 📝 Information to Include
When reporting a security vulnerability, please include:
- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact assessment
- Any suggested fixes (if you have them)
- Your contact information for follow-up

### ⏱️ Response Timeline
- **Initial Response**: Within 48 hours
- **Status Update**: Within 1 week
- **Resolution**: Varies by complexity, but we aim for timely fixes

### 🛡️ Security Considerations

#### Extension Security
- All data processing occurs locally in the browser
- No external network requests are made
- No user data is collected or transmitted
- Chrome's security model provides sandboxing

#### Potential Security Areas
While the extension is designed with security in mind, potential areas of concern include:
- DOM manipulation and injection
- Chrome extension permissions
- Cross-frame communication (iframe scenarios)
- Message passing between extension components

#### Safe Usage
The extension is designed to:
- Only operate on LinkedIn Queens pages
- Use minimal required permissions
- Process data locally without external transmission
- Follow Chrome extension security best practices

**Official Distribution**: The extension is officially distributed through the [Chrome Web Store](https://chromewebstore.google.com/detail/linkedin-queens-solver/dgncekenlgnneibllkjinpcfccajpjmc) for verified security and automatic updates.

### 🏆 Recognition
Contributors who responsibly disclose security vulnerabilities will be:
- Credited in the fix release notes (unless they prefer anonymity)
- Listed in a security contributors section
- Given priority support for future security reports

### 📋 Security Best Practices

If you're contributing to the project, please follow these security guidelines:
- Validate all DOM interactions
- Use secure coding practices
- Avoid eval() or similar dynamic code execution
- Follow Chrome extension security guidelines
- Test across different LinkedIn contexts (signed-in/signed-out)

---

Thank you for helping keep LinkedIn Queens Solver secure! 🛡️
