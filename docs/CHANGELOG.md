# Changelog

All notable changes to the LinkedIn Queens Solver extension will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

**🏪 Available on Chrome Web Store**: [Install Here](https://chromewebstore.google.com/detail/linkedin-queens-solver/dgncekenlgnneibllkjinpcfccajpjmc)

## [1.1.0] - 2025-08-28

### 🚀 Major Features Added
- **Universal LinkedIn Compatibility** - Extension now works for both signed-in and signed-out users
- **Smart Iframe Support** - Automatic detection and handling of LinkedIn's iframe-based game loading for signed-out users
- **Intelligent Context Detection** - Automatically identifies execution environment (main page vs iframe) and adapts accordingly
- **Cross-Frame Communication** - Enhanced message passing system with context awareness

### ✨ Enhancements
- Added dual URL matching in manifest for both main page and iframe contexts
- Implemented `detectContext()` function for runtime environment detection
- Enhanced navigation handling with iframe-aware URL detection
- Added context information to puzzle data for improved debugging
- Improved console logging with context indicators

### 🔧 Technical Improvements
- Updated manifest.json to include iframe URL pattern (`*://www.linkedin.com/games/view/queens/desktop*`)
- Enhanced content script with `handleMainPageWithIframe()` and `processPuzzleInIframe()` functions
- Added robust iframe loading detection with timeout handling
- Improved SPA navigation detection for both main and iframe contexts

### 📚 Documentation
- Updated README.md with universal compatibility information
- Added architectural overview explaining iframe handling
- Enhanced feature descriptions with context detection capabilities
- Added compatibility badges and status indicators

## [1.0.0] - 2025-08-27

### 🎉 Initial Release
- **Automated LinkedIn Queens Solving** - Complete backtracking algorithm implementation
- **Real-time Board Parsing** - Sophisticated DOM analysis and game state extraction  
- **Visual Solution Display** - Subtle highlighting and crown icon placement on game board
- **Dynamic Grid Support** - Support for unlimited grid sizes with dynamic color mapping
- **Performance Optimization** - O(1) conflict checking with auxiliary data structures
- **SPA Navigation** - Single-page application routing support for LinkedIn Games
- **Chrome Manifest V3** - Modern extension architecture with enhanced security

### 🏗️ Core Components
- Background script with optimized N-Queens solver algorithm
- Content script with DOM parsing and visual feedback
- Popup interface for user interaction and status display
- Comprehensive error handling and timeout management

### 📋 Game Rules Implementation
- Each row must contain exactly one queen
- Each column must contain exactly one queen  
- Each color region must contain exactly one queen
- Queens cannot touch each other (including diagonally)

### 🛡️ Security & Privacy
- No data collection or external network requests
- Local-only processing with no user data transmission
- MIT License with comprehensive privacy policy
