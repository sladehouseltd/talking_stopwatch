# Yoga Timer - Talking Stopwatch

A Progressive Web App (PWA) that announces elapsed time at configurable intervals during your yoga practice.

## Features

- **Voice Announcements**: Automatically speaks elapsed time every 15, 30, 45, or 60 seconds
- **Simple Controls**: Large start/pause and reset buttons
- **Wake Lock**: Keeps screen on during practice
- **Offline Support**: Works without internet connection once installed
- **Installable**: Can be installed on phone, tablet, or desktop
- **Responsive Design**: Works on all device sizes

## Quick Start

1. **Serve the app locally**:
   ```bash
   # Using Python 3
   python3 -m http.server 8000

   # Or using Node.js http-server
   npx http-server -p 8000
   ```

2. **Open in browser**: Navigate to `http://localhost:8000`

3. **Install the PWA** (optional but recommended):
   - On Chrome/Edge: Click the install button in the address bar
   - On iOS Safari: Tap Share → Add to Home Screen
   - On Android: Tap the menu → Install app

## Generating Icon Files

The app needs PNG icons for full PWA support. You can generate them from the included `icon.svg`:

### Option 1: Using an online converter
1. Visit https://svgtopng.com/ or similar
2. Upload `icon.svg`
3. Generate 192x192 and 512x512 PNG files
4. Save as `icon-192.png` and `icon-512.png`

### Option 2: Using ImageMagick
```bash
convert -background none -resize 192x192 icon.svg icon-192.png
convert -background none -resize 512x512 icon.svg icon-512.png
```

### Option 3: Using Inkscape
```bash
inkscape icon.svg --export-filename=icon-192.png -w 192 -h 192
inkscape icon.svg --export-filename=icon-512.png -w 512 -h 512
```

## Usage

1. **Select your announcement interval** (15s, 30s, 45s, or 60s)
2. **Tap Start** to begin the timer
3. The app will speak the elapsed time at your chosen interval
4. **Tap Pause** to pause (timer keeps the elapsed time)
5. **Tap Reset** to start over

## Tips for Yoga Practice

- **Install the app** for quick access without opening a browser
- **Enable Do Not Disturb** on your device to avoid interruptions
- **Place your device nearby** but where you can hear it clearly
- The app will **keep your screen on** during practice
- Adjust your device volume before starting

## Technical Details

- **No dependencies**: Pure HTML, CSS, and JavaScript
- **Web Speech API**: For voice announcements
- **Wake Lock API**: Prevents screen sleep
- **Service Worker**: Enables offline functionality
- **localStorage**: Saves your interval preference

## Browser Support

Works best in:
- Chrome/Edge (desktop & mobile)
- Safari (iOS & macOS)
- Firefox (desktop & mobile)

Note: Some older browsers may not support all features (wake lock, installation), but the core timer functionality will still work.

## Deployment

To deploy to a production server:

1. Generate the PNG icons (see above)
2. Upload all files to your web server
3. Ensure HTTPS is enabled (required for PWA features)
4. Update the `start_url` in `manifest.json` if not serving from root

### Deploy to GitHub Pages

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main

# Enable GitHub Pages in repository settings
```

Then visit: `https://yourusername.github.io/talking_stopwatch`

## License

Free to use for personal practice. Namaste!
