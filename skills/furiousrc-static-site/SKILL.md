---
name: furiousrc-static-site
description: Use when working on the Furious RC static website project, especially when converting provided screenshots and image assets into matching HTML/CSS pages for Homepage, Packages, Our Cars, or Contact Us.
---

# Furious RC Static Site

## Project Goal

Create a fully working static website from provided page screenshots and image/logo assets. Match the screenshots as closely as practical using plain HTML and CSS.

## Site Scope

The site has four pages:

- Homepage
- Packages
- Our Cars
- Contact Us

Use one HTML file per page. The current homepage file is `index.html`; shared styles are in `styles.css`.

## Asset Conventions

- Image assets live in `images/`.
- Screenshot references live in `screenshots/`, grouped by page subfolder when provided.
- Image names follow the pattern `Page_Section_Number.jpg` or page banner naming such as `Homepage-Welcome-banner.jpg`.
- Live-page images were compressed in place for deployment performance. Keep newly added website images close to or under `100KB` where practical, accepting slight quality reduction when needed.
- The homepage video has optimized variants in `videos/`; use the compressed under-8MB variant for the live homepage unless the user asks for a higher-quality file.
- Existing important assets:
  - `images/FuriousRCLogo.jpg`
  - `images/Homepage-Welcome-banner.jpg`
  - `images/Homepage_SchoolIncursion_01.jpg`
  - `images/Homepage_SchoolIncursion_02.jpg`
  - `images/Homepage_CouncilEvent_01.jpg`
  - `images/Homepage_BirthdayParty_01.jpg`
  - `images/Packages-Welcome-banner.jpg`
  - `images/Packages_Soccer_Arena_01.jpg`
  - `images/Ourcars-Welcome-banner.jpg`
  - `images/Contactus-Welcome-banner.jpg`

## Workflow

1. Inspect the relevant screenshots before coding.
2. Ask questions if screenshots, text content, image assets, or page filenames are unclear.
3. Preserve the existing shared header/footer approach unless the screenshots for a page show otherwise.
4. Build static HTML/CSS only unless the user explicitly asks for JavaScript.
5. Verify that all linked local image/CSS files exist after edits.
6. Double check the completed page layout at desktop and mobile widths before finalizing. Mobile must be readable, navigable, and free of obvious overflow/cropping issues.

## Homepage Notes

Homepage sections:

- Header with logo on the left and navigation on the right.
- Welcome hero video with centered white text.
- `Perfect for School Incursions` section.
- `Perfect for Council Events/Festivals` section.
- `Perfect for Birthday Party` section.
- Footer with logo, footer nav, mobile/email/location, privacy/public liability links, copyright, and social icons.

Homepage implementation details:

- Header is positioned over the hero video and currently uses a solid dark grey background to cover a logo area in the top-right of the video.
- Homepage header-specific styling currently uses a taller `92px` header, `72px` logo, and larger homepage nav text; preserve this unless the user asks to change the homepage reference look.
- Hero uses `videos/Welcome_video_01_under8mb.mp4` with `autoplay`, `muted`, `loop`, and `playsinline`.
- Video history:
  - `videos/Welcome_video.mp4` is the original 59.8-second source, about 15.5MB.
  - `videos/Welcome_video_01.mp4` is the first 40-second trimmed version, about 11.6MB.
  - `videos/Welcome_video_01_under8mb.mp4` is the live compressed 40-second H.264 version, 1280x720, about 6.4MB.
- `images/Homepage-Welcome-banner.jpg` is retained as the video poster/fallback image.
- Homepage hero media uses top-centered cover framing; keep `.hero-copy` layered above it with `z-index` so the punch line and subline remain visible.
- Section content uses a two-column layout: large heading left, body copy and Learn More button right.
- Section images are wide below their text blocks.
- School Incursions currently has three wide images: `Homepage_SchoolIncursion_01.jpg`, `Homepage_SchoolIncursion_02.jpg`, and `Homepage_SchoolIncursion_03.jpg`.
- Footer background is dark grey.
- Footer social icons are currently inline SVG placeholders because no separate Facebook/Instagram image assets were provided.
- Homepage Learn More routing:
  - School Incursions links to `packages.html#furious-rc-soccer-game`.
  - Council Events/Festivals links to `packages.html#mega-race`.
  - Birthday Party links to `packages.html#mega-race`.

## Packages Notes

Packages page file: `packages.html`.

Packages sections:

- Grey header with logo/nav and active `Packages` link.
- Centered `PACKAGES` title.
- Centered package welcome image using `images/Packages-Welcome-banner.jpg`.
- `Furious RC Bigfoot RC Soccer Arena` package details.
- `2 hour Furious RC Mega Race` package details.
- Homepage footer reused at the bottom.

Packages implementation details:

- Main package content uses Helvetica at 14px.
- The footer keeps Homepage styling, so Helvetica is scoped to `.packages-main`, not the whole page.
- Package content is narrow and centered, matching the screenshots.
- Booking buttons link to `contact-us.html`.
- The live first package in `packages.html` is a 90-minute school STEM incursion called `Furious RC Bigfoot RC Soccer Arena`.
- The Bigfoot RC Soccer Arena package introduces children to RC car driving through an RC basics crash course followed by a competitive 3 vs 3 RC soccer game.
- Bigfoot RC Soccer Arena package details currently include:
  - Duration: 90 minutes.
  - Soccer Court Size: 8m x 5m fenced court.
  - Ideal Group Size: 6-15 students.
  - Recommended Age: 6-12 years old.
  - Staffing: 1 instructor/commentator + 1 assistant.
  - Pricing: $500.
- Bigfoot RC Soccer Arena `Program Format` should mention interactive RC training, anatomy of an electric RC car, basic control technique, driving etiquette, safety rules, 3 vs 3 soccer, match halves/breaks, music/commentary/scoring/timing, and regular battery changes.
- Bigfoot RC Soccer Arena `What We Provide` currently lists 6 beginner-friendly detailed Bigfoot monster trucks, an 8m x 5m fenced soccer court, 30 x 3000mAh 2S LiPo batteries, full-size soccer ball, scoreboard/timer, speaker/whistle, 2 soccer goals, setup table, and other event equipment.
- `images/Packages_Soccer_Arena_01.jpg`, `images/Packages_Soccer_Arena_02.jpg`, and `images/Packages_Soccer_Arena_03.jpg` are inserted before the Bigfoot RC Soccer Arena booking button.
- `.package-section-image` in `styles.css` makes inserted package body images responsive inside the narrow package content column.
- Bookmark IDs:
  - Bigfoot RC Soccer Arena section: `id="furious-rc-soccer-game"`.
  - Mega Race section: `id="mega-race"`.
- `.package-detail` uses `scroll-margin-top` so anchored jumps land cleanly.

## Our Cars Notes

Our Cars page file: `our-cars.html`.

Our Cars sections:

- Grey header with logo/nav and active `Our Cars` link.
- Centered `OUR CARS` title.
- Centered welcome image using `images/Ourcars-Welcome-banner.jpg`.
- Car sections for:
  - `MJX 10303/10304 1/10 Rally Car`
  - `MJX 14209 Desert Truck`
  - `Arrma Fury 223S Short Course Truck`
- Homepage footer reused at the bottom.

Our Cars implementation details:

- Each car section has an ornamental divider, centered car title, two-column text/spec layout, then a horizontal photo slider.
- Current sliders use real car images from model-specific folders under `images/OurCars/`.
- MJX 10303/10304 images live under `images/OurCars/MJX10303_10304/`.
- MJX 14209 images live under `images/OurCars/MJX14209/`.
- Arrma Fury 223S images live under `images/OurCars/ArrmaFury223S/`.
- Slider arrows scroll the horizontal track.
- Clicking a slider photo opens a front-facing enlarged lightbox.
- The lightbox has one-time support for both image enlargement and YouTube iframe playback.
- YouTube video thumbnails use `.slide-photo.video-slide` buttons with `data-youtube="https://www.youtube.com/embed/YOUTUBE_ID"` and a local thumbnail image.
- For MJX 10303/10304 videos, use thumbnails from `images/OurCars/MJX10303_10304/video_thumbnails/`.
- For MJX 14209 videos, use thumbnails from `images/OurCars/MJX14209/video_thumbnail/`.
- When the user adds a new model video thumbnail and provides a YouTube URL, find the next thumbnail file in that model's thumbnail folder, convert the YouTube URL to `https://www.youtube.com/embed/YOUTUBE_ID`, and add a `.slide-photo.video-slide` entry to the matching car slider.
- Put featured video thumbnails first in their slider when requested; if several videos are already featured, add new featured video thumbnails after the existing video slides and before regular photos unless the user specifies a different order.
- `.video-slide` uses a CSS play indicator: a small centered white triangle over a dark circular backdrop. Keep it subtle; the current size is intentionally about 30% of the earlier oversized version.
- Lightbox closes by close button, outside click, or Escape key.
- Closing the lightbox clears the YouTube iframe `src` so video playback stops.
- Mobile layout stacks the car text/spec columns and keeps sliders horizontally scrollable.

## Contact Us Notes

Contact Us page file: `contact-us.html`.

Contact Us sections:

- Header/nav over the contact banner image.
- Banner image uses `images/Contactus-Welcome-banner.jpg`.
- Centered contact form card.
- Homepage footer reused at the bottom.

Contact Us implementation details:

- Form fields: First name, Last name, Email, Phone, Message.
- First name and Email are required.
- The form currently uses FormSubmit so submissions from GitHub Pages are emailed to Gmail:
  - `action="https://formsubmit.co/aaron.zhang.aus@gmail.com"`
  - `method="POST"`
  - Hidden `_subject`: `New Furious RC Contact Form Submission`
  - Hidden `_template`: `table`
  - Hidden `_next`: `https://AaronZhangAus.github.io/FuriousRC_Website/thank-you.html`
- After the Namecheap custom domain is live, update `_next` to the final custom-domain thank-you URL.
- `thank-you.html` is the FormSubmit success redirect page.
- On mobile, form rows stack into one column.

## Shared Typography And Footer

- The shared base font is Helvetica with Arial fallback.
- The shared base text size is 14px.
- Main body text should remain Helvetica 14px unless the user requests otherwise.
- Title/display text uses the shared `--display-font` stack in `styles.css`; currently this imports and uses `Bebas Neue` with `"Arial Narrow", Impact, sans-serif` fallbacks.
- Apply display font only to titles/headings, not main body copy.
- The homepage hero punch line is the primary visual headline: keep it in two fixed lines using `.hero-title-line`, with `Bring the Excitement of RC Racing` on line 1 and `Directly to You` on line 2.
- The homepage hero punch line currently uses `font-size: clamp(28px, 4.1vw, 42px)`, `line-height: 1.05`, and a stronger text shadow so it stays in the sky area above the cars.
- The homepage hero supporting line (`We take care of the gears, You take care of the speed`) should stay larger than body copy and close to the punch line.
- Main page titles such as `PACKAGES`, `OUR CARS`, and `CONTACT US` should match the homepage hero headline scale for consistency.
- Secondary page section titles such as package titles and car titles should use the same display font with a slightly smaller scale than main page titles.
- Footer is reused across all pages.
- Current footer layout is three columns:
  - Column 1: page link list, one page link per line.
  - Column 2: Furious RC logo first, then mobile, email, and address.
  - Column 3: social media icons first, then `Privacy Policy`, `Public Liability`, and copyright text.
- Logo stays in the middle column, social media icons stay at the top of the third column.
- Footer columns stack safely on mobile and must not overlap.

## Documentation Notes

- Project documentation lives in `README.md`.
- README documents page structure, local preview, image conventions, slider updates, YouTube video slide setup, homepage video hero behavior, contact form behavior, backend email requirements, server transfer/upload steps, and pre-publish checks.
- The README server transfer section should distinguish public upload files (`*.html`, `styles.css`, `images/`, `videos/`) from local-only materials (`.idea/`, `venv/`, `screenshots/`, `skills/`, `main.py`, `pyproject.toml`).
- The one-time complicated YouTube lightbox support is already implemented; future README/user guidance should focus on the simple three-step video insertion process.
- Latest performance work:
  - Homepage now points to `videos/Welcome_video_01_under8mb.mp4`.
  - Live-page images referenced by `index.html`, `packages.html`, `our-cars.html`, and `contact-us.html` were compressed in place to about `100KB` or less each.
  - Keep `Packages_old.html`, `.idea/`, `venv/`, `screenshots/`, and `skills/` off the public server.
  - Unused large files such as `images/boxofSCRAPS.jpg` and unreferenced car photos should not be uploaded unless explicitly needed.

## Current Link Targets

Navigation currently uses:

- `index.html`
- `packages.html`
- `our-cars.html`
- `contact-us.html`

When creating later pages, use those filenames unless the user requests different names.

## Style Requirements

- Match screenshots over generic design preferences.
- Keep CSS responsive for desktop and mobile; mobile verification is required for every page.
- Prefer concise, readable CSS using shared classes for repeated page structure.
- Use ASCII-safe source text where practical.
- Do not overwrite existing user changes without checking first.
