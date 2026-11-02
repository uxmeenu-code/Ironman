# Ironing Service – apartment ironing app (MVP prototype)

Mobile-first web app for apartment-based ironing: **Collect · Iron · Deliver**.
One static file (`index.html`, no build step) with four role-based interfaces.

| Role | What they do |
|---|---|
| **Customer** | Pick home / friend / mom flats, view the weekly collection schedule, book items with itemised pricing, pay, and track every stage; sees nearby iron men on a map and the pickup person's photo |
| **Pickup person** | Today's apartments and flats, accept pickups, record cloth type and count per flat, label each bag, drop the lot to a chosen iron man, quality-check and collect ironed bags, deliver to flats |
| **Iron man** | Dashboard, bag queue (To Iron / In Progress / Completed), confirm received count, update per-item ironing progress, submit for quality check, notifications with call button, earnings |
| **Admin** | Approve apartments, iron man shops and pickup people (with documents), set schedules and prices, monitor all orders, release payouts after quality approval |

Workflow: Booked → Pickup accepted → Collected → Dropped to iron man → Picked up from iron man → Delivered.
Payout is only created after the quality check is approved.

## Run locally
Open `index.html` in Chrome, or `python3 -m http.server 8000` and visit http://localhost:8000.
On the first screen tap **Load sample data**, then jump into any customer, iron man or pickup person (sample orders exist at every stage). **Admin (demo)** needs no password.

## Deploy
Static site, no build command, publish directory `.`
- **Netlify** / **Vercel**: import this repo (config files included).
- **GitHub Pages**: Settings > Pages > Deploy from branch `main` / root.

## Limitations (prototype)
- Data lives in each browser's `localStorage`; different phones do not share orders.
- OTP is simulated on screen (no SMS). Admin has no password.
- Document uploads store only file names; the pickup person's photo stays in the browser.
- The map is a schematic drawing; shop and apartment links open Google Maps.

## To make it production-ready
Backend and database (e.g. Supabase / Firebase) for shared data and real auth, an SMS OTP provider,
secure storage for ID and licence documents, a payment gateway, and a real map (Google Maps / Mapbox).
