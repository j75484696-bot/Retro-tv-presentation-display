# 📺 Retro TV Presentations

A fully interactive, browser-based presentation system built inside a 3D retro television. No installation. No server. Open the HTML file and go.

---

## Getting Started

1. Open `retro-tv-final.html` in any modern browser (Chrome, Edge, Firefox, Safari)
2. Wait for the intro animation to finish (~3 seconds)
3. Use the **Broadcast Control** panel at the bottom to load your files
4. Click the TV's tuner knobs to advance slides — or use the keyboard

That's it. No internet connection required after the page first loads.

---

## Loading Presentations

The panel at the bottom has two channels — **CH 1 (Presentation A)** and **CH 2 (Presentation B)**. You can load a different file into each channel and switch between them live.

| Format | Notes |
|--------|-------|
| **PDF** | Best quality. Every slide renders pixel-perfectly. Recommended. |
| **PPTX / PPT** | Supported. Text, images, shapes, tables, and gradients all render. Complex animations and custom fonts may not appear exactly as in PowerPoint. |
| **PNG / JPG / GIF / WebP** | Single image loads as a one-slide presentation |

> **Tip:** For the best PPTX results, export your PowerPoint as PDF first (File → Export → PDF) and load that instead. PDF rendering is always pixel-perfect.

---

## Controls

### Mouse
| Action | What it does |
|--------|--------------|
| Click a **tuner knob** on the TV | Advance to next slide on that channel |
| Click the **red PWR button** | Open fullscreen mode |
| **Drag** the Broadcast Control panel header | Move the panel anywhere on screen |
| **Drag** the 3D canvas | Orbit the camera around the TV |

### Keyboard
| Key | Action |
|-----|--------|
| `← / →` or `↑ / ↓` | Previous / Next slide |
| `Space` | Next slide |
| `A` | Switch active channel to A |
| `B` | Switch active channel to B |
| `F` | Toggle fullscreen mode |
| `T` | Start / stop auto-advance timer |
| `Esc` | Exit fullscreen or close shortcut HUD |
| `?` | Show / hide keyboard shortcut overlay |

---

## Fullscreen Mode

Press **F**, click the **⛶** button, or click the **red PWR button** on the TV to enter fullscreen.

In fullscreen:
- The slide fills the screen with a **drop shadow** and **rounded corners**
- The background color **dynamically shifts** to complement the colors in the current slide
- Each slide change plays a **transition animation** (cycles through 5 styles: slide left, slide right, zoom, slide up, fade)
- Going backward always plays a right-to-left slide animation
- A **progress bar** at the very bottom shows how far through the deck you are
- The right panel shows the flat circular tuner knobs — click them to advance slides
- The **slide size slider** (with − and + buttons) lets you scale the slide from 10% to 100%
- Press **Esc** or click the red **⏻** button to exit

---

## Auto-Advance Timer

In the Broadcast Control panel, use the **AUTO-ADV** row:

1. Type a number of seconds (e.g. `5`)
2. Click **▶ START** (or press `T`)
3. The timer counts down and automatically advances to the next slide
4. Click **■ STOP** (or press `T` again) to stop it

The timer respects whichever channel is currently active and works in both normal and fullscreen mode.

---

## Broadcast Control Panel

The panel is **draggable** — grab the header bar (where the colored dots are) and drag it anywhere. It snaps back to bounds so it never goes off-screen.

The panel shows:
- **Slide counter** and **progress bar** per channel
- Which channel is currently **active** (highlighted in orange)
- **Load** buttons for each channel
- **Auto-advance timer** controls

---

## Ambient Lighting

The room lighting reacts to your slides. The green point light near the TV screen slowly shifts color to match the dominant hues of whatever slide is currently showing — warm slides warm the room, cool slides cool it down.

---

## Technical Notes

- **No backend or server required** — runs entirely in the browser
- **WebGL required** — uses Three.js for the 3D TV scene. If WebGL is unavailable, an error message will appear
- **Dependencies loaded from CDN on first use:**
  - Three.js r160 (3D rendering)
  - GSAP 3.12 (animations)
  - PDF.js 3.11 (PDF parsing, loaded when you upload a PDF)
  - JSZip 3.10 (PPTX parsing, loaded when you upload a PPTX)
- After the first load, all CDN assets are cached by the browser

---

## Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 15+ | ✅ Full |
| Mobile browsers | ⚠️ Works but not optimized for touch |

---

## Known Limitations

- PPTX **animations** (entrance effects, motion paths) are not played — only the final state of each slide is shown
- **Custom fonts** embedded in PPTX files fall back to system fonts
- **Charts** in PPTX files are not rendered (chart frames are skipped)
- **SmartArt** is not rendered
- Very large PDF files (50+ pages) may be slow to load as each page is rasterized in the browser

---

## File Structure

```
retro-tv-final.html   ← The entire application. Single self-contained file.
README.md             ← This file
```

Everything is in one HTML file. No build step, no dependencies to install, no configuration.
