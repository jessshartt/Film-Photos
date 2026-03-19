# Film Photos

A personal photo gallery site for sharing film photos with family and friends. Hosted on GitHub Pages.

**Live site:** https://jessshartt.github.io/Film-Photos
**Admin page:** https://jessshartt.github.io/Film-Photos/admin.html

---

## Current State (March 2026)

The site is fully functional. Current albums:
- **Aspen 2026** — 40 photos, cover photo set
- **NYC - Winter** — ~50 photos, cover photo set
- **Test** — empty album (can be deleted from admin → Manage Photos)

Repo is clean and up to date on `main`.

---

## Features

- **Password protected** — enter once per device, stays logged in (password: `film`)
- **Album grid** — homepage shows all albums with cover photos
- **Grid view** — clean 3-column layout, photos read left to right
- **Scrapbook view** — compact mini photo album with 3D page-flip animation; 2–6 photos per page in varied layouts; swipe or tap arrows to navigate
- **Lightbox** — full-screen photo viewer with prev/next navigation and keyboard support (arrow keys, Escape)
- **Favorites** — heart any photo to save it; view all favorites in one place
- **Admin page** — upload photos, manage albums, rename albums, set cover photos, delete photos — all from your phone, no terminal needed

---

## Uploading Photos (Admin)

1. Go to `https://jessshartt.github.io/Film-Photos/admin.html`
2. Paste your GitHub fine-grained personal access token (only needs to be done once per device)
3. Select an existing album or create a new one
4. Pick photos and tap **Upload**

To generate a token: GitHub → Settings → Developer settings → Personal access tokens → Fine-grained → give **Contents: read & write** access on the `Film-Photos` repo.

---

## Managing Photos (Admin)

In the **Manage Photos** section of the admin page:
- **Rename** — edit the album name field and tap Rename
- **✕** — delete a photo (also removes the album if it becomes empty)
- **★** — set a photo as the album cover
- **Delete Album** — appears when an album has 0 photos

---

## Pushing After Admin Uploads

The admin page commits directly to GitHub via the API. If you also work locally, your local branch may fall behind. Run:

```bash
cd Film-Photos
git pull --rebase && git push
```

---

## Local Development

```bash
cd Film-Photos
python3 -m http.server 8000
# Then open http://localhost:8000
```

---

## File Structure

```
Film-Photos/
├── index.html        # Homepage — password gate + album grid
├── album.html        # Album view — grid + scrapbook toggle, lightbox
├── favorites.html    # Favorites view — all hearted photos
├── admin.html        # Admin — upload, manage, rename, delete
├── styles.css        # All styles (shared across pages)
├── albums.json       # Album metadata + photo paths (source of truth)
└── photos/
    ├── aspen-2026/
    └── new-york-winter---2026/
```

**Key localStorage keys:**
| Key | Value |
|-----|-------|
| `film_auth` | `"true"` — set on login |
| `film_favorites` | JSON array of photo paths |
| `film_github_token` | GitHub PAT for admin uploads |

---

## Tech

Plain HTML, CSS, and JavaScript — no frameworks. Photos and album metadata stored directly in this repo via the GitHub Contents API.
