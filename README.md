# Subtitle Resync

A one-page web app that fixes the timing of an out-of-sync subtitle (for example a Sinhala `.srt`). Only the timings change. The text is never translated or replaced.

1. **Your movie file:** choose the video, or type its file name.
2. **Out-of-sync subtitle:** choose the `.srt`, or the `.zip` it came in.
3. **Reference subtitle:**
   - **Find reference subtitle** looks inside the video first (if it's an MKV), then searches SubDL and OpenSubtitles in every language, and shows everything in one list. The best match is marked.
   - **Choose reference subtitle** uses a file from your device instead.
4. Press **Sync subtitles**, check the timeline, then **Download .srt**.

Works in any modern browser on a PC or a phone. The video is never uploaded. The app reads its name, its size and a 128 KB fingerprint, and for MKV files it reads the subtitle tracks inside it, all on your device.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app (HTML, CSS and JavaScript in one file) |
| `manifest.webmanifest` | Lets phones add it to the home screen like an app |
| `icon-192.png`, `icon-512.png` | App icons |

## Publish on GitHub Pages

1. Upload all four files to the root of your repository, replacing the old ones.
2. In **Settings → Pages**, deploy from the **main** branch, **/ (root)** folder.
3. The site is live at `https://<your-username>.github.io/<repository>/` after a minute.

On a phone, open that address in Chrome and choose **Add to Home screen**.

## API keys

Two keys are built into `index.html` (search for `BUILT_IN`): one for OpenSubtitles and one for SubDL. GitHub Pages sites are public, so anyone who opens the page source can read them.

To keep them private, set both to `''` before uploading, then open **Settings → Use different API keys** in the app and paste your keys once on each device. They're stored only in that browser.

- OpenSubtitles keys: opensubtitles.com → API consumers
- SubDL keys: subdl.com → account → API

## Daily limits

- **Inside your video:** no limit, no internet needed.
- **SubDL:** about 2,000 searches a day on a free key; downloads have their own daily allowance.
- **OpenSubtitles:** a few downloads a day per internet connection.

Any reference you've already downloaded is saved in the browser, so using it again doesn't count.
