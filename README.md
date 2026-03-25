# Lucid — Video File Align & Stack

Lucid is a video file align and stack application for planetary, lunar, and solar astronomy. It takes SER or AVI video files as input, analyzes each frame for quality, aligns them to a common reference, and stacks the best frames to produce a high signal-to-noise output image.

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

## Workflow

1. **Load** — Open a SER or AVI video file
2. **Analyze** — Quality-rank all frames; set the stack percentage
3. **Align** — (Optional) place Alignment Points for local shift-field correction
4. **Stack** — Choose drizzle scale and output format; click Stack Frames
5. **Post-process** — Open the stacked TIFF in Kepler or your processing software

## About

Lucid is designed to complement AutoStakkert!4 and similar stacking tools. Its particular strengths are flexible quality-ranked stacking with drizzle integration and local AP shift-field correction.
