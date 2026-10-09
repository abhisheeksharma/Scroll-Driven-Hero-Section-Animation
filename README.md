# ITZ FIZZ — Scroll-Driven Hero

A responsive scroll-driven hero experience built with **Next.js**, **Tailwind CSS**, **GSAP**, and **ScrollTrigger**. The design is inspired by the supplied Itz Fizz car-scroll reference: tracked headline, four impact metrics, an animated car illustration, and a dark closing section.

## Requirements

- Node.js 18.17 or newer (Node 20 LTS recommended)
- npm

## Run locally

1. Extract the ZIP and open the `itz-fizz-scroll-hero` folder in VS Code.
2. Open a terminal in that folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Visit [http://localhost:3000](http://localhost:3000).

## Production build

```bash
npm run build
npm start
```

## How the animation works

- **Intro:** GSAP animates headline letters with a stagger and reveals the four metrics sequentially.
- **Scroll motion:** `ScrollTrigger` uses `scrub` so the car's translation, rotation, and scale are tied to scroll progress rather than playing as an autoplay animation.
- **Smoothness:** The animated car and orbit use transform properties; the GSAP context is reverted on unmount to clean up animations and triggers.
- **Responsive:** CSS breakpoints adjust typography, statistics, and the car illustration for smaller screens.

## Main files

- `app/page.jsx` — page entry
- `app/layout.jsx` — metadata and root layout
- `app/globals.css` — responsive layout, Tailwind directives, and styling
- `components/HeroExperience.jsx` — hero markup and GSAP animations
- `tailwind.config.js` — Tailwind configuration

## Customize

- Change the headline and metrics in `components/HeroExperience.jsx`.
- Tune scroll length by changing `height: 200vh` on `.scroll-stage` in `app/globals.css`.
- Adjust the car's scroll movement in the `gsap.to(car.current, ...)` block.

The car is an inline SVG illustration, so no external image/API is required.
