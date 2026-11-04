# Mandarin Anatomy Trainer (好 prototype)

One-card mobile-first Mandarin learning prototype for Samsung Z Fold and other modern browsers.

- Two-sided study card: pinyin, definition, optional etymology explanation
- Full 好 = 女 + 子 breakdown, pinyin and built-in Mandarin text-to-speech
- Voice recording/playback using browser microphone access (HTTPS is required)
- Optional Web Speech recognition (availability depends on browser/network)
- Approximate partial-credit grading with a 50% multiplier per pre-grading peek
- LocalStorage progress history, JSON export, offline cache (after first online load)

## Publish on GitHub Pages

In the repository: **Settings → Pages → Build and deployment: Deploy from a branch → branch `master`, folder `/docs` → Save**.

Open the HTTPS GitHub Pages URL in **Samsung Internet** or **Chrome**, not the embedded ChatGPT card.

The app is statically hosted; recordings are kept locally. Browser speech recognition may invoke a service operated by the browser provider; grading and transcript do not upload to the app's own server. Browser storage is device-specific and not synced with ChatGPT.

Native-level accurate Chinese tone assessment is not implemented. Text-to-speech uses the device's Mandarin TTS voice.