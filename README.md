# portfolio-content

Content repository for [my portfolio](https://arnab-here.vercel.app) — served via jsDelivr CDN.

The portfolio ([`ArNAB-0053/my-portfolio`](https://github.com/ArNAB-0053/my-portfolio)) is built with Next.js and deployed on Vercel. It fetches all dynamic data and assets from this repo at runtime, so I can update projects, swap my resume, or add banners without touching the portfolio codebase or triggering a redeployment.

---

## Why this exists

The portfolio UI lives in a separate repository. This repo holds everything that changes frequently:

- **Project data** — add, remove, or edit projects by updating a single JSON file
- **Resume** — drop in a new PDF whenever it's updated
- **Project banners** — only newer project banners are stored here; older ones are still hosted on Imgur and referenced directly in `projects.json`
- **Fonts** — personal collection; not necessarily in use, just archived here for future reference

---

## Folder Structure

```
portfolio-content/
├── Fonts/        # Personal font collection for future use
├── Images/       # Banners for newer projects only (older ones are on Imgur)
├── JSON/
│   └── projects.json   # Project data fetched by the portfolio at runtime
└── PDF/
    └── Arnab_Bhattacharyya_Resume.pdf
```

---

## CDN URLs

### jsDelivr

| Resource | URL |
|---|---|
| Repository root | `https://cdn.jsdelivr.net/gh/ArNAB-0053/portfolio-content/` |
| projects.json | `https://cdn.jsdelivr.net/gh/ArNAB-0053/portfolio-content/JSON/projects.json` |
| Resume PDF | `https://cdn.jsdelivr.net/gh/ArNAB-0053/portfolio-content/PDF/Arnab_Bhattacharyya_Resume.pdf` |
| Images | `https://cdn.jsdelivr.net/gh/ArNAB-0053/portfolio-content/Images/<image-name>` |
| Fonts | `https://cdn.jsdelivr.net/gh/ArNAB-0053/portfolio-content/Fonts/<font-name>` |

### Raw GitHub

| Resource | URL |
|---|---|
| Repository root | `https://raw.githubusercontent.com/ArNAB-0053/portfolio-content/main/` |
| projects.json | `https://raw.githubusercontent.com/ArNAB-0053/portfolio-content/main/JSON/projects.json` |
| Resume PDF | `https://raw.githubusercontent.com/ArNAB-0053/portfolio-content/main/PDF/Arnab_Bhattacharyya_Resume.pdf` |
| Images | `https://raw.githubusercontent.com/ArNAB-0053/portfolio-content/main/Images/<image-name>` |
| Fonts | `https://raw.githubusercontent.com/ArNAB-0053/portfolio-content/main/Fonts/<font-name>` |

---

## Purging the jsDelivr Cache

jsDelivr caches files aggressively. After pushing an update, purge the cache so the portfolio picks up the new version immediately.

**Option 1 — Direct URL**

Open the purge URL for the file you updated:

```
https://purge.jsdelivr.net/gh/ArNAB-0053/portfolio-content/JSON/projects.json
https://purge.jsdelivr.net/gh/ArNAB-0053/portfolio-content/PDF/Arnab_Bhattacharyya_Resume.pdf
```

Replace the file path for whichever file changed.

**Option 2 — jsDelivr Purge Tool**

1. Go to `https://www.jsdelivr.com/tools/purge`
2. Paste the jsDelivr CDN URL of the updated file
3. Click **Purge**
