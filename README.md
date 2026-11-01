# PressUp – apartment ironing service (MVP prototype)

Single-file, mobile-first web app (`index.html`, no build step) with four interfaces:
customer, iron man (shop owner), pickup boy, and admin.

## Run locally
Open `index.html` in Chrome, or run `python3 -m http.server 8000` and visit http://localhost:8000.
On the login screen tap **Load sample data** to get demo users, shops and 25 orders.

## Deploy (pick one)
**GitHub Pages**
1. Create a repo and push this folder to the `main` branch.
2. Repo Settings > Pages > Source: **GitHub Actions**.
3. The included workflow publishes it; the URL appears in the Actions run.

**Netlify**: New site > Import from Git > select repo (no build command, publish dir `.`).

**Vercel**: New Project > import repo > framework "Other" (no build command).

```bash
git init && git add . && git commit -m "PressUp MVP"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

## Important limitations
- Data (users, orders, uploaded photos) is stored in each browser's localStorage. Different phones do NOT see each other's updates, so this is a demo, not production.
- OTP is simulated on screen; no SMS is sent. Admin login has no password.
- Document uploads store only the file name; the pickup photo is kept in the browser.
- The map is a schematic drawing; "Open in Maps" links go to Google Maps.

## To make it production-ready
Add a backend and database (e.g. Supabase or Firebase) for shared data and real authentication,
an SMS OTP provider, secure file storage for ID/licence documents, a payment gateway, and a
real map (Google Maps / Mapbox).
