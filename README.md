# What The Fuck - Status Generator

A fun, interactive web application that lets you generate a shareable status card with customizable checkboxes and free-form text. Perfect for expressing frustration in style.

## Features

- **Interactive Checkbox Grid**: Select from predefined options or add custom text
- **Share Links**: Generate compact shareable URLs with encoded state that can be shared with colleagues
- **Mobile Responsive**: Works seamlessly on phones, tablets, and desktops
- **Responsive Grid**: On mobile, the layout intelligently reflows to maintain proper grouping

## Functionality

### Button Actions
- **Reset**: Clears all selections (with confirmation)
- **Email to Boss**: Shows a comprehensive reality check message
- **Share**: Generates a compact shareable link and copies it to clipboard

### Share Links
Share compact encoded URLs with colleagues and friends

## Setup & Running

### Option 1: Python HTTP Server (Recommended)

1. Navigate to the project directory:
```bash
cd /path/to/fuck
```

2. Start the Python HTTP server:
```bash
python3 -m http.server 8000
```

3. Find your local IP address:
```bash
ifconfig | grep "inet " | grep -v 127.0.0.1 | head -1 | awk '{print $2}'
```

4. Open in your browser:
```
http://YOUR_IP:8000
```

The server will be running at `http://localhost:8000` on your machine and accessible from other devices on your network at `http://YOUR_IP:8000`.

### Option 2: VS Code Live Server Extension

1. Install the **Live Server** extension in VS Code
   - Open Extensions (`Cmd+Shift+X`)
   - Search for "Live Server"
   - Click Install

2. Right-click on `index.html` and select **"Open with Live Server"**

3. The page will automatically open in your browser and refresh when you make changes

### Option 3: Direct File Access

Simply open `index.html` directly in your browser:
```bash
open index.html
```

Note: Some features (like the download button) may work better when served through a web server.

## File Structure

```
/path/to/fuck/
├── index.html          # Main application file
└── README.md          # This file
```

## Browser Compatibility

- Chrome/Chromium (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

Mobile browsers supported:
- iOS Safari
- Chrome for Android
- Firefox for Android

## Technical Details

### Encoding Strategy
- **State**: Binary representation of checkbox states
  - Example: `101010` (11 checkboxes, alternating checked/unchecked)
  - Converted to hex for URL shortness: `2a`
- **Text**: Base64 encoding of URL-encoded custom text
  - Example: "hello" → `aGVsbG8=`

### URL Format
Share URLs are structured as: `#hexstate|base64text`
- `hexstate`: Hex-encoded checkbox states
- `base64text`: (Optional) Base64-encoded custom text

## Troubleshooting

### Share Link Not Working
- Clear your browser cache
- Make sure the URL hash is properly formatted
- Check browser console for errors

### Mobile Issues
- Try a different browser
- Ensure JavaScript is enabled
- Check that cookies/local storage isn't blocking state restoration

## Tips

- **Short URLs**: The hex encoding keeps share links compact
- **Privacy**: Custom text is Base64 encoded, not plaintext
- **Mobile-Friendly**: The grid reflows on small screens while keeping related items together

---

Made with ❌ and frustration.
