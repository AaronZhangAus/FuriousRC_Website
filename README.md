# Furious RC Static Website

This project is a static HTML/CSS website for Furious RC. It was built from provided screenshots and local image assets.

The website currently uses plain HTML, CSS, and a small amount of JavaScript for the Our Cars photo sliders and image lightbox.

## Website Pages

The site has four pages:

- `index.html` - Homepage
- `packages.html` - Packages
- `our-cars.html` - Our Cars
- `contact-us.html` - Contact Us

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
|-- styles.css
|-- README.md
|-- videos/
|   `-- Welcome_video.mp4
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

- School Incursions `Learn More` links to `packages.html#beginner-racer-training-camp`
- Council Events/Festivals `Learn More` links to `packages.html#mega-race`
- Birthday Party `Learn More` links to `packages.html#mega-race`

Homepage video:

- The homepage hero uses `videos/Welcome_video.mp4`.
- The video autoplays, loops, stays muted, and plays inline on mobile.
- `images/Homepage-Welcome-banner.jpg` is used as the poster/fallback image.
- The homepage header uses a solid dark grey background to cover a logo area in the top-right of the video.

### Packages

File: `packages.html`

Main sections:

- Header
- Packages welcome image
- Beginner Racer Training Camp package
- Mega Race package
- Shared footer

Bookmark sections:

```html
id="beginner-racer-training-camp"
id="mega-race"
```

These IDs allow links from the homepage to jump directly to the correct package section.

### Our Cars

File: `our-cars.html`

Main sections:

- Header
- Our Cars welcome image
- MJX 10303/10304 1/10 Rally Car section
- MJX 14209 Dessert Truck section
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
action="mailto:aaron.zhang.aus@gmail.com"
method="post"
enctype="text/plain"
```

This opens the user's default email application. It does not send email silently from the website.

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

The current Contact Us form uses `mailto:`.

Current behavior:

- The user fills in the form.
- The user clicks Submit.
- The browser tries to open the user's default email application.
- The user must send the email manually from their email application.

Limitation:

- If the user does not have a default email application configured, clicking Submit may appear to do nothing.
- Static HTML cannot silently send emails by itself.

## Sending Emails With Backend Support

To send form submissions directly to `aaron.zhang.aus@gmail.com`, the website needs backend support.

Recommended flow:

1. User fills in the Contact Us form.
2. Browser sends the form data to a backend endpoint, for example `/api/contact`.
3. Backend validates the data.
4. Backend sends an email using SMTP or an email API.
5. Backend returns success or error.
6. Website shows a thank-you or error message.

### Example Backend Endpoint

The frontend form could be changed from:

```html
<form class="contact-form" action="mailto:aaron.zhang.aus@gmail.com" method="post" enctype="text/plain">
```

To:

```html
<form class="contact-form" action="/api/contact" method="POST">
```

Recommended field names:

```html
<input type="text" name="first_name" required>
<input type="text" name="last_name">
<input type="email" name="email" required>
<input type="tel" name="phone">
<textarea name="message"></textarea>
```

### Backend Requirements

The backend should:

- Accept `POST` requests from the contact form.
- Validate required fields.
- Validate the email format.
- Sanitize user input.
- Add spam protection.
- Send the email to `aaron.zhang.aus@gmail.com`.
- Return a clear success or failure response.

### Email Sending Options

Common backend email options:

- SMTP server
- SendGrid
- Mailgun
- Amazon SES
- Postmark
- Resend
- Nodemailer with Node.js
- Python `smtplib`

### Example Email Content

The backend should send an email with content similar to:

```text
Subject: New Furious RC Contact Form Submission

First name: Jane
Last name: Smith
Email: jane@example.com
Phone: 0400 000 000

Message:
I would like to book a birthday party package.
```

### Spam Protection

At minimum, add:

- Honeypot hidden field
- Basic rate limiting
- Server-side validation

For stronger protection, add:

- reCAPTCHA
- Cloudflare Turnstile
- hCaptcha

### Success Page Or Message

After a backend receives the form, use one of these approaches:

- Redirect the user to a thank-you page.
- Show an inline success message.
- Return JSON and handle it with JavaScript.

Simple redirect example:

```text
/thank-you.html
```

## Deployment Notes

This site can be hosted as static files on:

- Netlify
- Vercel
- GitHub Pages
- Cloudflare Pages
- Standard web hosting with Apache or Nginx

If backend email support is required, choose a host that supports:

- Serverless functions
- API routes
- Traditional backend hosting

Static-only hosting is enough for the pages and sliders, but not enough for silent email sending.

## Transferring The Website To A Server

Upload only the public website files and folders needed by the browser. Do not upload local development folders such as `.idea/`, `venv/`, `screenshots/`, or `skills/`.

### Files And Folders To Upload

Upload these files and folders to the server's public website root folder, usually named `public_html`, `www`, `htdocs`, or the root folder provided by the hosting company:

```text
index.html
packages.html
our-cars.html
contact-us.html
styles.css
images/
videos/
```

Upload the full `images/` folder, including:

```text
images/
|-- boxofSCRAPS.jpg
|-- Contactus-Welcome-banner.jpg
|-- FuriousRCLogo.jpg
|-- Homepage-Welcome-banner.jpg
|-- Homepage_BirthdayParty_01.jpg
|-- Homepage_BirthdayParty_02.jpg
|-- Homepage_CouncilEvent_01.jpg
|-- Homepage_CouncilEvent_02.jpg
|-- Homepage_SchoolIncursion_01.jpg
|-- Homepage_SchoolIncursion_02.jpg
|-- Homepage_SchoolIncursion_03.jpg
|-- Ourcars-Welcome-banner.jpg
|-- Packages-Welcome-banner.jpg
`-- OurCars/
    |-- ArrmaFury223S/
    |   |-- 0.jpg
    |   |-- 1.jpg
    |   |-- 2.jpg
    |   |-- 3.jpg
    |   |-- 4.jpg
    |   |-- 5.jpg
    |   |-- 6.jpg
    |   |-- 7.jpg
    |   `-- video_thumbnails/
    |       `-- 1.jpg
    |-- MJX10303_10304/
    |   |-- 0.jpg
    |   |-- 1.jpg
    |   |-- 2.jpg
    |   |-- 3.jpg
    |   |-- 4.jpg
    |   |-- 5.jpg
    |   `-- video_thumbnails/
    |       |-- 1.jpg
    |       |-- 2.jpg
    |       `-- 3.jpg
    `-- MJX14209/
        |-- 1.jpg
        |-- 2.jpg
        |-- 3.jpg
        |-- 4.jpg
        |-- 5.jpg
        `-- video_thumbnail/
            |-- 1.jpg
            `-- 2.jpg
```

Upload the full `videos/` folder, including:

```text
videos/
`-- Welcome_video.mp4
```

Optional:

```text
README.md
```

`README.md` is documentation only. The live website does not need it to run.

### Do Not Upload

These are local project/development materials and should normally stay off the public server:

```text
.idea/
venv/
screenshots/
skills/
pyproject.toml
README.md
```

`README.md` appears in both lists because it is optional. Upload it only if you want documentation available on the server.

### Step-By-Step Upload Process

1. Choose a static hosting provider. Simple options include Netlify, Vercel, Cloudflare Pages, GitHub Pages, or standard cPanel web hosting.
2. If using standard web hosting, open your hosting control panel, FTP client, or SFTP client.
3. Find the public website folder. It is usually named:

```text
public_html/
www/
htdocs/
```

4. Upload these files directly into that public folder:

```text
index.html
packages.html
our-cars.html
contact-us.html
styles.css
```

5. Upload the entire `images/` folder into the same public folder.
6. Upload the entire `videos/` folder into the same public folder.
7. Confirm the server structure looks like this:

```text
public_html/
|-- index.html
|-- packages.html
|-- our-cars.html
|-- contact-us.html
|-- styles.css
|-- images/
`-- videos/
```

8. Make sure `index.html` is in the root public folder, not inside another folder. This is what makes the homepage load at your domain.
9. If your FTP/SFTP client asks whether to overwrite existing files, choose overwrite for files you intentionally updated.
10. Open the live website in a browser:

```text
https://your-domain.com/
```

11. Test these pages:

```text
https://your-domain.com/index.html
https://your-domain.com/packages.html
https://your-domain.com/our-cars.html
https://your-domain.com/contact-us.html
```

12. Test the important assets:

- Homepage video
- Homepage images
- Package banner
- Our Cars welcome banner
- Contact Us banner
- Our Cars photo sliders
- Our Cars image lightbox
- Our Cars YouTube popups
- Contact form behavior

13. Hard refresh the browser if old styling still appears:

```text
Ctrl + F5
```

14. If an image, video, or stylesheet is missing, verify that the filename and capitalization on the server exactly match the filename used in the HTML.
15. Test the site on desktop and mobile after upload.

### Important Server Notes

- The homepage must be named `index.html` so the domain opens the homepage automatically.
- Keep `styles.css` next to the `.html` files because each page links to `styles.css`.
- Keep all image paths relative, such as `images/FuriousRCLogo.jpg`.
- Keep all video paths relative, such as `videos/Welcome_video.mp4`.
- Server filenames can be case-sensitive. `images/OurCars/MJX14209/1.jpg` is different from `images/ourcars/mjx14209/1.jpg` on many servers.
- If the Contact Us form still uses `mailto:`, no backend upload is required.
- If silent email sending is added later, the backend/API files must be deployed according to that backend host's instructions.

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
- Confirm whether the form should use `mailto:` or a backend endpoint.
