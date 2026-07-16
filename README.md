# Skyway Media — Fishing Charter Landing Page

Dark, Apple-style landing page for Skyway Media's fishing charter vertical. Single-file build (`index.html`) with local video assets — no build step, deploys anywhere (GitHub Pages, Vercel, Netlify, or the Skyway server).

## What's inside

- **Hero** — full-screen boat footage, parallax, floating glass chips
- **Problem section** — platform fees, Google invisibility, dead websites, no rebooking
- **Fee calculator** — interactive sliders showing annual commission bleed
- **Live booking demo** — clickable calendar → trip → guests → Stripe-style checkout
- **Services, process, stats band, FAQ**
- **Lead form** — posts JSON to the Skyway CRM

## Hooking up the CRM

Open `index.html`, find the `SKYWAY_CRM` config at the top of the `<script>` block:

```js
const SKYWAY_CRM = {
  endpoint: "",   // your CRM webhook URL
  token: "",      // sent as Authorization: Bearer <token>
  source: "fishing-charter-landing"
};
```

Paste the endpoint + token and leads flow in as JSON:
`{name, phone, email, business, city, trips_per_month, current_platform, source, submitted_at}`

Until an endpoint is set, submissions log the payload to the console and show the success state (demo mode).

## Swapping in real boat footage

Drop your clips into `assets/` and update the two `<video>` sources:

- Hero: `assets/hero-drone.mp4` (real drone footage, 1080p H.264)
- Stats band: `assets/boat-45365.mp4`

Current clips are Mixkit stock (free commercial license, no attribution required).

## Deploy

Static hosting of the repo root. For GitHub Pages: Settings → Pages → deploy from `main` / root.
