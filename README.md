# Ibn Burhan

Marketing website for **Ibn Burhan**, an autonomous aviation company building UAVs and TB-2 class drones.

A single static page: no build step.

- **Hero:** a pinned, scroll-driven scene. A 3D TB2-class aircraft (three.js) starts beside the headline, then flies across the whole screen as you scroll.
- **Sections:** mission, platform explorer (animated tabs), in-flight video, capabilities, mission planner, roadmap and contact form.
- Responsive, with a fallback aircraft if WebGL or the model cannot load.

## Run locally

The 3D model is loaded with `fetch`, so open the site through a local server instead of double-clicking the file:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Node.js works too: `npx serve .`

## Deploy

Enable **Settings → Pages → Deploy from a branch → `main` / root** to host it on GitHub Pages.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The whole site: markup, styles, scripts |
| `model.json`, `tex/` | Optimised glTF aircraft model (geometry is embedded in `model.json`) and its textures |
| `hero.mp4`, `poster.jpg` | In-flight video and its poster frame |

External libraries load from CDNs: three.js r128 (cdnjs) and Google Fonts. The glTF loader is included in `index.html`.

## To edit before launch

- Platform specs, and the names IB Scout and IB Surveyor, are placeholders.
- Add the real address and email in the contact section. The contact form is not connected to an email service yet.

## 3D model credit (CC BY 4.0)

This work is based on "Bayraktar TB2 Military Ukrainian Navi" (https://sketchfab.com/3d-models/bayraktar-tb2-military-ukrainian-navi-0f888399a49444ad84cc8d6b89b449e7) by Idmental (https://sketchfab.com/idmental.id), licensed under CC BY 4.0 (http://creativecommons.org/licenses/by/4.0/).

Changes made: geometry simplified for the web, livery markings removed, textures resized, and colours changed. The credit also appears in the site footer. Keep it when you share or modify the site.
