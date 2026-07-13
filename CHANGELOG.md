# Changelog

All notable changes to this project are documented here.

## Unreleased

- Added previous/next controls, keyboard arrow navigation, and an image counter to the enlarged preview
- Simplified extracted image filenames to numbered names such as `001.webp`
- Added an optional presenter-and-caption detection mode that suppresses repeated frames caused by presenter movement
- Added a short look-ahead check to discard brief caption-free transition frames in presenter videos

## v0.2.0 - 2026-07-13

- Renamed the project from `slides2pdf` to `DeckSift`
- Moved the complete browser app into this repository and removed the iframe dependency
- Added CSV metadata export with slide numbers, filenames, source video names, and timestamps
- Updated project documentation and live demo links for the DeckSift name
- Added extraction algorithm and tradeoff documentation
- Linked implementation notes from the README

## v0.1.1

Documentation and maintenance update.

- Documented the AI-assisted research workflow
- Clarified upload-friendly ZIP volume splitting
- Added guidance for using extracted slide ZIP files with Claude, ChatGPT, and other multimodal assistants
- Clarified the current implemented capabilities in the README
- Added project maintenance and release history documentation

## v0.1.0

Initial public release.

- Added MP4/video slide-like frame extraction
- Added image export for captured slides
- Added PDF generation from extracted slides
- Added WebP output for lightweight image batches
- Added PNG output option
- Added exclusion-zone selection for moving regions such as captions, presenter cameras, and overlays
- Added ZIP export for extracted frames
- Added individual frame saving from generated outputs
- Added split ZIP output for upload-friendly volumes
- Added browser-only local processing with no required backend
