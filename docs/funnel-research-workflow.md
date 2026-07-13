# Funnel And Creative Research Workflow

This guide describes how web marketers and funnel designers can use DeckSift to study the visual and messaging sequence of campaign, webinar, educational, and video sales letter content.

## Research Question

DeckSift helps answer a question that a transcript alone cannot:

> What design appeared, where did it appear, and what was being communicated at that moment?

The current release extracts reviewable frames and timestamp metadata. Transcription and funnel-structure analysis are performed with separate tools today; tighter transcript alignment and optional structured analysis are planned.

## Workflow

1. Obtain a video that you are authorized to download and analyze.
2. Run it through DeckSift using slide-focused mode or presenter-and-caption mode.
3. Review the extracted frames and remove any captures that do not support the research question.
4. Export WebP/PNG ZIP volumes and the timestamp CSV.
5. Create a transcript with timestamps using an appropriate transcription service.
6. Align the transcript with DeckSift frames using the video timestamps.
7. Analyze the sequence as evidence: visual design, spoken/written message, intended funnel role, and source timestamp.
8. Use the resulting table in a client research report or as a reference when planning an original educational video.

## Suggested Evidence Table

| Timestamp | Visual design | Message or claim | Funnel role | Evidence and confidence |
| --- | --- | --- | --- | --- |
| 00:00 | Describe the frame | Quote or summarize the message | Hook, problem, proof, offer, CTA, or other | Filename and whether the classification is explicit or inferred |

Keeping the filename and timestamp beside every conclusion makes it easier to return to the original source and distinguish observation from interpretation.

## Example AI Prompt

```text
Analyze these timestamped frames together with the transcript.

Create a table with:
- timestamp and image filename
- visual layout and notable design choices
- message or claim being communicated
- likely role in the funnel
- supporting evidence from the frame or transcript
- confidence level

Then outline the apparent sequence using categories such as hook, problem,
agitation, mechanism, proof, offer, and call to action. Do not force every
category to appear. Clearly label interpretations that are not explicit in
the source material.
```

## Client And Production Uses

- Support recommendations with timestamped visual evidence instead of memory alone.
- Compare how multiple videos introduce problems, mechanisms, proof, and offers.
- Identify recurring slide patterns, pacing, and transitions between message stages.
- Build an evidence base for planning original webinars, courses, and educational videos.
- Pair visual evidence with transcripts so multimodal AI review does not lose layout or sequence.

## Responsible Use

Only collect, download, share, and analyze material when you have the necessary rights or permission. Follow the terms of the source platform. Avoid presenting inferred strategy as a confirmed fact, and preserve timestamps so client-facing conclusions can be checked against the source.
