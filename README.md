# Isherveer's Tech Services — business site

Static site for Isherveer's Tech Services (computer/IT support, drone aerial
photography, and custom 3D printing in Rotorua, NZ), hosted on GitHub Pages.
Plain HTML/CSS/JS — no build step, no framework.

## Pages

| File | Page |
|---|---|
| `index.html` | Home — overview of all three services |
| `it-support.html` | Computer / IT support |
| `drone-photography.html` | Drone aerial photography |
| `3d-printing.html` | Custom 3D printing |
| `contact.html` | Contact — Facebook, email, and an embedded job-request form |

All pages share `style.css` (every colour, font, and layout rule) and
`script.js` (just the mobile menu toggle).

## First things to do before this goes live

### 1. Google Form

Done — `contact.html` already embeds the live "Job Request" Google Form
(owned by `dailyvloggerstudios@gmail.com`), and email notifications are on
for new responses. To edit the questions, open the form at
[docs.google.com/forms](https://docs.google.com/forms) under that account;
changes there show up on the site automatically since it's just embedded.

### 2. Add real photos

`3d-printing.html`'s three past-project photos are pulled directly from
[Isherveer's MakerWorld profile](https://makerworld.com/en/@Isherveer/upload)
(hotlinked, so they stay in sync if those listings are ever updated — add
new MakerWorld uploads to the page the same way). As more jobs are designed
and printed that aren't MakerWorld uploads, add a new `.case` block with
your own photo.

`drone-photography.html` still shows three dashed placeholder boxes for
aerial shots (`aerial-01.jpg`, etc.) since there's no real aerial work to
show yet. To swap one in:

1. Put the image file in `assets/img/` (already created, currently empty).
2. In the relevant `.html` file, find the matching `<div class="photo-slot">`
   block and replace it with:
   ```html
   <img src="assets/img/your-file-name.jpg" alt="Short description of the photo" loading="lazy">
   ```
   The image will fill the same space the placeholder did — no CSS changes
   needed. Keep images under ~1–2MB each (resize/compress first) so pages
   load quickly on mobile data.

### 3. Double-check the contact details

`dailyvloggerstudios@gmail.com` and the Facebook Messenger link
(`facebook.com/isherveer`) are used throughout. Update them in each `.html`
file (search for the old value, replace everywhere it appears) if either
ever changes.

## Editing content

Everything is plain HTML — open the relevant file, edit the text inside
the `<section>` tags, save, commit, push. GitHub Pages rebuilds
automatically, usually within a minute of a push to `main`.

To add a new "past project" card on `3d-printing.html`, copy an existing
`.case` block and edit the text and image. To add a new video on
`drone-photography.html`, copy an existing `.v-card` block and swap in a
new Google Drive file ID (`https://drive.google.com/file/d/FILE_ID/preview`).

## Design notes

The look is built around a "field service ticket" idea rather than a
generic landing-page template: flat paper background, hairline rules
instead of card shadows, and custom line-art diagrams (drawn as inline SVG
in each page) instead of a stock icon pack. Colours and type live entirely
in `style.css`'s `:root` block at the top — change a value there and it
updates everywhere.
