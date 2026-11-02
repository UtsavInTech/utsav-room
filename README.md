# Utsav's Room

My application for the Wispr Flow India growth team. Built by talking, not typing.

**Live: https://utsav-room-production.up.railway.app**

Press **"3-minute tour"** and it walks you through everything on its own: my years in the room, then every app on the laptop.

## What it is

A 3D room you walk through by year: 2021, 2023, 2024, 2026, and now. Use the cube button for an overview of the whole room. I'm at the desk, and the MacBook on it opens into a working macOS with:

- **How I built this:** ideas in my head, spoken through Wispr Flow, shaped by Claude into this site
- **How I use Wispr Flow:** where it fits in my day, with my real numbers as a user (102,899 words, 144 wpm, top 0.2%)
- **My AI Toolkit:** the AI tools I build with, and what I make with them
- **FocusSpace, Play2Place, Upgrade Gate:** products I've shipped, with real screenshots and what each one taught me
- **Ideas for Flow:** what I'd love next, as a daily user
- **Say the Full Idea:** a growth campaign I'd run in India
- **Notes, Photos, Messages, Mail and Music:** my story, my photos, and ways to reach me

## About me

- **Available:** full-time or internship, Bangalore, happy to travel
- **Contact:** utsav.udk@gmail.com · [LinkedIn](https://www.linkedin.com/in/utsav-tech/) · [GitHub](https://github.com/UtsavInTech) · [X](https://x.com/itsUtsav2020)

## Run it locally

Plain HTML, CSS and JavaScript, with no build step. It needs a local server because the 3D models load over HTTP.

```bash
python3 -m http.server 8768
```

Then open http://localhost:8768. With Node, `npm install && npm start` also works, and that's how Railway runs it.

## Project layout

```
index.html        the 3D room and the guided tour
mac/index.html    the macOS inside the laptop
css/motion.css    spring-based motion shared by both pages
js/songs.js       the music player (the room and the laptop share one player)
assets/           images, app icons, AI tool logos, wallpaper, HDR lighting, textures
models/           3D models, including my avatar (models/me)
photos/           my photos
```

## How it's built

- **3D:** three.js 0.160 with PBR materials, HDR lighting, ambient occlusion and bloom (only the Apple logo glows).
- **Motion:** damped-spring curves, the same physics Framer Motion uses, baked into CSS `linear()` easing. No animation library. Entry animations use `@starting-style`, and the dock magnification uses `:has()`.
- **Laptop:** a macOS-style desktop in an iframe, with a window manager, dock, menu bar and apps.
- **Tour:** 14 stops that play on their own, with pause, back and next. The room drives it and the laptop shows each app.
- **Music:** 30-second previews from the iTunes Search API, each with a link to the full song on Apple Music.
- **Wispr Flow numbers:** totals from my Flow Insights screen (2 Nov 2026). The daily chart comes from my local Flow history.
- **Hosting:** Railway, deployed from this repo on every push.

## Credits

- 3D models, textures and HDRI: [Poly Haven](https://polyhaven.com) (CC0)
- San Francisco view: Wikimedia Commons, "View from Salesforce Tower" (CC0)
- Laptop wallpaper: Golden Gate Bridge from Marshall's Beach, Frank Schulenburg, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
- Avatar: made with Avaturn from my own photos
- macOS icons, Apple Music, Wispr Flow and the AI tool logos belong to their owners and are used only to show a familiar desktop and the tools I use.
