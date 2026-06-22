# Extraction Algorithm And Tradeoffs

This document explains the current slide extraction approach used by `slides2pdf` and the tradeoffs behind it.

## Overview

`slides2pdf` is designed for slide-heavy videos such as lectures, webinars, screen recordings, and product demos. The current approach detects visual changes between sampled video frames and captures frames that appear to represent slide transitions.

The goal is not to understand the semantic content of slides. Instead, the tool provides a fast browser-only workflow for extracting likely slide images that can be reviewed by a human or passed into an AI-assisted research workflow.

## Frame Sampling

The video is sampled at regular intervals. Each sampled frame is reduced to a small grayscale signature. Comparing signatures is much cheaper than comparing full-resolution frames, which helps keep the tool usable in the browser.

This design keeps processing local and avoids requiring a backend service.

## Change Detection

For each sampled frame, the tool compares the current grayscale signature with the previous one. If enough grid cells changed by more than a brightness threshold, the frame is treated as a likely slide change.

The sensitivity control adjusts how many changes are required before a new slide is captured:

- Lower sensitivity produces fewer captures and can reduce noise.
- Higher sensitivity catches more subtle changes but may capture extra frames.

## Exclusion Zones

Videos often include moving regions that are unrelated to slide changes, such as:

- Presenter camera overlays
- Captions or subtitles
- Timers
- Animated lower thirds
- Cursor-heavy regions

Users can draw exclusion zones before analysis. These regions are ignored during change detection, which helps reduce false positives from movement that is not part of the slide content.

## Output Formats

`slides2pdf` supports image and PDF outputs:

- WebP is useful for lightweight batches and AI upload workflows.
- PNG is useful when higher-quality images are preferred.
- PDF is useful for review, archiving, and sharing extracted slide sequences.

## ZIP Volume Splitting

Large slide sets can exceed upload limits in chat or AI review workflows. The tool splits ZIP output into upload-friendly volumes. The current implementation targets approximately 24 MB per ZIP volume.

Because browser-generated ZIP files include file metadata and per-entry overhead, the final file size can vary slightly. Future work may make the size check stricter by validating the generated blob size before offering each volume.

## Known Tradeoffs

The current approach is intentionally simple and browser-friendly. This means:

- Animated slide builds may produce extra captures.
- Very subtle slide changes may be missed.
- Videos with camera movement or transitions may need sensitivity tuning.
- Exact duplicate cleanup is not yet implemented.
- OCR-based slide titles are not yet implemented.

These tradeoffs are acceptable for the first version because the tool is optimized for practical research workflows rather than perfect video segmentation.

## Future Improvements

Planned improvements include:

- Duplicate slide cleanup
- Timestamp metadata export
- More exact ZIP volume-size validation
- Optional OCR-assisted slide naming
- Sample videos and benchmark expected outputs
- Better handling of animated decks and presenter overlays
