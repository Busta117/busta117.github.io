# Website Redesign Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Modernize busta.me from a dated single-page HTML site into a scroll-reveal, dark-themed, responsive personal site reflecting a Senior/Staff-Level Engineer with 12+ years of experience.

**Architecture:** Single `index.html` with inline `<style>` and `<script>`. Four full-viewport sections revealed on scroll via IntersectionObserver. CSS custom properties for theming, flexbox/grid for layout, scroll-snap on desktop. No frameworks, no build tools — deploys as-is to GitHub Pages.

**Tech Stack:** HTML5, CSS3 (custom properties, grid, flexbox, scroll-snap), vanilla JS (IntersectionObserver), Google Fonts (Inter).

---

### Task 1: Download profile photo

**Files:**
- Create: `images/profile.jpg`

**Step 1: Download the LinkedIn profile photo locally**

Run:
```bash
curl -L -o /Users/khks381/Documents/WORK/Busta/busta117/images/profile.jpg "https://media.licdn.com/dms/image/v2/D4D03AQGnIFkNkWXoog/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1703717838923?e=1773273600&v=beta&t=aWIRbifntLVaI6aMJRBAyb1nSowCHcujvV3dgYSbQuI"
```

If this URL has expired, fall back to using the existing `images/img_santiago.png` — copy it as `images/profile.jpg` or reference it directly.

**Step 2: Verify the image downloaded**

Run:
```bash
file /Users/khks381/Documents/WORK/Busta/busta117/images/profile.jpg
```
Expected: Should report JPEG or PNG image data. If it reports HTML or text, the URL expired — use `img_santiago.png` instead.

**Step 3: Commit**

```bash
cd /Users/khks381/Documents/WORK/Busta/busta117
git add images/profile.jpg
git commit -m "feat: add profile photo for redesign"
```

---

### Task 2: Rewrite index.html — HTML structure

**Files:**
- Modify: `index.html` (complete rewrite)

**Step 1: Replace the entire content of `index.html`**

Write the full HTML structure with all four sections. The complete file content:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Santiago Bustamante — Senior / Staff-Level Engineer</title>
  <meta name="description" content="Senior / Staff-Level Engineer. Product-Driven. Mobile & Client Architecture. 12+ years of experience.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <!-- STYLES GO HERE (Task 3) -->

</head>
<body>

  <!-- Section 1: Hero -->
  <section class="section hero" id="hero">
    <div class="hero-content">
      <div class="hero-photo">
        <img src="images/profile.jpg" alt="Santiago Bustamante" width="160" height="160">
      </div>
      <h1 class="hero-name">Santiago Bustamante</h1>
      <p class="hero-title">Senior / Staff-Level Engineer · Product-Driven · Mobile & Client Architecture</p>
    </div>
    <div class="scroll-indicator" aria-hidden="true">
      <span class="scroll-arrow"></span>
    </div>
  </section>

  <!-- Section 2: About -->
  <section class="section about" id="about">
    <div class="section-inner">
      <p class="about-text reveal">
        Engineer with 12+ years building and scaling mobile products end-to-end. At the senior and staff level, I drive architectural decisions, shape technical strategy, and bridge the gap between product vision and engineering execution.
      </p>
      <p class="about-text reveal">
        My focus: iOS and client-side architecture at scale, with a product-first mindset across startups and established teams worldwide.
      </p>
    </div>
  </section>

  <!-- Section 3: What I Do -->
  <section class="section what-i-do" id="what-i-do">
    <div class="section-inner">
      <div class="cards">
        <div class="card reveal">
          <h2 class="card-title">Mobile & Client Architecture</h2>
          <p class="card-desc">System design, platform strategy, iOS &amp; Swift at scale.</p>
        </div>
        <div class="card reveal">
          <h2 class="card-title">Product-Driven Engineering</h2>
          <p class="card-desc">Translating product vision into technical execution.</p>
        </div>
        <div class="card reveal">
          <h2 class="card-title">Staff-Level Leadership</h2>
          <p class="card-desc">Architectural ownership, mentoring, cross-team influence.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Section 4: Connect -->
  <section class="section connect" id="connect">
    <div class="section-inner">
      <h2 class="connect-heading reveal">Let's connect</h2>
      <div class="links reveal">

        <a href="https://www.linkedin.com/in/busta117" target="_blank" rel="noopener noreferrer" class="link" aria-label="LinkedIn">
          <svg viewBox="0 0 24 24" fill="currentColor" width="28" height="28"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          <span>LinkedIn</span>
        </a>

        <a href="https://github.com/busta117" target="_blank" rel="noopener noreferrer" class="link" aria-label="GitHub">
          <svg viewBox="0 0 24 24" fill="currentColor" width="28" height="28"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
          <span>GitHub</span>
        </a>

        <a href="https://stackoverflow.com/users/1499250" target="_blank" rel="noopener noreferrer" class="link" aria-label="Stack Overflow">
          <svg viewBox="0 0 24 24" fill="currentColor" width="28" height="28"><path d="M15.725 0l-1.72 1.277 6.39 8.588 1.716-1.277L15.725 0zm-3.94 3.418l-1.369 1.644 8.225 6.85 1.369-1.644-8.225-6.85zm-3.15 4.465l-.905 1.94 9.702 4.517.904-1.94-9.701-4.517zm-1.85 4.86l-.44 2.093 10.473 2.201.44-2.092-10.473-2.203zM1.89 15.47V24h19.19v-8.53h-2.133v6.397H4.021v-6.396H1.89zm4.265 2.133v2.13h10.66v-2.13H6.154z"/></svg>
          <span>Stack Overflow</span>
        </a>

        <a href="Curriculum_Vitae_English.pdf" target="_blank" rel="noopener noreferrer" class="link" aria-label="Resume">
          <svg viewBox="0 0 24 24" fill="currentColor" width="28" height="28"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8l-6-6zm4 18H6V4h7v5h5v11zM8 15h8v2H8v-2zm0-3h8v2H8v-2z"/></svg>
          <span>Resume</span>
        </a>

      </div>

      <a href="mailto:busta117@gmail.com" class="email-link reveal">busta117@gmail.com</a>

      <footer class="footer reveal">
        <p>From Colombia <span aria-label="Colombia">&#127464;&#127476;</span> · Based in Spain <span aria-label="Spain">&#127466;&#127480;</span></p>
      </footer>
    </div>
  </section>

  <!-- SCRIPT GOES HERE (Task 4) -->

</body>
</html>
```

**Important notes for the image path:** If Task 1 failed to download `profile.jpg`, change `src="images/profile.jpg"` to `src="images/img_santiago.png"`.

**Step 2: Commit**

```bash
git add index.html
git commit -m "feat: rewrite HTML structure for redesign

Four full-viewport sections: hero, about, what-i-do, connect.
Semantic HTML5, SVG icons, Inter font, accessibility attributes."
```

---

### Task 3: Add CSS styles to index.html

**Files:**
- Modify: `index.html` — replace the `<!-- STYLES GO HERE (Task 3) -->` comment

**Step 1: Replace `<!-- STYLES GO HERE (Task 3) -->` with the full `<style>` block**

```css
<style>
  /* ===== Reset & Base ===== */
  *, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :root {
    --bg: #0a0a0a;
    --bg-card: #141414;
    --text: #f5f5f5;
    --text-muted: #888;
    --accent: #a0b4c8;
    --border: #222;
    --font: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    --max-width: 720px;
    --section-padding: 0 clamp(1.5rem, 5vw, 4rem);
  }

  html {
    scroll-behavior: smooth;
    scroll-snap-type: y mandatory;
  }

  body {
    font-family: var(--font);
    background: var(--bg);
    color: var(--text);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  /* ===== Sections ===== */
  .section {
    min-height: 100vh;
    min-height: 100dvh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: var(--section-padding);
    scroll-snap-align: start;
    position: relative;
  }

  .section-inner {
    width: 100%;
    max-width: var(--max-width);
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  /* ===== Hero ===== */
  .hero-content {
    text-align: center;
    animation: fadeInUp 0.8s ease-out both;
  }

  .hero-photo {
    margin-bottom: 2rem;
  }

  .hero-photo img {
    width: 140px;
    height: 140px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid var(--border);
    filter: grayscale(15%);
    transition: filter 0.4s ease;
  }

  .hero-photo img:hover {
    filter: grayscale(0%);
  }

  .hero-name {
    font-size: clamp(2rem, 5vw, 3.5rem);
    font-weight: 600;
    letter-spacing: -0.02em;
    line-height: 1.1;
    margin-bottom: 1rem;
  }

  .hero-title {
    font-size: clamp(0.95rem, 2vw, 1.15rem);
    color: var(--text-muted);
    font-weight: 400;
    max-width: 500px;
    margin: 0 auto;
    line-height: 1.5;
  }

  /* Scroll indicator */
  .scroll-indicator {
    position: absolute;
    bottom: 2.5rem;
    left: 50%;
    transform: translateX(-50%);
    animation: fadeInUp 0.8s ease-out 0.6s both;
  }

  .scroll-arrow {
    display: block;
    width: 20px;
    height: 20px;
    border-right: 2px solid var(--text-muted);
    border-bottom: 2px solid var(--text-muted);
    transform: rotate(45deg);
    animation: bounceDown 2s ease-in-out infinite;
  }

  /* ===== About ===== */
  .about-text {
    font-size: clamp(1.15rem, 2.5vw, 1.5rem);
    font-weight: 300;
    line-height: 1.7;
    color: var(--text);
    text-align: center;
    max-width: var(--max-width);
    margin-bottom: 1.5rem;
  }

  .about-text:last-child {
    margin-bottom: 0;
  }

  /* ===== What I Do — Cards ===== */
  .cards {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.25rem;
    width: 100%;
    max-width: var(--max-width);
  }

  .card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 2rem 2.25rem;
    transition: border-color 0.3s ease, transform 0.3s ease;
  }

  .card:hover {
    border-color: var(--text-muted);
    transform: translateY(-2px);
  }

  .card-title {
    font-size: 1.15rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
    letter-spacing: -0.01em;
  }

  .card-desc {
    font-size: 0.95rem;
    color: var(--text-muted);
    line-height: 1.5;
  }

  /* ===== Connect ===== */
  .connect-heading {
    font-size: clamp(1.5rem, 3vw, 2.25rem);
    font-weight: 600;
    letter-spacing: -0.02em;
    margin-bottom: 2.5rem;
  }

  .links {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: center;
    margin-bottom: 2.5rem;
  }

  .link {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.75rem 1.25rem;
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    color: var(--text);
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 400;
    transition: border-color 0.3s ease, color 0.3s ease;
  }

  .link:hover {
    border-color: var(--text-muted);
    color: var(--accent);
  }

  .link svg {
    flex-shrink: 0;
    width: 20px;
    height: 20px;
  }

  .email-link {
    display: block;
    color: var(--text-muted);
    text-decoration: none;
    font-size: 1rem;
    margin-bottom: 3rem;
    transition: color 0.3s ease;
  }

  .email-link:hover {
    color: var(--text);
  }

  .footer {
    text-align: center;
  }

  .footer p {
    font-size: 0.85rem;
    color: var(--text-muted);
    font-weight: 300;
  }

  /* ===== Reveal Animation ===== */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease-out, transform 0.7s ease-out;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* Stagger cards */
  .card.reveal:nth-child(2) {
    transition-delay: 0.15s;
  }

  .card.reveal:nth-child(3) {
    transition-delay: 0.3s;
  }

  /* ===== Keyframes ===== */
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes bounceDown {
    0%, 100% {
      transform: rotate(45deg) translateY(0);
    }
    50% {
      transform: rotate(45deg) translateY(8px);
    }
  }

  /* ===== Responsive ===== */
  @media (min-width: 640px) {
    .cards {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 640px) {
    html {
      scroll-snap-type: none;
    }

    .section {
      min-height: auto;
      padding-top: 5rem;
      padding-bottom: 5rem;
    }

    .hero {
      min-height: 100vh;
      min-height: 100dvh;
    }

    .hero-photo img {
      width: 110px;
      height: 110px;
    }

    .card {
      padding: 1.5rem;
    }
  }
</style>
```

**Step 2: Commit**

```bash
git add index.html
git commit -m "feat: add CSS styles for redesigned site

Dark theme, scroll-snap, reveal animations, responsive layout.
Inter font, CSS custom properties, grid/flexbox."
```

---

### Task 4: Add JavaScript to index.html

**Files:**
- Modify: `index.html` — replace the `<!-- SCRIPT GOES HERE (Task 4) -->` comment

**Step 1: Replace `<!-- SCRIPT GOES HERE (Task 4) -->` with the script block**

```html
<script>
  // Scroll-triggered reveal animation
  const reveals = document.querySelectorAll('.reveal');

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, {
    threshold: 0.15,
    rootMargin: '0px 0px -50px 0px'
  });

  reveals.forEach(el => observer.observe(el));
</script>
```

**Step 2: Commit**

```bash
git add index.html
git commit -m "feat: add IntersectionObserver for scroll reveal animations"
```

---

### Task 5: Clean up unused images

**Files:**
- Delete: `images/background_bottom.png`
- Delete: `images/btn_contacto.png`
- Delete: `images/btn_facebook.png`
- Delete: `images/btn_github.png`
- Delete: `images/btn_linkedin.png`
- Delete: `images/btn_odesk.png`
- Delete: `images/btn_resume.png`
- Delete: `images/btn_stackoverflow.png`
- Delete: `images/btn_twitter.png`

Keep `images/img_santiago.png` as a fallback.

**Step 1: Remove unused image files**

```bash
cd /Users/khks381/Documents/WORK/Busta/busta117
git rm images/background_bottom.png images/btn_contacto.png images/btn_facebook.png images/btn_github.png images/btn_linkedin.png images/btn_odesk.png images/btn_resume.png images/btn_stackoverflow.png images/btn_twitter.png
```

**Step 2: Commit**

```bash
git commit -m "chore: remove unused image assets from old design"
```

---

### Task 6: Visual verification

**Step 1: Open the site in a browser**

```bash
open /Users/khks381/Documents/WORK/Busta/busta117/index.html
```

**Step 2: Verify checklist**

- [ ] Hero section: name, title, photo visible and centered
- [ ] Scroll down reveals About section with fade-in animation
- [ ] Cards section shows 3 cards with stagger animation
- [ ] Connect section shows 4 links (LinkedIn, GitHub, SO, Resume) + email + footer
- [ ] Footer shows "From Colombia / Based in Spain" with flags
- [ ] Mobile responsive: resize browser to phone width, sections stack properly
- [ ] All links open correct URLs in new tabs
- [ ] Resume PDF link works
- [ ] Email link opens mail client
- [ ] Scroll-snap works on desktop (sections align)
- [ ] Dark theme looks correct, text is readable

**Step 3: Fix any issues found, then final commit if needed**
