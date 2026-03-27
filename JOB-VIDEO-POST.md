# Job Video Post App

## What It Does
Standalone PWA for fence services. Driver records a job site video on iPhone → auto-posts to Telegram → AI generates a branded social media caption → creates a branded thumbnail → email draft for owner approval before posting to Instagram/Facebook/GMB.

## Live URL
https://kawiride027.github.io/job-video-post/

## GitHub Repo
https://github.com/kawiride027/job-video-post

## Tech Stack
- Single HTML file (`index.html`), vanilla JS, no dependencies
- Telegram Bot API for video posting
- Claude/OpenAI API for AI caption generation
- Canvas API for branded thumbnail generation
- localStorage for settings
- PWA (installable on iPhone home screen)

## Telegram Setup
- **Bot:** @Fencevideobot (created via @BotFather)
- **Group:** "Jobsite Videos"
- **Chat ID:** -5288930917
- **Bot Token:** REVOKE AND REPLACE — the original token was exposed. Send `/revoke` to @BotFather and update in app settings.

## Features
1. **Video capture** — opens iPhone camera, 60 sec or less, under 50MB
2. **Job type selector** — Fence Rental, Installation, Removal, Repair, Site Inspection, Other
3. **Optional details** — address and notes fields
4. **Auto-post to Telegram** — video + caption with job details, upload progress bar
5. **AI caption generation** — production-ready social media post with hashtags and CTA
6. **Branded thumbnail** — 1080x1080 image with video frame, business name, job type badge, caption overlay, hashtags
7. **Copy/Share/Email** — copy caption, share thumbnail, email draft for approval
8. **50MB file size guard** — warns and blocks oversized videos
9. **Settings** — Telegram token, chat ID, AI API key, owner email, business name

## How to Update the Live App
1. Go to github.com/kawiride027/job-video-post → open `index.html` → pencil icon
2. Select all, delete
3. Paste updated code
4. Commit changes
5. GitHub Pages auto-deploys in ~1 min

## TODO / Future Features
- [ ] Revoke exposed Telegram bot token and update in app settings
- [ ] Auto-post to Instagram (requires Meta Business API + backend or Zapier)
- [ ] Auto-post to Facebook (requires Meta Graph API + backend or Zapier)
- [ ] Auto-post to Google My Business (requires Google Business Profile API)
- [ ] Email approval workflow with clickable approve/reject buttons (requires backend)
- [ ] Video compression before upload (FFmpeg.wasm or cloud service)
- [ ] Multiple driver support with driver name tagging
- [ ] Job history log (list of past posts with status)
