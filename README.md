# GHI at BlackHat — Prize Wheel

A single-page spin-the-wheel for the GHI booth at BlackHat. Runs entirely in the
browser, works fully offline once loaded, and needs no build step or server.

**Live:** https://funguscyberpenguin.github.io/ghi-prize-wheel/

## Features

- 🎡 Spin by tapping **anywhere on the wheel** or the **Spin** button — smooth 4s ease-out with confetti.
- ✎ **Edit prizes** in a pop-up modal: add prizes, remove them, or use the +/− steppers to give a prize more slices (better odds).
- ▶ **Booth mode** — one tap turns it into a touchscreen kiosk (see below).
- ☑ Optional **remove-the-winner-after-each-spin** for door-prize style draws.
- 💾 Your prize list is saved in the browser (localStorage) and survives refreshes.
- 📴 100% offline & client-side — nothing is uploaded anywhere.

## Booth mode (touchscreen kiosk)

Tap **Booth mode** to run it guest-facing on a touchscreen:

- **Fullscreen** with the wheel scaled up big, no browser chrome or operator buttons.
- **Screen stays awake** (Wake Lock) so the display won't sleep during the event.
- **Tap the wheel to spin** — the whole wheel is one big touch target.
- **Winner takeover** — a full-screen "🎉 WINNER: _prize_" readable across the aisle, with a **Next spin** button.
- **Attract mode** — the wheel pulses "Tap to spin" when idle to pull people over.
- **Two ways to exit** (both need a deliberate ~1-second hold so a guest can't bump them):
  - **Hold the ✕ in the top-right corner** — exits straight back to normal mode (a red ring fills as you hold).
  - **Hold the 🔒 in the top-left corner** — opens an on-screen number pad; enter the PIN to exit.
  - Default PIN is **`1337`** — change it in **Edit prizes → Booth exit PIN**.
  - On the laptop keyboard, **Esc** also exits booth mode.

> Fullscreen and keep-awake need HTTPS — they work on the live GitHub Pages URL, not always when opening the raw file locally.

## Editing prizes

Click **Edit prizes**. Add one per line, bump the count with **+** to weight a
prize higher, or **×** to remove it. There's also an *Advanced: edit as text*
box for bulk paste. To restore the original list, hit **Reset defaults**.

## Running locally

Just open `index.html` in any browser, or serve the folder:

```bash
python -m http.server 8000
```

## Files

- `index.html` — the whole app (HTML + CSS + JS)
- `logo.png` — GHI logo (header, favicon)
- `donate-qr.svg` — donation QR code shown in the wheel hub

## Donation QR code

The hub in the middle of the wheel is a QR code pointing at
https://hcb.hackclub.com/donations/start/gingerhacker so guests can scan it
while they wait for a spin. It's a static file, so it still works with no
network at the booth.

To point it somewhere else, regenerate `donate-qr.svg`:

```bash
pip install segno
python -c "import segno; segno.make('https://YOUR-URL-HERE', error='m').save('donate-qr.svg', scale=10, border=2, dark='#0b0c10', light='#ffffff', omitsize=True)"
```
