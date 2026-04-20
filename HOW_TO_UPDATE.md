# Udaya Ram Kumar — Portfolio Update Guide

Everything you need to update the site is in `index.html`. Look for the ✏️ comments.

---

## Personalizing your info

### 1. Hero tagline
Find `hero-tagline` and update your title and one-line pitch.

### 2. About section stats
Find `<!-- ✏️ UPDATE THESE NUMBERS -->` and update:
- Years of experience
- Projects shipped
- Technologies

### 3. Skills / Tech Stack
Find `<!-- ✏️ UPDATE SKILLS HERE -->` and swap in your actual stack.
Each `<span class="skill-tag">` is one tag. Add or remove freely.

---

## Updating experience (every time you get a new job)

Find `<!-- ✏️ ADD/EDIT EXPERIENCES HERE -->` in the `#experience` section.

**To add a new role**, copy this block and paste it at the TOP of the `.timeline` div:

```html
<div class="timeline-item reveal">
  <div class="timeline-period">2025 — Present</div>
  <div class="timeline-role">Your New Title</div>
  <div class="timeline-company">Company Name · Full-time</div>
  <p class="timeline-desc">
    What you built, what you achieved, measurable impact.
  </p>
  <div class="timeline-tags">
    <span class="timeline-tag">Tech1</span>
    <span class="timeline-tag">Tech2</span>
  </div>
</div>
```

---

## Adding a new project

Find `<!-- ✏️ ADD/EDIT PROJECTS HERE -->` in the `#projects` section.

**Copy this block** and paste inside `.projects-grid`:

```html
<div class="project-card reveal">
  <div class="project-icon">🔥</div>        <!-- Pick any emoji -->
  <div class="project-name">My New Project</div>
  <p class="project-desc">
    What it does, why it matters, tech used.
  </p>
  <div class="project-footer">
    <div class="project-stack">
      <span class="stack-chip">React</span>
      <span class="stack-chip">Node.js</span>
    </div>
    <div class="project-links">
      <a href="https://github.com/you/repo" class="project-link" target="_blank">
        <!-- GitHub SVG already in file — copy from existing card -->
      </a>
      <a href="https://yourproject.com" class="project-link" target="_blank">
        <!-- External link SVG already in file — copy from existing card -->
      </a>
    </div>
  </div>
</div>
```

---

## Updating social links

Find `<!-- ✏️ UPDATE YOUR SOCIAL LINKS & HANDLES -->` and update:
- `href="https://linkedin.com/in/YOUR_HANDLE"` → your LinkedIn URL
- `href="https://github.com/YOUR_HANDLE"` → your GitHub URL
- `href="https://twitter.com/YOUR_HANDLE"` → your X/Twitter URL
- Update the handle text inside `.social-link-handle`

---

## Setting up a real contact form (optional upgrade)

The form currently uses a `mailto:` fallback. To get form submissions in your inbox without the user opening their email client:

1. Go to **https://formspree.io** → Create free account → New form
2. Copy your form endpoint (looks like `https://formspree.io/f/XXXXXXXX`)
3. In `index.html`, find the `contactForm.addEventListener('submit', ...)` block
4. Replace the `mailto` logic with a fetch call:

```js
const res = await fetch('https://formspree.io/f/XXXXXXXX', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name, email, subject, message })
});
if (res.ok) { /* show success */ }
```

---

## Deploying to GitHub Pages

1. Create a repo named `YOUR_USERNAME.github.io` on GitHub
2. Push `index.html` to the `main` branch:
   ```bash
   git init
   git add index.html
   git commit -m "Initial portfolio"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io
   git push -u origin main
   ```
3. Go to **Settings → Pages → Branch: main → Save**
4. Your site goes live at `https://YOUR_USERNAME.github.io` within minutes

**Future updates:** just edit `index.html` and `git push` — the site updates automatically.

---

## Theming (colors)

All colors are in CSS custom properties at the top of `<style>`:

```css
--accent-1: #6e40c9;   /* purple — change to your brand color */
--accent-2: #2997ff;   /* blue */
--accent-3: #30d158;   /* green */
```

Change those three hex values to completely re-theme the entire site.
