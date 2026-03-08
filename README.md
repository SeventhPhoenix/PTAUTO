# 🌎 Pluto TV Playlists (Auto-Updating)

![Auto Update](https://img.shields.io/badge/JWT-Auto%20Refreshed-brightgreen)
![Client ID](https://img.shields.io/badge/UUID-Auto%20Generated-blue)

Automatically generates and refreshes a **Pluto TV M3U playlist** with a valid session token using GitHub Actions.

A new random **UUID v4 clientID** is generated automatically during each workflow run. No manual UUID setup required.

---

## 🚀 How It Works

- GitHub Actions runs on a schedule.
- A fresh random **UUID v4** is generated automatically for `clientID`.
- A fresh Pluto session JWT is requested.
- The M3U playlist is regenerated using:
  - An auto-generated `clientID`
  - A valid session token
- The updated playlist is committed to your fork.

No manual token updates or UUID generation required.

---

# 📌 Setup Instructions

## 1️⃣ Fork This Repository

Click **Fork** in the top right of this page.

You now have your own independent copy.

---

## 2️⃣ Run the Workflow

No config changes are required for basic use.

1. Go to the **Actions** tab in your fork.
2. Select **Auto Pluto Update**.
3. Click **Run workflow**.
4. Wait for the workflow to complete.

The workflow will automatically:

- generate a new UUID v4 for `clientID`
- request a fresh Pluto session token
- regenerate the playlist
- commit updated output files

After that, the workflow will continue updating automatically on schedule.

---

## 3️⃣ Optional: Adjust `config.json`

You can edit other settings in `config.json` if needed, such as:

- output directory
- region mapping
- grouping options
- refresh settings
- channel filtering

Example:

{
  "outdir": "./output",
  "mapping": {
    "us": "45.50.96.71",
    "uk": "51.89.255.67",
    "ca": "23.227.38.65",
    "de": "91.107.201.140",
    "fr": "51.210.0.1",
    "es": "82.98.134.10",
    "it": "79.137.44.85"
  },
  "all": false,
  "group": "genre",
  "regionalize": false,
  "excludeGroups": false,
  "excludeChannels": false,
  "uniqueClientid": false,
  "randomClientid": false,
  "refresh": 0,
  "xTvgUrl": false,
  "ondemand": false,
  "vlcopts": false,
  "pipeopts": false
}

`clientID` is handled automatically by `index.js` during each run.

---

# 📂 Access Your Playlist

After the workflow completes:

1. Open the `output/` folder.
2. Locate:
   plutotv_us.m3u8
3. Click **Raw**
4. Copy the URL.

RAW URL format:

https://raw.githubusercontent.com/YOUR_USERNAME/REPO_NAME/main/output/plutotv_us.m3u8

Add this URL to your IPTV player:

- TiviMate
- IPTV Smarters
- OTT Navigator
- VLC
- Any M3U-compatible player

---

# 🔄 Automatic Updates

The workflow automatically:

- generates a new UUID v4 `clientID`
- requests a fresh Pluto session token
- regenerates playlist URLs
- commits updated files

Since Pluto session tokens expire regularly, this automation keeps the playlist valid.

---

# 📺 EPG (Electronic Program Guide)

https://raw.githubusercontent.com/matthuisman/i.mjh.nz/refs/heads/master/PlutoTV/all.xml

---

# ⚠️ Important Notes

- Do not share your generated playlist publicly.
- A new `clientID` is generated automatically on each workflow run.
- Excessive requests may result in temporary IP rate limiting.
- This project is intended for personal use.

---

# 🙏 Credits

Based on:
https://github.com/4v3ngR/pluto_tv_scraper

EPG data provided by:
https://github.com/matthuisman/i.mjh.nz
