# millersrepairco

Landing page for Miller's Repair Co. (millersrepairco.com), built for Meta and Google ad traffic.
Everything is in `index.html`. GitHub Pages publishes it when you push to `main`.

All settings live in the `CONFIG` block near the bottom of `index.html`.

## 1. Connect the form (do this first)

Until this is set, people who fill out the form have to send it themselves from their email app. Many won't.

1. Make a free account at https://formspree.io and create a form.
2. Copy its URL (looks like `https://formspree.io/f/abcdwxyz`).
3. Paste it into `formEndpoint: ""` in `CONFIG`.

Each request arrives by email. It includes the vehicle, the problems the customer tapped, the repair they picked,
and the ad it came from (`utm_*`, `gclid`, `fbclid`).

## 2. Add the explainer video

Until a video is set, the page shows an animated gauge in its place.

**Option A: video file (best for conversions; no YouTube logo or suggested videos)**
1. Export a landscape (16:9) MP4 at 720p or 1080p. Keep it under about 20 MB and 60–90 seconds.
2. Add it to the repo as `video/explainer.mp4`. A cover image as `video/poster.jpg` is optional but recommended.
3. In `CONFIG.video` set `mp4: "video/explainer.mp4"` and `poster: "video/poster.jpg"`.

**Option B: YouTube**
Upload the video, then set `youtubeId` to the part after `watch?v=` in its link.

Square or vertical video? Set `ratio` to `"1/1"` or `"4/5"`.

## 3. Tracking

- **Meta Pixel** (already installed): `PageView`, `ViewContent` when someone taps a Start button,
  `Lead` when a request is submitted (with value 99 or 139), plus custom `RequestStep1` and `VideoPlay`.
  Optimize your Meta campaigns for **Lead**.
- **Google Ads**: create a "Submit lead form" conversion action, choose *Install the tag yourself*,
  and copy the `AW-…` ID and the conversion label into `CONFIG.googleAds`.

## Ideas that will raise conversions further

- Add 3 real customer reviews. A section for them is ready but commented out (search for `REVIEWS` in `index.html`).
- Add before/after photos of a repaired cluster.
- Add a privacy policy page. Ad platforms expect one when a page collects contact info and uses tracking pixels.
