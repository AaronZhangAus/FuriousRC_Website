# Furious RC Static Website

This project is a static HTML/CSS website for Furious RC. It was built from provided screenshots and local image assets.

The website currently uses plain HTML, CSS, and a small amount of JavaScript for the Our Cars photo sliders and image lightbox.

## Website Pages

The site has four pages:

- `index.html` - Homepage
- `packages.html` - Packages
- `our-cars.html` - Our Cars
- `contact-us.html` - Contact Us
- `thank-you.html` - Contact form success page

All pages share:

- The same navigation structure
- The same footer layout
- The same `styles.css` stylesheet
- The same image folder: `images/`

## Project Structure

```text
FuriousRC_Website/
|-- index.html
|-- packages.html
|-- our-cars.html
|-- contact-us.html
|-- thank-you.html
|-- styles.css
|-- README.md
|-- videos/
|   |-- Welcome_video.mp4
|   |-- Welcome_video_01.mp4
|   `-- Welcome_video_01_under8mb.mp4
|-- images/
|   |-- boxofSCRAPS.jpg
|   |-- Contactus-Welcome-banner.jpg
|   |-- FuriousRCLogo.jpg
|   |-- Homepage-Welcome-banner.jpg
|   |-- Homepage_BirthdayParty_01.jpg
|   |-- Homepage_BirthdayParty_02.jpg
|   |-- Homepage_CouncilEvent_01.jpg
|   |-- Homepage_CouncilEvent_02.jpg
|   |-- Homepage_SchoolIncursion_01.jpg
|   |-- Homepage_SchoolIncursion_02.jpg
|   |-- Homepage_SchoolIncursion_03.jpg
|   |-- Ourcars-Welcome-banner.jpg
|   |-- Packages-Welcome-banner.jpg
|   `-- OurCars/
|       |-- ArrmaFury223S/
|       |   |-- 0.jpg
|       |   |-- 1.jpg
|       |   |-- 2.jpg
|       |   |-- 3.jpg
|       |   |-- 4.jpg
|       |   |-- 5.jpg
|       |   |-- 6.jpg
|       |   |-- 7.jpg
|       |   `-- video_thumbnails/
|       |       `-- 1.jpg
|       |-- MJX10303_10304/
|       |   |-- 0.jpg
|       |   |-- 1.jpg
|       |   |-- 2.jpg
|       |   |-- 3.jpg
|       |   |-- 4.jpg
|       |   |-- 5.jpg
|       |   `-- video_thumbnails/
|       |       |-- 1.jpg
|       |       |-- 2.jpg
|       |       `-- 3.jpg
|       `-- MJX14209/
|           |-- 1.jpg
|           |-- 2.jpg
|           |-- 3.jpg
|           |-- 4.jpg
|           |-- 5.jpg
|           `-- video_thumbnail/
|               |-- 1.jpg
|               `-- 2.jpg
|-- screenshots/
|   |-- Homepage/
|   |-- Packages/
|   |-- Ourcars/
|   `-- Contact Us/
`-- skills/
    `-- furiousrc-static-site/
        `-- SKILL.md
```

## Page Overview

### Homepage

File: `index.html`

Main sections:

- Header with logo and navigation
- Welcome hero video
- School Incursions section
- Council Events/Festivals section
- Birthday Party section
- Shared footer

Important links:

- School Incursions `Learn More` links to `packages.html#furious-rc-soccer-game`
- Council Events/Festivals `Learn More` links to `packages.html#mega-race`
- Birthday Party `Learn More` links to `packages.html#mega-race`

Homepage video:

- The homepage hero uses `videos/Welcome_video_01_under8mb.mp4`.
- The video autoplays, loops, stays muted, and plays inline on mobile.
- `images/Homepage-Welcome-banner.jpg` is used as the poster/fallback image.
- The homepage header uses a solid dark grey background to cover a logo area in the top-right of the video.

### Packages

File: `packages.html`

Main sections:

- Header
- Packages welcome image
- Bigfoot RC Soccer Arena package
- Mega Race package
- Shared footer

Bookmark sections:

```html
id="furious-rc-soccer-game"
id="mega-race"
```

These IDs allow links from the homepage to jump directly to the correct package section.

### Our Cars

File: `our-cars.html`

Main sections:

- Header
- Our Cars welcome image
- MJX 10303/10304 1/10 Rally Car section
- MJX 14209 Desert Truck section
- Arrma Fury 223S Short Course Truck section
- Shared footer

Each car section includes:

- Car title
- Description text
- Specification list
- Horizontal photo slider
- Click-to-enlarge lightbox

### Contact Us

File: `contact-us.html`

Main sections:

- Header over the contact banner
- Contact form
- Shared footer

Current form behavior:

```html
action="https://formspree.io/f/mqevkzey"
method="POST"
```

The form posts to the active Formspree endpoint `https://formspree.io/f/mqevkzey`.

After a successful submission, the form redirects to:

```text
thank-you.html
```

Important: create the form in Formspree first, set the recipient email to `aaron.zhang.aus@gmail.com`, then copy the endpoint into `contact-us.html`.

## Styling

Main stylesheet:

```text
styles.css
```

Important styling rules:

- Main body font is Helvetica, 14px.
- Title/display text uses a separate display font stack.
- Shared footer CSS applies to all pages.
- Mobile breakpoints are included for smaller screens.

When editing styles, prefer updating shared CSS classes rather than duplicating page-specific styles.

## Running The Website Locally

The site can be opened directly in a browser, but testing through a local server is more reliable.

From the project folder, run:

```powershell
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

Useful page URLs:

```text
http://localhost:8000/index.html
http://localhost:8000/packages.html
http://localhost:8000/our-cars.html
http://localhost:8000/contact-us.html
http://localhost:8000/thank-you.html
```

## Updating Images

All website images are stored in:

```text
images/
```

Recommended naming convention:

```text
Page_Section_Number.jpg
```

Examples:

```text
Homepage_SchoolIncursion_01.jpg
Ourcars_MJX10303_01.jpg
Ourcars_MJX10303_02.jpg
Ourcars_MJX14209_01.jpg
Ourcars_ArrmaFury223s_01.jpg
```

After adding new images, update the relevant HTML file to point to the new filenames.

## Updating The Our Cars Photo Sliders

The Our Cars sliders are in:

```text
our-cars.html
```

Each slider uses this structure:

```html
<div class="photo-slider" data-slider>
  <button class="slider-arrow slider-prev" type="button" data-direction="-1">&lsaquo;</button>
  <div class="slider-track">
    <button class="slide-photo" type="button">
      <img src="images/example-01.jpg" alt="Description of image 1">
    </button>
    <button class="slide-photo" type="button">
      <img src="images/example-02.jpg" alt="Description of image 2">
    </button>
  </div>
  <button class="slider-arrow slider-next" type="button" data-direction="1">&rsaquo;</button>
</div>
```

### Step 1: Add The New Images

Add the new car photos to:

```text
images/
```

Use clear filenames. For example:

```text
Ourcars_MJX10303_01.jpg
Ourcars_MJX10303_02.jpg
Ourcars_MJX10303_03.jpg
```

### Step 2: Find The Correct Car Section

Open:

```text
our-cars.html
```

Find the car title you want to update:

```html
<h2 id="mjx-10303-title">MJX 10303/10304 1/10 Rally Car</h2>
```

Then find the `<div class="photo-slider" data-slider>` immediately below that car's text.

### Step 3: Replace The Demo Image Paths

Replace demo image paths like this:

```html
<img src="images/Homepage_SchoolIncursion_01.jpg" alt="Demo RC car photo 1">
```

With real car image paths:

```html
<img src="images/Ourcars_MJX10303_01.jpg" alt="MJX 10303 rally car front view">
```

### Step 4: Add Or Remove Slider Photos

To add another photo, add another button inside `.slider-track`:

```html
<button class="slide-photo" type="button">
  <img src="images/Ourcars_MJX10303_04.jpg" alt="MJX 10303 rally car side view">
</button>
```

To remove a photo, delete the whole block:

```html
<button class="slide-photo" type="button">
  <img src="images/old-image.jpg" alt="Old image">
</button>
```

### Step 5: Keep Alt Text Useful

Always update the `alt` text. Good alt text helps accessibility and search engines.

Good:

```html
alt="MJX 10303 rally car on indoor racing track"
```

Poor:

```html
alt="image"
```

### Step 6: Test Desktop And Mobile

After updating slider images, test:

- Desktop browser width
- Mobile width around 375px to 430px
- Slider arrows
- Horizontal swipe/scroll
- Click-to-enlarge lightbox
- Escape key closes the lightbox
- Clicking outside the enlarged image closes the lightbox

## How The Slider Works

The slider behavior is handled by JavaScript at the bottom of:

```text
our-cars.html
```

It does three things:

- Finds each `.photo-slider`
- Scrolls `.slider-track` when arrow buttons are clicked
- Opens the clicked image in the lightbox

The lightbox HTML is also in `our-cars.html`:

```html
<div class="lightbox" id="car-lightbox" hidden>
  <button class="lightbox-close" type="button" aria-label="Close enlarged photo">&times;</button>
  <img src="" alt="">
</div>
```

Normally you only need to update image paths inside each `.slider-track`.

## Adding A YouTube Video To A Photo Slider

The website already supports YouTube videos in the Our Cars slider popup. You do not need to change the JavaScript or CSS.

To add a YouTube video, only do these steps.

### Step 1: Add A Thumbnail Image

Add a thumbnail image to:

```text
images/
```

Example filename:

```text
Ourcars_MJX10303_VideoThumb_01.jpg
```

### Step 2: Get The YouTube Video ID

For this YouTube URL:

```text
https://www.youtube.com/watch?v=abc123XYZ
```

The video ID is:

```text
abc123XYZ
```

### Step 3: Add The Video Slide

Open:

```text
our-cars.html
```

Find the car slider you want to update, then add this inside its `.slider-track`:

```html
<button class="slide-photo video-slide" type="button" data-youtube="https://www.youtube.com/embed/abc123XYZ">
  <img src="images/Ourcars_MJX10303_VideoThumb_01.jpg" alt="Watch MJX 10303 rally car video">
</button>
```

Replace:

- `abc123XYZ` with the real YouTube video ID.
- `Ourcars_MJX10303_VideoThumb_01.jpg` with your thumbnail image filename.
- The `alt` text with a useful video description.

That is all. The existing lightbox will open the video in a popup and stop playback when the popup closes.

### Quick Example

If the YouTube video is:

```text
https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

And the thumbnail is:

```text
images/Ourcars_ArrmaFury_VideoThumb_01.jpg
```

Add this slide:

```html
<button class="slide-photo video-slide" type="button" data-youtube="https://www.youtube.com/embed/dQw4w9WgXcQ">
  <img src="images/Ourcars_ArrmaFury_VideoThumb_01.jpg" alt="Watch Arrma Fury short course truck video">
</button>
```

### Testing Checklist

After adding a video slide, check:

- The thumbnail appears in the slider.
- Clicking the thumbnail opens the video popup.
- The close button closes the popup.
- The video stops after closing the popup.
- The slider still works on mobile.
## Contact Form And Email Submission

The current Contact Us form uses Formspree so submissions can be emailed from a static GitHub Pages site.

Current form endpoint:

```html
<form class="contact-form" action="https://formspree.io/f/mqevkzey" method="POST">
```

Current hidden fields:

```html
<input type="hidden" name="_subject" value="New Furious RC Contact Form Submission">
<input type="text" name="_gotcha" tabindex="-1" autocomplete="off" hidden>
```

Field naming notes:

- The visitor email field is named `email` so Formspree can include it in the submission and reply workflow.
- First name, last name, phone, and message are included in the email body.
- First name and email are required.

Live setup process:

1. Create or log in to a Formspree account.
2. Create a new form for the Furious RC website.
3. Set the recipient email to `aaron.zhang.aus@gmail.com`.
4. Confirm the endpoint is `https://formspree.io/f/mqevkzey`.
5. In Formspree, configure the form's redirect or thank-you behavior to send users to `thank-you.html` if desired.
6. Publish the site to GitHub Pages.
7. Open the live Contact Us page.
8. Submit a test message.
9. Confirm the test message arrives in Gmail.

Example final form action:

```html
<form class="contact-form" action="https://formspree.io/f/abcdwxyz" method="POST">
```

After connecting the Namecheap custom domain, update any Formspree dashboard redirect from the GitHub Pages URL to the final custom-domain URL:

```text
https://www.your-domain.com/thank-you.html
```

Limitations:

- Form submissions depend on Formspree as a third-party service.
- The destination Gmail address is managed in Formspree rather than exposed directly in the form action.
- Formspree may show a captcha or confirmation step to reduce spam.
- If more control is needed later, replace Formspree with a backend/serverless endpoint such as Cloudflare Workers, Netlify Functions, Vercel Functions, or another email API integration.

## Deployment Notes

The preferred deployment path is GitHub Pages for hosting and Namecheap for DNS/domain registration.

Current repository:

```text
https://github.com/AaronZhangAus/FuriousRC_Website
```

Recommended live source files:

```text
index.html
packages.html
our-cars.html
contact-us.html
thank-you.html
styles.css
images/
videos/
```

Local-only or unnecessary files should not be published intentionally:

```text
.idea/
venv/
screenshots/
skills/
pyproject.toml
Packages_old.html
README.md
```

Important: GitHub Pages serves files from the selected branch/folder. Anything committed inside the publishing source can be publicly accessible by URL, even if no page links to it.

Static-only GitHub Pages hosting is enough for this website's pages, images, homepage video, Our Cars sliders, YouTube lightbox, and Formspree-powered contact form. No custom backend is required for the current contact form.

Official references:

- GitHub Pages site setup: `https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site`
- GitHub Pages custom domains and DNS records: `https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site`
- Namecheap DNS management: `https://www.namecheap.com/support/knowledgebase/`

## Publishing With GitHub Pages

Use this process after making future website changes.

1. Confirm the homepage still points to the compressed hero video:

```html
<source src="videos/Welcome_video_01_under8mb.mp4" type="video/mp4">
```

2. Confirm `index.html` is in the repository root. GitHub Pages needs this file as the homepage.

3. Commit and push changes to `master`:

```powershell
git status
git add index.html packages.html our-cars.html contact-us.html thank-you.html styles.css images videos
git commit -m "Update website"
git push origin master
```

4. In GitHub, open the repository:

```text
AaronZhangAus/FuriousRC_Website
```

5. Go to:

```text
Settings -> Pages
```

6. Under `Build and deployment`, choose:

```text
Source: Deploy from a branch
Branch: master
Folder: / (root)
```

7. Click `Save`.

8. Wait for GitHub Pages to build and publish the site. The first publish can take a few minutes.

9. Open the default GitHub Pages URL:

```text
https://AaronZhangAus.github.io/FuriousRC_Website/
```

10. Test these pages before connecting the custom domain:

```text
https://AaronZhangAus.github.io/FuriousRC_Website/
https://AaronZhangAus.github.io/FuriousRC_Website/packages.html
https://AaronZhangAus.github.io/FuriousRC_Website/our-cars.html
https://AaronZhangAus.github.io/FuriousRC_Website/contact-us.html
https://AaronZhangAus.github.io/FuriousRC_Website/thank-you.html
```

11. Test the homepage video, homepage images, package images, Our Cars sliders, Our Cars lightbox, YouTube popups, Contact Us form behavior, and thank-you page.

12. Submit the Contact Us form once after the first live deploy and confirm the message arrives in Gmail.

## Connecting A Namecheap Domain

Use these steps when the domain is registered at Namecheap and GitHub Pages is already publishing correctly.

Replace `your-domain.com` with the real domain, for example `furiousrc.com.au` if that is the final domain.

### Step 1: Add The Custom Domain In GitHub

1. In GitHub, open:

```text
Settings -> Pages
```

2. Under `Custom domain`, enter the domain you want visitors to use.

Recommended option:

```text
www.your-domain.com
```

Using `www` as the primary domain is usually the simplest GitHub Pages setup. GitHub can redirect between the apex domain and `www` when both DNS records are configured correctly.

3. Click `Save`.

4. If GitHub creates or updates a `CNAME` file in the repository, pull that change locally before the next edit:

```powershell
git pull origin master
```

The `CNAME` file should contain only the custom domain, for example:

```text
www.your-domain.com
```

### Step 2: Configure Namecheap DNS

1. Log in to Namecheap.
2. Open `Domain List`.
3. Click `Manage` next to the domain.
4. Open the `Advanced DNS` tab.
5. Remove or replace conflicting parking, redirect, or old website records for `@` and `www`.
6. Add these `A Record` entries for the apex domain:

```text
Type: A Record
Host: @
Value: 185.199.108.153
TTL: Automatic

Type: A Record
Host: @
Value: 185.199.109.153
TTL: Automatic

Type: A Record
Host: @
Value: 185.199.110.153
TTL: Automatic

Type: A Record
Host: @
Value: 185.199.111.153
TTL: Automatic
```

7. Add this `CNAME Record` for `www`:

```text
Type: CNAME Record
Host: www
Value: AaronZhangAus.github.io
TTL: Automatic
```

Do not include the repository name in the `www` CNAME value. Use `AaronZhangAus.github.io`, not `AaronZhangAus.github.io/FuriousRC_Website`.

8. Optional IPv6 records can be added later if needed. GitHub Pages supports these `AAAA` values:

```text
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

9. Do not add wildcard DNS records such as `*.your-domain.com`.

### Step 3: Wait And Verify DNS

DNS changes can take minutes, but allow up to 24 hours.

From PowerShell, check the apex domain:

```powershell
Resolve-DnsName your-domain.com -Type A
```

Expected values:

```text
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Check the `www` domain:

```powershell
Resolve-DnsName www.your-domain.com -Type CNAME
```

Expected value:

```text
AaronZhangAus.github.io
```

### Step 4: Enable HTTPS

1. Go back to GitHub:

```text
Settings -> Pages
```

2. Wait until GitHub shows the custom domain as configured.
3. Enable `Enforce HTTPS`.

GitHub may take up to 24 hours before the HTTPS checkbox becomes available after DNS changes.

### Step 5: Final Live-Site Checks

Open:

```text
https://www.your-domain.com/
https://www.your-domain.com/packages.html
https://www.your-domain.com/our-cars.html
https://www.your-domain.com/contact-us.html
https://www.your-domain.com/thank-you.html
```

Also test the apex domain:

```text
https://your-domain.com/
```

Confirm that one domain redirects cleanly to the other and that HTTPS is active.

Test:

- Homepage video loads and plays.
- `styles.css` loads.
- All page navigation links work.
- Homepage `Learn More` links jump to the correct package sections.
- Our Cars slider arrows work.
- Our Cars image lightbox opens and closes.
- Our Cars YouTube popups open and stop playback after closing.
- Contact Us form submits through Formspree.
- Gmail receives the Formspree contact email.
- Formspree thank-you or redirect behavior works as configured in the Formspree dashboard.
- Mobile layout is readable and has no obvious horizontal overflow.

## Future Update Process

For normal content/image changes after GitHub Pages is connected:

1. Edit the local files.
2. Test locally:

```powershell
python -m http.server 8000
```

3. Open:

```text
http://localhost:8000/
```

4. Commit and push:

```powershell
git status
git add .
git commit -m "Update website content"
git push origin master
```

5. Wait for GitHub Pages to redeploy.
6. Hard refresh the live site if old styling or images are cached:

```text
Ctrl + F5
```

7. If an image, video, or stylesheet is missing on the live site, verify filename capitalization. GitHub Pages paths are case-sensitive.

## Important Publishing Notes

- The homepage must stay named `index.html`.
- Keep `styles.css` next to the `.html` files.
- Keep all image paths relative, such as `images/FuriousRCLogo.jpg`.
- Keep all video paths relative, such as `videos/Welcome_video_01_under8mb.mp4`.
- Keep live images compressed where practical. The current referenced images were compressed to about `100KB` or less each.
- Keep using the compressed homepage video unless a higher-quality video is intentionally needed.
- Keep the Contact Us form action pointed at `https://formspree.io/f/mqevkzey` format, using the real Formspree form ID.
- After the Namecheap domain is live, update any Formspree dashboard redirect from the GitHub Pages URL to the final domain.
- Do not commit credentials, API keys, Namecheap login details, or GitHub tokens.
- If replacing Formspree with custom backend email sending later, GitHub Pages alone will not be enough; use serverless/API hosting for the backend endpoint.

## Pre-Publish Checklist

Before publishing changes:

- Check all page links.
- Check all image paths.
- Check desktop layout.
- Check mobile layout.
- Check footer alignment.
- Check Our Cars slider arrows.
- Check Our Cars image lightbox.
- Check Contact Us form behavior.
- Check that `thank-you.html` loads.
- Confirm Formspree delivery to Gmail after the first live deploy or domain change.
- Confirm `contact-us.html` uses the active Formspree endpoint `https://formspree.io/f/mqevkzey`.
