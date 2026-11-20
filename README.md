# exam-photo-tools

Free tools for Chinese exam registration photos. Built for Gaokao, CET, civil service and other exams where the upload system rejects your photo for wrong pixels or KB size.

## What it does now

- **Photo compressor (Tool 1, working prototype in `index.html`):** enter the required width, height and KB range, upload a photo, it center-crops to the right ratio, resizes to the exact pixels, then binary-searches JPEG quality (0.02–1) to fit the KB range. All processing is client-side, no upload, no server.
- **Self-check before download:** checks pixels, size, whether the original was upscaled, and tells you exactly what failed and what to fix.
- **Background changer (Tool 2, working prototype in `background-changer.html`):** upload a photo, pick white / blue / red, it center-crops to the target pixels and draws it on the new background, downloads as JPG.
- **Rejection checker (Tool 3, working prototype in `rejection-checker.html`):** upload a photo, enter the required pixels and KB range, it checks format, pixels, size, ratio and upscaling, and lists pass / fail with what to fix.

## Next tools (roadmap)

- Tool 4: Batch processor for teachers — upload 100 photos, compress all, rename by student ID, download as zip.

## Tech stack

- Plain HTML / CSS / JavaScript, no build step, no server.
- Canvas + OffscreenCanvas in a Web Worker for resizing.
- `pica` for high-quality resizing, `JSZip` with streaming for batch zips.
- `canvas.toBlob(canvas, "image/jpeg", quality)` for compression.

## How the Bot will work on it

- Every morning: check official exam photo specs, fix bugs, work on the next tool, test it.
- Report every day at 9am via Poke, weekly summary on Sunday.
- Owner reviews every evening and gives the next task.

## Run it

Open `index.html` in a browser. No install, no upload.
