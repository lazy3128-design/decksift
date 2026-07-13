# DeckSift v0.3.0

DeckSift v0.3.0 improves review speed, output naming, and extraction quality for presenter-led and interview videos while preserving the existing slide-focused workflow.

## Added

- A visible video-type selector with separate slide-focused and presenter-and-caption modes
- Presenter-and-caption detection for talking-head videos, interviews, and discussions
- Color-aware caption matching to distinguish real caption changes from facial expressions, gestures, and speaker movement
- One-sample look-ahead for brief caption-free transitions and delayed captions after scene cuts
- Previous/next buttons in the enlarged image preview
- Left/Right arrow-key navigation and an image-position counter
- Visible status feedback when ZIP and CSV downloads start

## Improved

- Extracted image filenames now use clean sequence numbers such as `001.webp`
- Individual downloads, ZIP entries, and CSV metadata use the same numbered filenames
- ZIP entries set the UTF-8 filename flag for consistent extraction across platforms
- Presenter-mode thresholds were tuned against manually reviewed false positives
- Documentation now explains when to use exclusion zones versus presenter-and-caption mode

## Validation

- JavaScript syntax and repository diff checks pass
- Desktop and narrow-width layouts were visually checked
- A 23-minute presenter/interview regression video was reviewed manually
- The original detector produced 683 captures; the refined presenter mode produced 594, about 13% fewer
- Reviewed distinct caption changes were retained while repeated poses, same-caption frames, and brief caption-free transitions were reduced

This benchmark is one real-world regression case, not a universal accuracy guarantee. More public test cases and expected outputs are tracked in [issue #5](https://github.com/lazy3128-design/decksift/issues/5).

## Unchanged

- Slide-focused mode remains available for slide decks, screen recordings, and fixed picture-in-picture layouts
- Exclusion zones can still ignore presenter cameras, captions, clocks, cursors, or other moving regions
- Video processing remains local to the browser
- WebP, PNG, split ZIP, PDF, individual image, and timestamp CSV outputs remain supported

## Known Limitations

- Unusual subtitle colors or layouts may still produce extra captures
- Highly animated decks may require sensitivity adjustment
- Very long videos remain subject to browser memory and processing limits
