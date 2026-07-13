# Privacy And Data Handling

This document explains how `DeckSift` handles video files and generated outputs.

## Local Browser Processing

`DeckSift` is designed as a browser-based static tool. Selected video files are read and processed inside the user's browser using browser APIs.

The project does not require a backend server for slide extraction, image generation, ZIP creation, or PDF generation. The original video is not intentionally uploaded by `DeckSift` during normal use.

## Generated Outputs

Generated slide images, ZIP volumes, PDFs, and timestamp CSV files are created in the browser and downloaded by the user. Users control where those generated files are stored and whether they are shared with another service.

## AI And Third-Party Uploads

Uploading generated images, ZIP files, or PDFs to an AI assistant or another third-party service is a separate action performed by the user. Before uploading generated material, users should:

- Confirm that they have permission to share the source material
- Remove confidential, personal, or sensitive information when necessary
- Review the destination service's privacy and data-handling policies
- Avoid uploading copyrighted material without authorization

## Browser And Device Considerations

Because processing happens in the browser, performance and memory usage depend on the user's device, browser, video length, resolution, and output settings. Very large videos or image batches may use substantial local memory.

Closing or refreshing the page may remove generated previews that have not yet been downloaded.

## Project Commitments

Changes to the project should preserve clear user control over video files and generated outputs. New features that introduce telemetry, server-side processing, external upload, or third-party data transfer should be documented clearly and require explicit user consent.

## Reporting Privacy Or Security Concerns

Privacy or security concerns can be reported through the repository's GitHub issues. Do not include private videos, confidential files, authentication information, or sensitive personal data in public reports.

See also [SECURITY.md](../SECURITY.md).
