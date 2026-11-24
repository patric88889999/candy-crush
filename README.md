# Kueh Pop!

A match-3 game with Singapore kueh, made for phones. Match 3 or more of the same kueh and pop as many as you can in 60 seconds.

It is a Progressive Web App (PWA): open it in your phone's browser, add it to your home screen, and it runs full-screen like a normal app, even offline.

## How to play

- **Swap:** swipe a kueh, or tap two kueh side by side.
- **4 in a row:** 3 extra seconds.
- **L or T shape:** makes a sparkly **Boom kueh**. Match it to blast the 3×3 around it.
- **5 in a row:** makes a **Durian**. Swap it with any kueh to pop every kueh of that kind.
- **Combos:** swap two Boom kueh, or a Durian with a Boom kueh, for a much bigger blast.

## Install on your phone

- **Android (Chrome):** open the site and tap **Add Kueh Pop to my phone** on the start screen. You can also use the ⋮ menu, then **Install app**.
- **iPhone (Safari):** open the site, tap **Share**, then **Add to Home Screen**.

## Project structure

```
index.html             The whole game (HTML, CSS and JavaScript, no build step)
manifest.webmanifest   App name, colours and icons for installing
sw.js                  Service worker: offline play and fast loading
icons/                 App icons (192/512 px, maskable versions, iPhone icon, favicons)
vercel.json            Caching headers for Vercel
```

## Deploy

It is a plain static site, so there is nothing to build.

- **Vercel:** import this repo at vercel.com/new. Framework preset: **Other**. Leave the build command and output directory empty. Every push to `main` redeploys.
- **Run locally:** `npx serve .` and open the address it shows. The service worker needs `http://localhost` or HTTPS; it won't run when you open `index.html` straight from disk.

## Updating the game

After you change `index.html` or the icons, bump `VERSION` in `sw.js` (for example `kueh-pop-v2`). Installed copies then pick up the new version the next time they open online.
