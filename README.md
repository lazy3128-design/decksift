# DeckSift

Browser-based video slide extractor for research, lectures, webinars, and AI-assisted review workflows.

Formerly named `slides2pdf`, DeckSift now reflects its broader WebP, PNG, ZIP, PDF, and metadata export workflow.

`DeckSift` detects slide-like scene changes in video files and exports WebP/PNG images, split ZIP volumes, a PDF, and timestamp metadata as CSV. It runs entirely in the browser, so videos are processed locally and are not uploaded to a server.

Live demo: https://lazy3128-design.github.io/decksift/

## Why This Exists

When researching webinars, product demos, online courses, talks, or recorded presentations, it is often useful to turn a long video into a set of reviewable slides. Manual screenshots are slow, and full video transcription does not preserve visual layout.

`DeckSift` helps convert video-based slide content into lightweight image/PDF materials that can be reviewed, annotated, summarized, or archived. For web marketers and funnel designers, the timestamped output also provides visual evidence of which design and message appeared at each point in a campaign or educational video.

## Current Capabilities

- Extracts slide-like frames from MP4/video files
- Exports captured frames as images
- Offers a presenter-and-caption mode to reduce repeated captures caused by presenter movement
- Uses color-aware caption matching to distinguish changed captions from presenter motion
- Removes brief caption-free transition frames while retaining persistent scenes
- Exports slide numbers, filenames, and video timestamps as CSV metadata
- Generates a PDF from extracted slides
- Exports lightweight WebP images for smaller upload size
- Supports PNG output when higher-quality images are needed
- Lets users select exclusion zones for moving regions such as captions, presenter cameras, or overlays
- Downloads extracted frames as ZIP files
- Supports saving individual frames from the preview/output while processing
- Supports previous/next buttons and Left/Right arrow keys in the enlarged preview
- Uses clean numbered image filenames such as `001.webp` in ZIP and CSV output
- Splits ZIP output into upload-friendly volumes for AI and chat workflows
- Supports multiple videos in one session
- Adjustable sensitivity for fewer or more extracted slides
- Runs locally in the browser with no installation

## Choosing A Detection Mode

Use **Slide-focused** mode when slides, screen recordings, or product demos occupy most of the frame. If a presenter appears in a fixed picture-in-picture area, draw an exclusion zone around that area so presenter movement does not trigger extra captures.

Use **Presenter + captions** mode for talking-head videos, interviews, and discussions where people occupy a large part of the frame. This mode gives more weight to caption changes and suppresses repeated captures caused by facial expressions, body movement, speaker changes, and brief caption-free transitions.

The original slide-focused detector remains available so presenter-specific heuristics do not change existing slide-heavy workflows.

## Use Cases

- Researching the visual and messaging sequence of authorized competitor campaign videos
- Building evidence-backed funnel research for clients
- Comparing hooks, claims, proof, offers, and calls to action alongside a transcript
- Planning in-house educational videos, webinars, and video sales letters
- Researching webinars, lectures, demos, and conference talks
- Turning recorded presentations into reviewable slide material
- Extracting visual references from product walkthrough videos
- Creating quick PDF summaries from screen-recorded slide decks
- Preparing source material for qualitative analysis or note-taking
- Preparing slide image batches for AI review tools such as Claude, ChatGPT, or other multimodal assistants

## AI Review Workflow

A common workflow is to extract slides from a long video, download the captured frames as ZIP files, and upload the ZIP volumes to an AI assistant for summarization, comparison, or research notes.

To support this workflow, `DeckSift` keeps ZIP downloads under 24 MB per volume. This makes large slide extraction jobs easier to upload in environments with file-size limits.

Example workflow:

1. Extract slide frames from a webinar, lecture, or product demo video.
2. Download the WebP ZIP output.
3. Upload one ZIP volume at a time to an AI assistant.
4. Ask for a summary, comparison table, research notes, or follow-up questions.

See the detailed [AI-assisted research workflow guide](docs/ai-workflow.md) for example prompts, privacy notes, and practical limitations.

For a workflow tailored to web marketing, client evidence, and funnel design, see the [funnel and creative research guide](docs/funnel-research-workflow.md).

An anonymized [target-user field study](docs/field-study-web-marketing.md) documents reported use within a 10-person web marketing team. The team combines extracted frames with transcripts when researching competitor advertising videos and planning original video production. The study also records requests for faster processing and an installable web-app experience.

Release details: [DeckSift v0.3.0 notes](docs/release-v0.3.0.md).

## Privacy

The tool processes videos locally in the user's browser. It does not intentionally upload video files to a server. Generated images, ZIP volumes, and PDFs remain under user control unless the user chooses to share them with another service.

See [Privacy and Data Handling](docs/privacy.md) for details about local processing, generated outputs, third-party uploads, and device considerations.

## Implementation Notes

The extraction approach combines visual frame sampling, grayscale signatures, change thresholds, sensitivity controls, optional exclusion zones, and an opt-in color-aware caption comparison. See [Extraction Algorithm And Tradeoffs](docs/algorithm.md) for details.

## Validation

The v0.3.0 presenter mode was tuned with a 23-minute presenter/interview test video and manual frame review. The initial detector produced 683 captures. The refined mode produced 594 captures, a reduction of about 13%, while retaining distinct caption changes during the reviewed sections. This is one real-world regression case rather than a universal accuracy claim; additional public benchmark cases are tracked in [issue #5](https://github.com/lazy3128-design/decksift/issues/5).

## How To Use

1. Open the live demo.
2. Drag and drop one or more MP4/video files.
3. Choose the slide-focused or presenter-and-caption detection mode.
4. Optionally mark areas to ignore, such as a presenter camera overlay.
5. Start analysis.
6. Download extracted images as ZIP, generate a PDF, or export timestamp metadata as CSV.

## Current Limitations

- Detection is based on visual frame differences, not semantic slide understanding.
- Highly animated slides may produce extra captures.
- Subtle slide changes may require higher sensitivity.
- Very long videos can take time because processing happens in the browser.
- Browser memory limits may affect very large files.
- ZIP volume size is controlled by an approximate size limit, so real-world file size can vary slightly by browser and image format.

## Roadmap

- Improve slide change detection for animated decks
- Expand duplicate-detection benchmarks across more video layouts
- Align imported transcripts with captured frames and timestamps
- Add structured funnel and DRM sequence analysis with evidence links
- Export comparison-ready research reports for client work
- Add optional OCR-assisted slide naming
- Add a batch summary workflow for research notes
- Add test videos and benchmark examples
- Improve accessibility and keyboard navigation
- Package the tool as an installable PWA

## Maintenance

The complete browser app is maintained in [`index.html`](index.html). The project tracks release history in [CHANGELOG.md](CHANGELOG.md) and uses GitHub issues for planned improvements, bug reports, and research workflow ideas.

## Maintainer

Maintained by [lazy3128-design](https://github.com/lazy3128-design).

## License

MIT License.
