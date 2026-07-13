# AI-Assisted Research Workflow

This guide describes a practical workflow for turning slide-based videos into materials that can be reviewed with multimodal AI assistants.

## Goal

Convert a long webinar, lecture, product demo, or research video into smaller batches of slide images that are easier to summarize, compare, and analyze.

## Workflow

1. Open the [DeckSift live demo](https://lazy3128-design.github.io/decksift/).
2. Select or drag and drop one or more video files.
3. Choose slide-focused mode for decks and screen recordings, or presenter-and-caption mode for talking-head and interview videos.
4. Optionally mark moving regions to exclude, such as presenter cameras, captions, clocks, or overlays.
5. Adjust extraction sensitivity when too many or too few slides are detected.
6. Start analysis and review the generated slide previews. Use the arrow keys to move through enlarged images quickly.
7. Save individual frames when needed, or download the full result as WebP/PNG ZIP volumes or a PDF.
8. Download the timestamp CSV when source-video references are useful.
9. Upload one ZIP volume at a time to a multimodal AI assistant.
10. Ask the assistant to summarize, compare, classify, or extract research notes from the slides.

## Why WebP And Split ZIP Volumes

WebP usually provides readable slide images at a smaller file size than PNG. This makes it useful when many slides need to be reviewed together.

Large output sets are split into upload-friendly ZIP volumes. The current implementation targets approximately 24 MB per volume so extracted slides are easier to upload in environments with file-size limits.

## Example Prompts

### Summarize A Webinar

```text
Review these extracted webinar slides. Summarize the main argument, supporting evidence, and recommended actions. Note any claims that require further verification.
```

### Compare Product Demos

```text
Create a comparison table from these product demo slides. Compare target users, key features, positioning, pricing claims, and notable limitations.
```

### Create Research Notes

```text
Turn these slides into structured research notes. Preserve important numbers, named concepts, frameworks, and open questions. Separate facts shown on the slides from your own inferences.
```

## Privacy Notes

The original video is processed locally in the browser by DeckSift. However, uploading extracted images or ZIP files to an AI service is a separate action. Before uploading, confirm that you have permission to share the extracted material and review the destination service's data-handling policies.

Do not upload confidential, private, copyrighted, or personal material unless you are authorized to do so.

## Known Limitations

- Scene-change detection is visual and may capture extra frames from animations.
- Subtle changes may be missed depending on sensitivity settings.
- ZIP volume size is approximate and may vary slightly by browser and output format.
- AI-generated summaries should be reviewed against the original material.
