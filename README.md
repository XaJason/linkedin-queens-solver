# LinkedIn Queens Solver

> **Note:** This extension is no longer actively maintained. LinkedIn modified their
> DOM structure in early 2026, breaking board detection. The repository is archived
> for reference. The solver algorithm and extension architecture remain fully intact.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Language](https://img.shields.io/badge/language-JavaScript-yellow.svg)
![Status](https://img.shields.io/badge/status-Archived-lightgrey.svg)
![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)

A Chrome extension that automatically solves LinkedIn's daily Queens puzzle. It works for both signed-in users (direct DOM access) and signed-out users (iframe-based loading), using an optimized backtracking algorithm with O(1) conflict checking to deliver solutions in under 1ms.

## Demo

![Demo Animation showing the extension solving a LinkedIn Queens puzzle in real time](assets/demo.gif)

## Features

- **Universal compatibility:** Automatically detects whether the game runs in the main page or an iframe and adapts accordingly, supporting both signed-in and signed-out LinkedIn users
- **Optimized solver:** Backtracking algorithm with auxiliary data structures for O(1) conflict checking, solving 9x9 boards in under 1ms with roughly 49 iterations
- **DOM parsing:** Extracts board state by analyzing LinkedIn's live DOM, including color region boundaries and cell layout
- **Solution visualization:** Injects subtle highlights and crown icons directly onto the game board without disrupting the page
- **SPA support:** Handles LinkedIn's single-page application routing so the extension stays functional across navigation
- **Minimal permissions:** Scoped exclusively to `*://www.linkedin.com/games/*` with no data collection

## Tech Stack

- JavaScript (ES6+), HTML5, CSS3
- Chrome Extension APIs, Manifest V3
- DOM Manipulation

## Architecture

The extension is built around three components communicating through Chrome's secure message passing protocol.

- `content.js`: Detects execution context (main page or iframe), parses the board, handles cross-frame communication, and renders the solution overlay
- `background.js`: Runs the backtracking solver, isolated from the page for security and performance
- `popup.js`: Displays solve status and performance metrics to the user

This separation keeps the solving logic independent from the DOM layer, making each component easier to test and maintain.

### Repository Structure

```
linkedin-queens-solver/
├── extensions/
│   ├── manifest.json
│   ├── background.js
│   ├── content.js
│   └── icons/
├── docs/
│   ├── CHANGELOG.md
│   ├── PRIVACY.md
│   ├── RELEASE_NOTES.md
│   └── RELEASE_SUMMARY.md
├── scripts/
│   └── package.ps1
├── assets/
│   └── demo.gif
├── .github/
│   └── workflows/
├── CONTRIBUTING.md
├── SECURITY.md
└── README.md
```

## Installation

### Manual Install (Developer Mode)

1. Download the latest release from [GitHub Releases](https://github.com/XaJason/linkedin-queens-solver/releases) and extract the ZIP
2. Go to `chrome://extensions` and enable Developer Mode
3. Click "Load unpacked" and select the extracted folder

### Clone and Run Locally

```bash
git clone https://github.com/XaJason/linkedin-queens-solver.git
```

Then follow the manual install steps above, pointing "Load unpacked" at the `/extensions` directory.

## Privacy

The extension operates entirely client-side. It collects no user data, sends no requests to external servers, and uses declarative content script injection rather than dynamic scripting permissions, reducing the attack surface while adhering to Chrome Web Store developer policies.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for setup instructions, coding standards, and the pull request process.

## Security

See [SECURITY.md](SECURITY.md) for supported versions and the vulnerability reporting process.

## Changelog

See [CHANGELOG.md](docs/CHANGELOG.md) for release history.

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.
