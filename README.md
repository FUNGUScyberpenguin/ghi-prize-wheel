# GHI at BlackHat — Prize Wheel

A single-page spin-the-wheel for the GHI booth at BlackHat. Runs entirely in the
browser, works fully offline once loaded, and needs no build step or server.

**Live:** https://funguscyberpenguin.github.io/ghi-prize-wheel/

## Features

- 🎡 Spin by tapping the **logo** or the **Spin** button — smooth 4s ease-out with a winner celebration + confetti.
- ✎ **Edit prizes** in a pop-up modal: add prizes, remove them, or use the +/− steppers to give a prize more slices (better odds).
- ⛶ **Enlarge wheel** mode for projecting on a big screen at the booth.
- ☑ Optional **remove-the-winner-after-each-spin** for door-prize style draws.
- 💾 Your prize list is saved in the browser (localStorage) and survives refreshes.
- 📴 100% offline & client-side — nothing is uploaded anywhere.

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
- `logo.png` — GHI logo (header, spin hub, favicon)
