# Utsav's Room

My application for the Wispr Flow India growth team. Built by talking, not typing.

It's a 3D room you can walk through by year. I'm sitting at the desk, and the MacBook on it opens into a working macOS with my projects, notes, music and a "How I built this" story told through Wispr Flow.

- **Available:** full-time or internship, Bangalore, happy to travel
- **Contact:** utsav.udk@gmail.com · [LinkedIn](https://www.linkedin.com/in/utsav-tech/) · [GitHub](https://github.com/UtsavInTech) · [X](https://x.com/itsUtsav2020)

## Run it locally

It's plain HTML, CSS and JavaScript with no build step. It needs a local server because the 3D models load over HTTP.

```bash
python3 -m http.server 8768
```

Then open http://localhost:8768. Or, with Node: `npm install && npm start` (this is also how Railway runs it).

## What's inside

```
index.html        the 3D room (three.js)
mac/index.html    the macOS inside the laptop
css/motion.css    spring-based motion shared by both pages
js/songs.js       the music player (room and laptop share one player)
assets/           images, app icons, wallpaper, HDR lighting, textures
models/           3D models, including my avatar (models/me)
photos/           my photos
```

## How it's built

- **3D:** three.js 0.160 with PBR materials, HDR lighting, ambient occlusion and bloom (only the Apple logo glows).
- **Motion:** real damped-spring curves, the same physics Framer Motion uses, baked into CSS `linear()` easing. No animation library. Entry animations use `@starting-style`, and the dock magnification uses `:has()`.
- **Laptop:** a macOS-style desktop in an iframe, with a window manager, dock, menu bar and apps.
- **Music:** 30-second previews from the iTunes Search API, each with a link to the full song on Apple Music.
- **Wispr Flow numbers:** my own dictation stats, read from my local Wispr Flow app.

## Credits

- 3D models, textures and HDRI: [Poly Haven](https://polyhaven.com) (CC0)
- San Francisco view: Wikimedia Commons, "View from Salesforce Tower" (CC0)
- Laptop wallpaper: Golden Gate Bridge from Marshall's Beach, Frank Schulenburg, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
- Avatar: made with Avaturn from my own photos
- macOS icons, Apple Music and Wispr Flow marks belong to their owners and are used here only to recreate a familiar desktop.
