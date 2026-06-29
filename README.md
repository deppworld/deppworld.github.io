# Deepak Verma — Portfolio Website

This folder is everything needed to host your site. Upload the whole folder
as-is to any static host (GitHub Pages, Netlify, Vercel, a university server,
etc.) — `index.html` is the homepage.

## Folder structure

```
website/
├── index.html                  ← the website (edit this for any text/content change)
├── Deepak_CV_updated.docx       ← linked from the "Download CV" button
└── assets/
    └── images/
        └── headshot.jpg         ← your photo (swap this file to change the photo)
```

## How to make common edits

Open `index.html` in any text editor (VS Code, Notepad++, even Notepad).

- **Change your photo**: replace `assets/images/headshot.jpg` with a new image
  file of the same name (keep it under ~1MB and roughly portrait-shaped for
  best results). No code edit needed.
- **Add/edit a publication**: search the file for `id="publications"`. Each
  publication is one block that looks like this — copy/paste a block and edit
  the text and link to add a new one:
  ```html
  <div class="pub" data-type="first">
    <div class="pub-band first"></div>
    <div>
      <div class="pub-title"><a href="DOI_LINK_HERE" target="_blank" rel="noopener">Paper Title</a></div>
      <div class="pub-meta">Author list · <em>Journal</em>, Year · <a href="DOI_LINK_HERE">doi:...</a></div>
    </div>
  </div>
  ```
  Use `data-type="first"` for first-author papers (violet bar) or
  `data-type="co"` for co-authored papers (teal bar).
- **Add/edit experience**: search for `id="experience"`, each role is a
  `.tl-item` block — copy/paste and edit dates, title, organization, and
  description.
- **Update contact form destination email**: search for `mailto:` near the
  bottom of the file. The address is base64-encoded so it isn't visible in
  the page source to visitors or scrapers — to change it, generate a new
  code with this one-liner (replace the email) and swap the string inside
  `atob('...')`:
  ```
  python3 -c "import base64; print(base64.b64encode(b'your_email@example.com').decode())"
  ```
- **Social links**: search for `social-pill` to find and edit the
  LinkedIn / ResearchGate / ORCID / GitHub / NCBI / Google Scholar links.

## Hosting

Any static host works since this is plain HTML/CSS/JS with no backend:
- **GitHub Pages**: create a repo, upload this folder's contents to the root
  (or `/docs`), enable Pages in repo settings.
- **Netlify / Vercel**: drag-and-drop this folder into their dashboard.
- **Your own server**: upload via FTP/cPanel to your `public_html` (or
  equivalent) directory.

No build step, npm install, or server required — it's a static site.
