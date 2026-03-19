# Film Photos

A personal photo gallery site for sharing film photos with family and friends. Hosted on GitHub Pages.

**Live site:** https://jessshartt.github.io/Film-Photos

---

## Features

- **Password protected** — enter once per device, stays logged in
- **Album grid** — homepage shows all albums with cover photos
- **Grid view** — clean 3-column layout, photos read left to right
- **Scrapbook view** — compact mini photo album with page flip animation (2–6 photos per page in varied layouts)
- **Lightbox** — full-screen photo viewer with prev/next navigation and keyboard support
- **Favorites** — heart any photo to save it; view all favorites in one place
- **Admin page** — upload photos and manage albums directly from your phone, no terminal needed

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
- **✕** — delete a photo (also removes the album if it becomes empty)
- **★** — set a photo as the album cover

---

## Local Development

```bash
# Serve locally (Python)
cd Film-Photos
python3 -m http.server 8000
# Then open http://localhost:8000
```

---

## Tech

Plain HTML, CSS, and JavaScript — no frameworks. Photos and album metadata stored directly in this repo via the GitHub Contents API.
