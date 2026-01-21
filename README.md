# HTP-1 Controller

A sleek, mobile-friendly web interface for controlling the Monoprice Monolith HTP-1 home theater processor.

**Zero dependencies. Single HTML file. Works offline.**

## Features

- **Input Selection** - Quick switching between all configured inputs
- **Volume Control** - Adjust volume with ±1 and ±3 dB buttons, mute toggle
- **Loudness Control** - Toggle loudness on/off, adjust level (50-90), tap to edit directly
- **Upmixer Selection** - Switch between Native, Dolby Surround, DTS Neural:X, Auro-3D, and Stereo
- **Presets** - Save and recall up to 20 presets with custom volume, loudness, and level settings
- **Dark/Light Mode** - Toggle between themes with persistent preference
- **Customizable Layout** - Show/hide cards and drag to reorder in settings
- **Responsive Design** - Optimized for mobile, tablet, and desktop
- **PWA Support** - Add to home screen for app-like experience on mobile

## Installation

### Method 1: Direct Download (Recommended)

The simplest approach - just download and open:

1. Download [`htp1-controller.html`](htp1-controller.html)
2. Open the file in any modern browser
3. Tap the gear icon (⚙) to enter your HTP-1's IP address
4. Done!

Your device must be on the same network as the HTP-1.

### Method 2: Local Web Server

If you prefer accessing via URL (e.g., `http://localhost:8080`):

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/htp1_controller.git
cd htp1_controller

# Start a simple HTTP server (Python 3)
python3 -m http.server 8080

# Or with Node.js
npx serve .
```

Then open `http://localhost:8080/htp1-controller.html`

> **Note**: Must be served over HTTP, not HTTPS. The HTP-1 uses unencrypted WebSockets (`ws://`), which browsers block from HTTPS pages.

### Mobile Installation (Android)

1. Download `htp1-controller.html` to your phone (via USB, email, cloud storage, etc.)
2. Open the file in Chrome using a file manager
3. Tap the menu (⋮) → "Add to Home screen"
4. The app appears on your home screen and opens in full-screen mode

### Mobile Installation (iOS)

1. Download the file or access via local server method
2. Open in Safari
3. Tap Share → "Add to Home Screen"

## Configuration

Tap the gear icon (⚙) to access settings:

- **IP Address** - Your HTP-1's network address (find it in the HTP-1's network settings)
- **Card Layout** - Toggle visibility and drag to reorder the control cards

All settings are stored in your browser's localStorage and persist across sessions.

## Technical Details

- Single HTML file (~70KB) with embedded CSS and JavaScript
- Communicates via WebSocket at `ws://{ip}/ws/controller`
- Uses JSON Patch format for state changes
- No external dependencies, frameworks, or build process
- Works entirely offline once loaded

## License

MIT License - feel free to modify and share.
