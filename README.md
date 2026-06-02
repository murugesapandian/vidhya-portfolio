# Art by Vidhya — Portfolio Website

The official digital art & illustration portfolio of **Vidhyasree Murugesapandian**, live at **[artbyvidhya.com](https://artbyvidhya.com)**.

A fast, fully static, responsive website — no server or database required. It works on GitHub Pages, Netlify, Vercel, or any static host.

---

## 📁 Project structure

```
artbyvidhya/
├─ public/                ← everything that gets deployed
│  ├─ index.html          ← the portfolio (home, gallery, about, contact)
│  ├─ admin.html          ← private page to add/edit/reorder drawings
│  ├─ artwork.json        ← the list of all artworks (titles, descriptions…)
│  ├─ artwork/            ← the drawing image files
│  ├─ assets/logo.png     ← site logo
│  ├─ favicon.png
│  ├─ CNAME               ← custom domain (artbyvidhya.com)
│  ├─ 404.html
│  └─ robots.txt
├─ netlify.toml           ← Netlify deploy config (optional)
├─ vercel.json            ← Vercel deploy config (optional)
└─ README.md
```

---

## 🖼️ How to add or change drawings (the easy way)

1. Open **`admin.html`** in a browser (locally, or at `artbyvidhya.com/admin.html`).
2. **Drag & drop** drawing images onto the upload box.
3. Type a **title, year, medium, size, and description** for each.
4. Reorder with the ↑ ↓ buttons; remove with ✕.
5. Click **Save Changes** to preview instantly on the site (saved in your browser).
6. Click **Download artwork.json** to get the updated list.

### To publish permanently for everyone

1. Put your new image files into `public/artwork/` (e.g. `art-21.jpg`).
2. In the downloaded `artwork.json`, make sure each new piece's `image` points to its file, e.g. `"image": "artwork/art-21.jpg"`.
   *(The admin page stores newly added images inline for preview; before publishing, save the actual file in `artwork/` and set the path. See note below.)*
3. Replace `public/artwork.json` with your downloaded version.
4. Commit & push to GitHub (see Deploy). The live site updates automatically.

> **Note on images:** the admin preview embeds new uploads directly so Vidhyasree sees them immediately. For the permanent public site, each drawing should be saved as a real file in `public/artwork/` and referenced by path — this keeps the site small and fast. The README's deploy step covers this.

You can also edit `public/artwork.json` directly by hand — it's a simple list:

```json
{
  "image": "artwork/art-01.jpg",
  "title": "Embrace the Colors",
  "year": "2026",
  "medium": "Digital on iPad",
  "size": "30 x 37 in. (76.2 x 94 cm.)",
  "description": "A short description of the piece."
}
```

---

## 🚀 Run it locally

No build step. Just serve the `public/` folder:

```bash
cd public
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## 🌐 Deploy

### Option A — GitHub Pages (uses the included CNAME)
1. Push this repo to GitHub.
2. Repo **Settings → Pages**.
3. Set **Source** to your branch, folder **`/public`** (or move `public/`'s contents to the root and pick `/root`).
4. Under **Custom domain**, enter `artbyvidhya.com` (the `CNAME` file is already included).
5. At your domain registrar, point DNS to GitHub Pages:
   - `A` records for the apex `artbyvidhya.com` →
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `murugesapandian.github.io`
6. Enable **Enforce HTTPS** once the certificate is issued.

### Option B — Netlify
Drag the `public/` folder into Netlify, or connect the repo (config in `netlify.toml`). Add `artbyvidhya.com` under Domain settings.

### Option C — Vercel
Import the repo (config in `vercel.json`). Add the domain in project settings.

---

## ✨ Features
- Fully responsive masonry gallery with smooth reveal animations
- Click any piece for a full-screen lightbox with details (keyboard ← → and Esc)
- Editorial, gallery-quality design with the custom brush logo
- Private admin panel to manage the collection with no coding
- SEO tags, custom 404, favicon, and custom-domain ready

© Vidhyasree Murugesapandian. Artwork is the property of the artist.
