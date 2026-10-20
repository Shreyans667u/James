# James – voice assistant PWA

Open-source voice assistant for Android (Chrome). Pure static files: no build step, no server.

## Host on GitHub Pages
1. Create a new GitHub repo (e.g. `james`), upload everything in this folder (keep `icons/`).
2. Settings > Pages > Source: "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
3. After a minute your app is at `https://<username>.github.io/james/`.

## Install on your phone
1. Open that URL in Chrome on Android.
2. Chrome menu (three dots) > Add to Home screen > Install.
3. Open James, expand Settings, paste your Anthropic API key (console.anthropic.com), set a spending limit there, optionally set a voice PIN, add contacts and devices, press Save.
4. Tap the brass button, allow the microphone, and speak.

## Notes
- Your key and data live only in this phone's browser storage. Never commit a key to the repo.
- Wake-word mode ("James") keeps listening while the app is open and the screen is on; Chrome cannot listen in the background.
- Calls, texts and emails open the phone's own apps with the draft filled in; you press send. Timers only fire while James is open. Alarms open the clock app.
- ESP devices: an https page cannot call plain `http://` addresses. Use an https tunnel (Cloudflare Tunnel, ngrok) or use the Tasker/native route for local-only gear. MQTT needs a `wss://` broker.
- Features needing deep Android access (flashlight, Wi-Fi toggles, reading texts, call screening) are not possible from a web app; they need a native app or Tasker.
