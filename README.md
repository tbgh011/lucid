# Lucid — Video File Align & Stack

Lucid is a free, open source, actively developed video file align and stack application for Linux, macOS and Windows. It takes SER or AVI video files as input, analyzes each frame for quality, aligns them to a common reference, and stacks the best frames to produce a high signal-to-noise output image.

## Reporting Bugs and Requesting Features
To report a bug, request a feature, or ask a question, please use the **Issues** tab at the top of this repository.

1. Click **Issues**
2. Click **New Issue**
3. Choose the Bug Report or Feature Request template
4. Fill in the details and submit

This helps keep all feedback organized and easy to track.

## Features

- Quality-ranked frame selection with Laplacian sharpness metric
- Raw Bayer quality analysis (~43× more sensitive than debayered analysis)
- Centroid-based global alignment (sub-pixel accuracy, <0.02 px typical error)
- Alignment Point (AP) local shift-field correction via Gaussian RBF interpolation
- RGB channel alignment for atmospheric dispersion correction
- Backwards bilinear drizzle at 1×, 1.5×, 2×, and 3× scale (full √N noise reduction)
- Sigma-kappa outlier rejection
- Histogram overlay (log-scale, AS!4 style)
- Multi-percentage stacking in a single run (F25, F50, F75 subfolders)
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
Extract the zip, open `installer\windows\`, right-click `install.bat` and choose **Run as administrator**.

### macOS
Extract the zip, open Terminal, `cd` to `installer/macos/`, and run:
```bash
bash install.sh
```

### Linux
Extract the zip, open Terminal, `cd` to `installer/linux/`, and run:
```bash
bash install.sh
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

## Copyright

Copyright © 2026 Tony Bailey. (tbgh011)

This project — **Kepler: Planetary Image Processing Suite** — is released under the MIT License.  
You are free to use, modify, distribute, and build upon this software, provided that the original copyright notice and license text are included in all copies or substantial portions of the software.

See the [LICENSE](LICENSE) file for full terms.
