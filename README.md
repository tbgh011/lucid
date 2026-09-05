# Lucid — Video File Align & Stack

Lucid is a free, open source, actively developed video file align and stack application for Linux, macOS and Windows.

## Reporting Bugs and Requesting Features

To report a bug, request a feature, or ask a question, please use the **Issues** tab at the top of this repository.

1. Click **Issues**
2. Click **New Issue**
3. Choose the Bug Report or Feature Request template
4. Fill in the details and submit

This helps keep all feedback organized and easy to track.

## Features

- Quality-ranked frame selection with Laplacian sharpness metric
- Multi-threaded analysis with an adaptive decoded-frame RAM buffer (reused across Analyze, Stack, and every Expand window)
- **Bayer Drizzle** — raw R/G/B sensor samples reconstructed on separate color grids with **no per-frame demosaic**, for sharper color with far less speckle (automatic for any raw Bayer file)
- **JIT-accelerated, multi-core stacking** (compiled scatter across all cores; automatic NumPy fallback with identical output)
- Disk-locked centroid alignment (sub-pixel accuracy, robust to nearby moons)
- Two alignment modes: Global (one whole-disk stack) and Local (per-AP) — lucky-region stacking that keeps each region's own locally-sharpest frames for noticeably crisper detail when stacking selectively
- Feature-driven Alignment Point (AP) placement — true multi-scale size tiers, snapping to local detail (belt edges, limb, crater rims), ring shadow detection, and irregular spacing that skips dark/featureless areas
- RGB channel alignment for atmospheric dispersion correction
- Optional pre-process blur (vertical/horizontal) that steadies alignment on noisy or low-contrast targets without softening the stacked image
- Bicubic sub-pixel warping (sharper than bilinear, no edge ringing)
- Single **Drizzle** control — 1×, 1.5×, 2×, 3× (separate-channel Bayer Drizzle for raw CFA files; forward variable-pixel drizzle for mono/RGB)
- Sigma-kappa outlier rejection
- Histogram overlay (log-scale, luminance + RGB channels)
- Multi-percentage stacking in a single run (F25, F50, F75 subfolders)
- Expand Recording — split one continuous capture into a sequence of stacks (by number of stacks or segment length, with optional overlap), each named by its midpoint UTC capture time for derotation
- Batch processing for multiple video files
- Session save and restore (.json)
- Output: TIFF 16-bit, PNG, FITS

## Supported Formats

- **Input:** SER (raw Bayer RGGB/GRBG/GBRG/BGGR, BGR color, monochrome), AVI
- **Output:** TIFF 16-bit, PNG, FITS

## Download

See the [Releases page](https://github.com/tbgh011/lucid/releases) to download the latest version.

## Requirements

- Python 3.8+
- Windows 10/11, Linux (Ubuntu / Mint / Debian / Fedora / Arch), or macOS 10.15+
- macOS requires Python 3.11+ (the system Python has a broken Tk)
- The included installer handles all dependencies automatically

## Installation

### Windows

Download `lucid_v200.zip`, then right-click it and choose **Extract All**.

> Windows extracts into a new folder named after the zip, so you may end up with `lucid_v200\lucid_v200\` — that is normal. To avoid it, delete the trailing `lucid_v200` from the destination path in the Extract dialog.

Open the extracted `lucid_v200` folder, go to `installer\windows\`, then right-click `install.bat` and choose **Run as administrator**.

### Linux

Download `lucid_v200.zip` to your Downloads folder, then open Terminal and run:

```bash
cd ~/Downloads
unzip lucid_v200.zip
bash ~/Downloads/lucid_v200/installer/linux/install.sh
```

### macOS

Download `lucid_v200.zip` — macOS will automatically extract it to your Downloads folder. Then open Terminal and run:

```bash
bash ~/Downloads/lucid_v200/installer/macos/install.sh
```

The installer GUI will open and guide you through the rest of the process.

## Documentation

Full documentation is included as downloads on the Releases page:

| Document | Description |
|----------|-------------|
| Installation Guide | Step-by-step installation for Windows, macOS, and Linux |
| User Guide | Interface reference, tab descriptions, practical tips |
| Technical Reference | Algorithm details, architecture, API reference |
| Tutorials | Worked examples for Jupiter, Saturn, and other targets |

Lucid is based on the concepts of AutoStakkert! (https://www.autostakkert.com/)

## Copyright

Copyright © 2026 Tony Bailey. (tbgh011)

This project — **Lucid: Video File Align & Stack** — is released under the MIT License.  
You are free to use, modify, distribute, and build upon this software, provided that the original copyright notice and license text are included in all copies or substantial portions of the software.

See the [LICENSE](LICENSE) file for full terms.
