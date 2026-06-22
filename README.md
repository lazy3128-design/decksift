# slides2pdf

Browser-based MP4 slide extractor for research, lectures, webinars, and video review workflows.

`slides2pdf` detects slide-like scene changes in an MP4 video and exports the captured frames as WebP/PNG images or a single PDF. It runs entirely in the browser, so videos are processed locally and are not uploaded to a server.

Live demo: https://lazy3128-design.github.io/slides2pdf/

## Why This Exists

When researching webinars, product demos, online courses, talks, or recorded presentations, it is often useful to turn a long video into a set of reviewable slides. Manual screenshots are slow, and full video transcription does not preserve visual layout.

`slides2pdf` helps convert video-based slide content into lightweight image/PDF materials that can be reviewed, annotated, summarized, or archived.

## Current Capabilities

- Extracts slide-like frames from MP4/video files
- Exports captured frames as images
- Generates a PDF from extracted slides
- Exports lightweight WebP images for smaller upload size
- Supports PNG output when higher-quality images are needed
- Lets users select exclusion zones for moving regions such as captions, presenter cameras, or overlays
- Downloads extracted frames as ZIP files
- Supports saving individual frames from the preview/output while processing
- Splits ZIP output into upload-friendly volumes for AI and chat workflows
- Supports multiple videos in one session
- Adjustable sensitivity for fewer or more extracted slides
- Runs locally in the browser with no installation

## Use Cases

- Researching webinars, lectures, demos, and conference talks
- Turning recorded presentations into reviewable slide material
- Extracting visual references from product walkthrough videos
- Creating quick PDF summaries from screen-recorded slide decks
- Preparing source material for qualitative analysis or note-taking
- Preparing slide image batches for AI review tools such as Claude, ChatGPT, or other multimodal assistants

## AI Review Workflow

A common workflow is to extract slides from a long video, download the captured frames as ZIP files, and upload the ZIP volumes to an AI assistant for summarization, comparison, or research notes.

To support this workflow, `slides2pdf` keeps ZIP downloads under 24 MB per volume. This makes large slide extraction jobs easier to upload in environments with file-size limits.

Example workflow:

1. Extract slide frames from a webinar, lecture, or product demo video.
2. Download the WebP ZIP output.
3. Upload one ZIP volume at a time to an AI assistant.
4. Ask for a summary, comparison table, research notes, or follow-up questions.

See the detailed [AI-assisted research workflow guide](docs/ai-workflow.md) for example prompts, privacy notes, and practical limitations.

## Privacy

The tool processes videos locally in the user's browser. It does not intentionally upload video files to a server. Generated images, ZIP volumes, and PDFs remain under user control unless the user chooses to share them with another service.

See [Privacy and Data Handling](docs/privacy.md) for details about local processing, generated outputs, third-party uploads, and device considerations.

## Implementation Notes

The current extraction approach is based on visual frame sampling, grayscale signatures, change thresholds, sensitivity controls, and optional exclusion zones. See [Extraction Algorithm And Tradeoffs](docs/algorithm.md) for details.

## How To Use

1. Open the live demo.
2. Drag and drop one or more MP4/video files.
3. Optionally mark areas to ignore, such as a presenter camera overlay.
4. Start analysis.
5. Download extracted images as ZIP or generate a PDF.

## Current Limitations

- Detection is based on visual frame differences, not semantic slide understanding.
- Highly animated slides may produce extra captures.
- Subtle slide changes may require higher sensitivity.
- Very long videos can take time because processing happens in the browser.
- Browser memory limits may affect very large files.
- ZIP volume size is controlled by an approximate size limit, so real-world file size can vary slightly by browser and image format.

## Roadmap

- Improve slide change detection for animated decks
- Add duplicate slide cleanup
- Add optional OCR-assisted slide naming
- Add a batch summary workflow for research notes
- Add test videos and benchmark examples
- Improve accessibility and keyboard navigation
- Package the tool as an installable PWA

## Maintenance

The project tracks release history in [CHANGELOG.md](CHANGELOG.md) and uses GitHub issues for planned improvements, bug reports, and research workflow ideas.

## Maintainer

Maintained by [lazy3128-design](https://github.com/lazy3128-design).

## License

MIT License.
