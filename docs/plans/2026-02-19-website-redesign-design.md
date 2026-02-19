# Website Redesign — busta.me

**Date:** 2026-02-19

## Goal

Modernize the single-page personal website from its current dated HTML/CSS into a modern, minimal, scroll-reveal design reflecting a Senior/Staff-Level Engineer profile with 12+ years of experience.

## Tech Stack

- HTML5 semantic + CSS modern (custom properties, grid/flexbox, scroll-snap) + vanilla JS (IntersectionObserver)
- Font: Inter (Google Fonts)
- No frameworks, no build tools — stays deployable on GitHub Pages as-is
- SVG icons inline (no external image dependencies for social links)

## Color Palette

- Background: #0a0a0a (near-black)
- Text primary: #f5f5f5 (off-white)
- Text secondary: #888 (muted gray)
- Accent: subtle cool blue-gray for hover states
- Cards: #141414 with subtle border

## Structure (4 full-viewport sections)

### Section 1: Hero
- Name: "Santiago Bustamante" — large, clean typography
- Subtitle: "Senior / Staff-Level Engineer · Product-Driven · Mobile & Client Architecture"
- Profile photo (circular, subtle border) — local image
- Animated scroll indicator at bottom
- Fade-in on load

### Section 2: About
- Bio text (large, centered, readable):
  "Engineer with 12+ years building and scaling mobile products end-to-end. At the senior and staff level, I drive architectural decisions, shape technical strategy, and bridge the gap between product vision and engineering execution. My focus: iOS and client-side architecture at scale, with a product-first mindset across startups and established teams worldwide."
- Scroll-triggered fade-in/slide-up

### Section 3: What I Do
- 3 minimal cards with stagger animation:
  1. **Mobile & Client Architecture** — System design, platform strategy, iOS/Swift at scale
  2. **Product-Driven Engineering** — Translating product vision into technical execution
  3. **Staff-Level Leadership** — Architectural ownership, mentoring, cross-team influence

### Section 4: Connect
- Professional links only (SVG icons): LinkedIn, GitHub, StackOverflow, Resume PDF
- Contact email
- Footer: "From Colombia · Based in Spain" with flag emojis
- Fade-in animation

## Responsive

- Mobile: vertical stack, adapted font sizes, touch-friendly tap targets
- Desktop: centered content with max-width, generous whitespace
- Scroll-snap on desktop, natural scroll on mobile

## Animations

- IntersectionObserver for scroll-triggered reveal (fade + translateY)
- CSS transitions (opacity, transform) — nothing heavy
- Subtle, professional feel

## Social Links (professional only)
- Resume PDF (local file)
- LinkedIn: linkedin.com/in/busta117
- GitHub: github.com/busta117
- StackOverflow: stackoverflow.com/users/1499250

## Photo
- Download LinkedIn profile photo and save locally (LinkedIn URLs expire)
- Circular crop with CSS, subtle shadow/border

## Footer
- "From Colombia · Based in Spain" — reflects both worlds
- Emoji flags for visual accent

## Files to modify
- `index.html` — complete rewrite
- Remove unused images (btn_*.png, background_bottom.png)
- Add profile photo locally
