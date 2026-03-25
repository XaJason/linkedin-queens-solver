> **Note:** This extension is no longer actively maintained. LinkedIn modified their
> DOM structure in early 2026, breaking board detection. The repository is archived
> for reference. The solver algorithm and extension architecture remain fully intact.

# LinkedIn Queens Solver

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Language](https://img.shields.io/badge/language-JavaScript-yellow.svg)
![Status](https://img.shields.io/badge/status-Complete-brightgreen.svg)
![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)
![Compatibility](https://img.shields.io/badge/compatibility-Universal-green.svg)

A Chrome extension that automatically solves the daily 'Queens' puzzle game on LinkedIn with **universal compatibility**. Works seamlessly for both **signed-in users** (direct DOM access) and **signed-out users** (iframe-based game loading). The extension uses an optimized backtracking algorithm to handle the game's unique constraints, including colored regions and queen adjacency rules, providing instant solutions with visual guidance directly on the LinkedIn game page.

## 🚀 Universal Compatibility

✅ **Signed-In Users** - Direct game board access and immediate solving  
✅ **Signed-Out Users** - Smart iframe detection and cross-frame puzzle solving  
✅ **All LinkedIn Game Modes** - Automatically adapts to different LinkedIn game presentations  
✅ **SPA Navigation** - Seamless operation across LinkedIn's single-page application routing

## Demo

![Demo Animation - Extension solving LinkedIn Queens puzzle in real-time](assets/demo.gif)
*Animated demonstration of the LinkedIn Queens Solver extension in action*

## 🤖 Tech Stack

- **JavaScript (ES6+)** - Core logic and algorithm implementation
- **Chrome Extension APIs (Manifest V3)** - Modern extension framework with enhanced security
- **HTML5** - Extension popup interface structure
- **CSS3** - Visual styling and highlighting effects
- **DOM Manipulation** - Real-time LinkedIn page interaction and solution visualization

## ✨ Features

- **Universal Compatibility** - Works for both signed-in and signed-out LinkedIn users with automatic context detection
- **Smart Iframe Support** - Seamlessly handles LinkedIn's iframe-based game loading for signed-out users
- **Automated Board Parsing** - Automatically detects and extracts LinkedIn Queens game state via sophisticated DOM analysis
- **Custom Backtracking Algorithm** - Implements optimized solving algorithm respecting LinkedIn's unique rules (color regions, adjacency constraints)
- **Dynamic Solution Visualization** - Injects subtle visual highlights and crown icons directly onto the live game board
- **Instant Performance** - Solves 9x9 puzzles in under 1ms with ~49 iterations using O(1) conflict checking
- **SPA Navigation Support** - Seamlessly works across LinkedIn's single-page application routing with context awareness
- **Intelligent Context Detection** - Automatically identifies execution environment (main page vs iframe) and adapts accordingly
- **User-Friendly Interface** - Clean browser action popup with solution status and performance metrics

## ⚙️ Installation and Usage

### 🏪 Method 1: Chrome Web Store (Recommended)
**[Install from Chrome Web Store →](https://chromewebstore.google.com/detail/linkedin-queens-solver/dgncekenlgnneibllkjinpcfccajpjmc)**

1. **Click the link above** to open the extension in Chrome Web Store
2. **Click "Add to Chrome"** to install instantly
3. **Visit LinkedIn Queens** - the extension will automatically solve puzzles!

### 📦 Method 2: Download Release
1. **Download the latest release** from [GitHub Releases](https://github.com/XaJason/linkedin-queens-solver/releases)
2. **Extract the ZIP file** to a local directory
3. **Open Google Chrome** and navigate to `chrome://extensions`
4. **Enable "Developer mode"** using the toggle in the top right corner
5. **Click "Load unpacked"** and select the extracted extension folder
6. **Visit LinkedIn Queens** - the extension will automatically solve puzzles!

### 🔧 Method 3: Clone Repository (Development)
1. **Clone the repository:**
   ```bash
   git clone https://github.com/XaJason/linkedin-queens-solver.git
   ```
2. **Open Google Chrome and navigate to `chrome://extensions`**
3. **Enable "Developer mode" using the toggle in the top right corner**
4. **Click the "Load unpacked" button**
5. **Select the `/extensions` directory from the cloned project folder**
6. **Navigate to a LinkedIn Queens puzzle page and the extension will automatically solve the puzzle, displaying solutions in the console and highlighting positions on the board**

### 🎯 Usage
- **Automatic Operation**: Simply visit any LinkedIn Queens puzzle page
- **Universal Compatibility**: Works whether you're signed in or signed out of LinkedIn  
- **Visual Guidance**: Solutions appear with golden highlights and crown icons
- **Console Output**: Detailed solving information available in browser developer tools

## 🏛️ Architectural Overview

The extension follows Chrome's Manifest V3 architecture with three core components working in harmony to provide **universal LinkedIn compatibility**. 

### Core Components:

- **Content Script** (`content.js`) - Features **intelligent context detection**, automatically identifying whether the game runs in direct DOM (signed-in users) or iframe mode (signed-out users). Handles DOM parsing, visual feedback, and cross-frame communication with sophisticated iframe detection algorithms.

- **Background Script** (`background.js`) - Serves as the computational engine, implementing the optimized backtracking algorithm with auxiliary data structures for O(1) conflict checking. Processes puzzle data regardless of source context (main page or iframe).

- **Popup Script** (`popup.js`) - Provides user interface controls and status information with context-aware feedback.

Communication flows through Chrome's secure message passing protocol, with the content script intelligently adapting to either context while maintaining full functionality and respecting LinkedIn's security boundaries.

### 🗂️ Repository Structure
```
linkedin-queens-solver/
├── extensions/              # Chrome extension source code
│   ├── manifest.json       # Extension configuration
│   ├── background.js       # Puzzle solving algorithm  
│   ├── content.js          # DOM interaction & UI
│   └── icons/             # Extension icons (16px, 48px, 128px)
├── docs/                   # Documentation
│   ├── CHANGELOG.md       # Release history
│   ├── PRIVACY.md         # Privacy policy
│   ├── RELEASE_NOTES.md   # Latest release notes
│   └── RELEASE_SUMMARY.md # Internal release documentation
├── scripts/               # Build and utility scripts
│   └── package.ps1       # Release packaging script
├── assets/               # Images and media assets
│   └── demo.gif         # Demo animation
├── .github/             # GitHub configuration
│   └── workflows/       # GitHub Actions
├── CONTRIBUTING.md      # Contribution guidelines
├── SECURITY.md         # Security policy
└── README.md           # This file
```

## 🔐 Privacy & Permissions

**Privacy-First Engineering:** This extension demonstrates professional development practices with minimal permission requirements and zero data collection.

- **Host Permission Only:** Uses exclusively `*://www.linkedin.com/games/*` for targeted puzzle access
- **No User Data Collection:** Operates entirely client-side with local processing
- **Minimal Attack Surface:** Leverages content script architecture over programmatic injection
- **Regulatory Compliance:** Adheres to Chrome Web Store Developer Program Policies

**Technical Implementation:** Utilizes declarative content script injection rather than dynamic scripting permissions, demonstrating understanding of modern browser security models and Chrome extension best practices.

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details on:
- Setting up the development environment
- Coding standards and best practices  
- Pull request process
- Testing requirements

## 🛡️ Security

Security is important to us. Please review our [Security Policy](SECURITY.md) for:
- Supported versions
- Vulnerability reporting process
- Security considerations

## 📋 Changelog

See [CHANGELOG.md](docs/CHANGELOG.md) for detailed release history and changes.

## 📜 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.
