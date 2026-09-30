# ⠙⠊⠵⠵⠽ Dizzy Braille — The Best Image-to-Braille Converter

[![Pure Vanilla JS](https://img.shields.io/badge/Vanilla-JavaScript-f7df1e?logo=javascript&logoColor=black)](#)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-success)](#)
[![Single File App](https://img.shields.io/badge/Format-Single%20HTML%20File-blue)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

> **The undisputed, best Image-to-Braille converter available anywhere on the web.**  
> While traditional generators rely on washed-out grayscale thresholds or basic Bayer patterns, **Dizzy Braille** uses state-of-the-art **Dizzy Dithering** coupled with high-speed downsampling and Photoshop-style tone curves to generate crisp, high-contrast Braille art directly in your browser.

---

## ⚡ Why is this the Best Image-to-Braille Converter?

Most online Braille generators are either extremely slow, produce flat and muddy output, or stretch characters into distorted silhouettes. **Dizzy Braille fixes all of that:**

1. **State-of-the-Art Dizzy Dithering:**
   Uses randomized Fisher-Yates coordinate shuffling with omnidirectional 4-way error diffusion. This eliminates repetitive scanline artifacts and banded noise, producing organic, rich textural density.
2. **Scale-First Architecture:**
   Heavy mathematical operations never touch multi-megapixel raw images. Downsampling to the target character matrix is performed **first**, making the entire pipeline run at **60 FPS / under 5ms** per frame.
3. **Photoshop-Style Tone Curves:**
   Includes a built-in Hermite cubic-spline interactive Look-Up Table (LUT) for Shadows, Midtones, and Highlights to bring out lost shadow details and tame blown highlights.
4. **Emphasize Contours (Sobel Filter):**
   Need hard edges? Toggle on gradient magnitude edge detection to carve out sharp silhouettes even on complex backgrounds.
5. **MonoSpace Grid Alignment (`⠄`):**
   Avoid character collapse in monospace layouts. Empty Braille cells can automatically be filled with an unobtrusive single dot (`⠄`, U+2804) to maintain perfect rectangular spacing in text editors and terminals.
6. **Zero Dependencies & Completely Offline:**
   A single, standalone `.html` file. No `npm install`, no backend, no WebAssembly bloat, no analytics. Drag, drop, and convert forever.

---

## 🚀 Live Demo

Run it straight in your browser:  
👉 **[Click here for the Live Demo](https://<your-username>.github.io/best-image-to-braille-converter/)**  
*(Or simply download `index.html` and double-click to open it anywhere).*

---

## 🛠 Features Overview

| Feature | Description |
| :--- | :--- |
| **Dizzy Dithering** | Always-on, non-linear stochastic error diffusion. |
| **Braille Resolution** | Dynamic width slider (15 to 250+ characters) with automatic font aspect ratio compensation. |
| **Image Inversion** | Toggle between "dots on dark" (for white backgrounds) and "dots on light" (for dark terminals). |
| **Viewer Inversion** | Instant dark/light mode toggle for the text preview pane. |
| **MonoSpace Fill** | Fills whitespace with single-dot glyphs (`⠄`) for terminal stability. |
| **Contour Booster** | Sobel convolution filter with variable intensity slider (0–150%). |
| **Grayscale Modes** | Choose between `Luminance` (perceptual human eye), `Average`, `Value`, or `Lightness`. |
| **Random Seed Reshuffle** | Re-roll the randomized Dizzy noise matrix on the fly without changing settings. |
| **Clipboard & File Export**| One-click instant copy to clipboard or `.txt` download. |

---

## 🧠 Design Philosophy & FAQ

#### Q: Why can't I turn off Dizzy Dithering?
> **A:** Because this is the *best* image-to-Braille converter. Basic thresholding and crude ordered dithering look terrible on low-density Braille grids. Dizzy Dithering is the foundational secret sauce of this project—why degrade perfection?

#### Q: What language is the UI in?
> **A:** The interface is natively presented in Ukrainian, built with love and clean code. Modern browsers offer instant auto-translation, but the layout is completely self-explanatory regardless.

#### Q: How does Braille Dot Mapping work?
Each Braille Unicode character (`U+2800` to `U+28FF`) represents a $2 \times 4$ dot matrix. Each character has 8 discrete bits mapped directly to the downsampled dither buffer:

 Dot 1: (x+0, y+0) -> 0x01    Dot 4: (x+1, y+0) -> 0x08
 Dot 2: (x+0, y+1) -> 0x02    Dot 5: (x+1, y+1) -> 0x10
 Dot 3: (x+0, y+2) -> 0x04    Dot 6: (x+1, y+2) -> 0x20
 Dot 7: (x+0, y+3) -> 0x40    Dot 8: (x+1, y+3) -> 0x80


---

## 📦 How to Use

1. Clone or download this repository:
   ```bash
   git clone https://github.com/<your-username>/best-image-to-braille-converter.git
   ```
2. Open `index.html` in any web browser.
3. Drag & drop any image (or paste directly via `Ctrl+V`).
4. Adjust the character width and threshold.
5. Click **"Скопіювати арт"** (Copy Art) and paste it into your terminal, Discord, or README!
