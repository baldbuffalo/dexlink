# DexLink
**Run Samsung DeX on your Tesla browser — no hardware, no hacks.**

Opens a VNC stream from Tesla's browser to your Samsung phone in DeX mode. Access any app (Waze, YouTube, anything) on your Tesla screen.

---

## One-Time Setup

### 1. Install DroidVNC-NG on your Samsung
- Download from the **Play Store** or [F-Droid](https://f-droid.org)
- Open it → **Settings**
  - Enable **WebSocket** transport
  - Enable **SSL / TLS** (this gives you WSS, required for HTTPS pages)
  - Set a password if you want (optional)
- Tap **Start** — the app shows your phone's local IP address

### 2. Accept the Self-Signed Certificate (Tesla browser, one-time only)
1. Connect your Tesla to your phone's hotspot
2. In Tesla's browser navigate to: `https://[your-phone-ip]:6080`
3. You'll get a security warning — tap **Advanced → Proceed**
4. Done. You never need to do this again unless the cert regenerates

### 3. Set Up Bixby Routines (fully automatic, optional but recommended)

**Routine A — when you get in the car:**
- **Trigger:** Bluetooth connects to `[your Tesla's name]`
- **Actions:** Enable Mobile Hotspot → Open DroidVNC-NG

**Routine B — when you get out:**
- **Trigger:** Bluetooth disconnects from `[your Tesla's name]`
- **Actions:** Close DroidVNC-NG → Disable Mobile Hotspot

---

## Daily Use

1. Get in Tesla → Bixby auto-enables hotspot and starts VNC server
2. Tesla connects to your hotspot automatically
3. Open Tesla browser → go to your GitHub Pages URL
4. Your last IP/port are remembered — tap **Connect**
5. Samsung DeX appears on your Tesla screen

To show the Disconnect / Fullscreen buttons while connected, **tap the screen**.

---

## Data Usage

Zero. The hotspot creates a private local network between your phone and Tesla — traffic never goes through your mobile data. Your phone still has full mobile data for WhatsApp, calls, and everything else alongside it.

---

## GitHub Pages Setup

1. Create a new GitHub repo (e.g. `dexlink`)
2. Drop `index.html` in the root
3. Go to **Settings → Pages → Source: main branch / root**
4. Your site is live at `https://[username].github.io/dexlink`

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "Connection failed" on first try | Accept the cert first (Step 2 above) |
| Black screen after connecting | Put phone into DeX mode *before* connecting |
| Can't see controls | Tap anywhere on the screen |
| Hotspot IP is different | Check DroidVNC-NG — it shows your current IP |
| Choppy / laggy | Normal on first connect; improves after a few seconds |
