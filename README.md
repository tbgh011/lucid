<hr>
<h2>Lucid v1.3.4 — Video File Align &amp; Stack</h2>
<h3>What's New in v1.3.4</h3>
<ul>
<li><strong>True Drizzle reconstruction (super-resolution)</strong> — a new <em>True drizzle</em> option on the Stack tab (needs Drizzle set above 1x) rebuilds the stacked image with variable-pixel linear reconstruction instead of the previous backwards-bilinear accumulate. Every frame is globally aligned and its pixels are dropped onto a grid three times finer than the sensor, then bicubic-downsampled to the drizzle scale. Because the planet drifts slightly between frames, real sub-pixel samples fill the finer grid — recovering genuine detail from natural jitter rather than interpolating — and the uniform, quality-weighted accumulation gives a noticeably cleaner disk (no quilted texture) than the earlier method. Leave it off for the classic reconstruction</li>
<li><strong>Gradient frame selection (Automatic estimator)</strong> — the Analyze and Batch <em>Automatic</em> quality estimator now ranks frames by edge sharpness (gradient magnitude) instead of pixel-to-pixel variance. On poor-seeing captures this stops the selection from favoring grainy frames that variance mistakes for sharpness, so the frames that actually contribute are genuinely sharper; on clean captures it makes no difference. The change is automatic — no settings to adjust</li>
<li><strong>Flatten background</strong> — an optional <em>Flatten background</em> toggle on the Stack tab subtracts the sky pedestal so the disk sits on a near-black background, matching a dynamic-background workflow. Off by default, so existing output is unchanged</li>
</ul>

<h3>Downloads</h3>

File | Description
-- | --
lucid_v134.zip | Application + Windows, macOS &amp; Linux installers + PDF guides
Lucid_Installation_Guide_v134.pdf | Installation instructions for Windows, macOS, and Linux
Lucid_User_Guide_v134.pdf | Complete user guide
Lucid_Technical_Reference_v134.pdf | Algorithm and API reference
Lucid_Tutorials_v134.pdf | Step-by-step tutorials for Lunar, Mars, Jupiter, and Saturn

## Installation

### Windows
Download `lucid_v134.zip`, then right-click it and choose **Extract All**.

> Windows extracts into a new folder named after the zip, so you may end up with `lucid_v134\lucid_v134\` — that is normal. To avoid it, delete the trailing `lucid_v134` from the destination path in the Extract dialog.

Open the extracted `lucid_v134` folder, go to `installer\windows\`, then right-click `install.bat` and choose **Run as administrator**.

### Linux
Download `lucid_v134.zip` to your Downloads folder, then open Terminal and run:

```bash
cd ~/Downloads
unzip lucid_v134.zip
bash ~/Downloads/lucid_v134/installer/linux/install.sh
```

### macOS
Download `lucid_v134.zip` — macOS will automatically extract it to your Downloads folder. Then open Terminal and run:

```bash
bash ~/Downloads/lucid_v134/installer/macos/install.sh
```
