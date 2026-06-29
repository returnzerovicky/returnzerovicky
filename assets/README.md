# Assets Directory

This folder contains all visual assets for the One Piece-themed GitHub profile README.

## Folder Structure

```
assets/
├── svg/              # Animated SVG components
│   ├── ocean-banner.svg          # Animated ocean waves background
│   ├── pirate-ship.svg           # Floating ship illustration
│   ├── wanted-poster.svg         # Wanted poster frame
│   ├── compass.svg               # Compass rose icon
│   ├── divider-anchor.svg        # Anchor divider (═══⚓═══)
│   ├── divider-skull.svg         # Skull divider (═══☠═══)
│   ├── divider-waves.svg         # Waves divider (🌊🌊🌊)
│   ├── divider-swords.svg        # Swords divider (⚔════⚔)
│   ├── devil-fruit-react.svg     # React (Mera Mera no Mi)
│   ├── devil-fruit-node.svg      # Node.js (Goro Goro no Mi)
│   ├── devil-fruit-docker.svg    # Docker (Uo Uo no Mi)
│   ├── devil-fruit-aws.svg       # AWS (Magu Magu no Mi)
│   ├── devil-fruit-mongodb.svg   # MongoDB (Hie Hie no Mi)
│   ├── devil-fruit-redis.svg     # Redis (Hie Hie no Mi)
│   ├── crew-luffy.svg            # Luffy (Leadership)
│   ├── crew-zoro.svg             # Zoro (Backend)
│   ├── crew-nami.svg             # Nami (Frontend)
│   ├── crew-robin.svg            # Robin (AI/Data)
│   ├── crew-franky.svg           # Franky (DevOps)
│   ├── crew-usopp.svg            # Usopp (Testing)
│   ├── footer-ship.svg           # Ship sailing away (footer)
│   └── grand-line-map.svg        # Timeline map (East Blue → Laugh Tale)
│
├── png/              # Screenshots, diagrams, images
│   ├── resumemate-ui.png         # ResumeMate project screenshot
│   ├── editor-demo.png           # CollabCode project screenshot
│   ├── url-shortener-ui.png      # URL Shortener project screenshot
│   ├── campus-nav-map.png        # SmartCampus project screenshot
│   ├── arch-resumemate.png       # ResumeMate architecture diagram
│   ├── arch-editor.png           # CollabCode architecture diagram
│   ├── arch-urlshort.png         # URL Shortener architecture diagram
│   └── arch-campus.png           # SmartCampus architecture diagram
│
├── gif/              # Animated GIFs
│   ├── editor-demo.gif           # CollabCode editor animation
│   ├── resume-analysis.gif       # ResumeMate AI analysis animation
│   └── campus-nav-demo.gif       # SmartCampus navigation animation
│
└── README.md         # This file
```

## Asset Specifications

### SVG Assets

All SVG files should:
- Be optimized with [SVGOMG](https://jakearchibald.github.io/svgomg/)
- Use CSS animations (no JavaScript)
- Have transparent backgrounds
- Include descriptive `<title>` and `<desc>` tags for accessibility
- Follow the color palette from DESIGN_SYSTEM.md
- Dimensions: See table below

| Asset | Dimensions | Purpose |
|-------|-----------|----------|
| ocean-banner.svg | 1200×400px | Hero banner background (animated waves) |
| pirate-ship.svg | 600×300px | Floating ship in hero |
| wanted-poster.svg | 600×800px | Animated wanted poster frame |
| compass.svg | 100×100px | Small compass icon (spinning) |
| divider-*.svg | 1000×50px | Section dividers |
| devil-fruit-*.svg | 100×100px | Tech stack icons (glowing on hover) |
| crew-*.svg | 128×128px | Crew member icons |
| footer-ship.svg | 120×60px | Small ship in footer |
| grand-line-map.svg | 1200×200px | Timeline map |

### PNG Assets

All PNG files should:
- Be compressed to ≤100KB where possible
- Have descriptive alt-text
- Ensure readable text overlays (4.5:1 contrast minimum)
- Dimensions: See table below

| Asset | Dimensions | Purpose |
|-------|-----------|----------|
| resumemate-ui.png | 800×450px | Project screenshot |
| editor-demo.png | 800×450px | Project screenshot |
| url-shortener-ui.png | 800×450px | Project screenshot |
| campus-nav-map.png | 800×450px | Project screenshot |
| arch-resumemate.png | 800×400px | Architecture diagram |
| arch-editor.png | 800×400px | Architecture diagram |
| arch-urlshort.png | 800×400px | Architecture diagram |
| arch-campus.png | 800×400px | Architecture diagram |

### GIF Assets

All GIF files should:
- Loop smoothly (no gaps between frames)
- Be optimized with [Gifsicle](https://www.lcdf.org/gifsicle/) (lossy compression)
- Be ≤2MB in size
- Have descriptive alt-text

---

## How to Use

### Linking SVGs in README

```markdown
![Ocean Banner](assets/svg/ocean-banner.svg)
```

### Linking PNGs in README

```markdown
![ResumeMate Screenshot](assets/png/resumemate-ui.png)
```

### Raw GitHub URLs

For external links:

```
https://raw.githubusercontent.com/returnzerovicky/returnzerovicky/main/assets/svg/ocean-banner.svg
```

### Alt-Text Examples

- Ocean Banner: "Animated ocean waves background with gentle moving water"
- Wanted Poster: "Wanted poster frame with pirate aesthetic"
- Devil Fruit Icons: "Glowing devil fruit icon representing [tech name]"
- Project Screenshots: "Screenshot of [project name] user interface"

---

## Adding New Assets

1. **Create the asset** in design tool (Figma, Inkscape, etc.)
2. **Export as SVG or PNG** with appropriate dimensions
3. **Optimize**: Use SVGOMG (SVG) or TinyPNG (PNG)
4. **Add to folder**: Place in appropriate subfolder
5. **Update README.md**: Add to the Asset Specifications table
6. **Commit**: Use descriptive commit message

### Example Commit

```
feat(assets): add devil-fruit icons for tech stack

- Add 6 new SVG icons for core technologies
- Optimize with SVGOMG
- Ensure WCAG AA contrast compliance
- Update assets/README.md
```

---

## References

- [SVG Optimization (SVGOMG)](https://jakearchibald.github.io/svgomg/)
- [PNG Compression (TinyPNG)](https://tinypng.com/)
- [GIF Optimization (Gifsicle)](https://www.lcdf.org/gifsicle/)
- [Accessibility (WCAG)](https://www.w3.org/WAI/WCAG21/quickref/)

---

**Last Updated:** June 2026  
**Maintainer:** @returnzerovicky
