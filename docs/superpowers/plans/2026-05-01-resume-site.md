# Resume Site Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single-file responsive personal resume website for 院耀辉 at `E:\JIANLI\index.html`.

**Architecture:** One self-contained HTML document with semantic sections, inline CSS, and inline JavaScript. CSS handles layout, theme, hover states, and entrance animations; JavaScript only handles navigation state, scroll effects, skill bar activation, and back-to-top visibility.

**Tech Stack:** HTML5, inline CSS, vanilla JavaScript, inline SVG/CSS icons, no external dependencies.

---

## File Structure

- Create: `E:\JIANLI\index.html`
  - Owns all markup, style, and interaction.
  - Contains all resume content exactly from the approved spec.
- Reference: `E:\JIANLI\docs\superpowers\specs\2026-05-01-resume-site-design.md`
  - Source of design constraints and acceptance criteria.

## Implementation Tasks

### Task 1: Create Semantic HTML Skeleton

**Files:**
- Create: `E:\JIANLI\index.html`

- [ ] **Step 1: Create the base document**

Add the HTML document with `html`, `head`, `body`, viewport metadata, title, and empty semantic regions:

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>院耀辉｜AI训练师</title>
  <style>
  </style>
</head>
<body>
  <nav class="top-nav" aria-label="页面导航"></nav>
  <main>
    <section id="hero" class="section hero-section"></section>
    <section id="advantages" class="section"></section>
    <section id="education" class="section"></section>
    <section id="experience" class="section"></section>
    <section id="projects" class="section"></section>
    <section id="campus" class="section"></section>
    <section id="skills" class="section"></section>
    <section id="honors" class="section"></section>
  </main>
  <button class="back-to-top" type="button" aria-label="回到顶部">↑</button>
  <footer class="footer">© 2025 院耀辉 · Built with AI</footer>
  <script>
  </script>
</body>
</html>
```

- [ ] **Step 2: Add navigation links**

Add links for each section:

```html
<nav class="top-nav" aria-label="页面导航">
  <div class="nav-inner">
    <a class="brand" href="#hero">院耀辉</a>
    <div class="nav-links">
      <a href="#advantages">优势</a>
      <a href="#education">教育</a>
      <a href="#experience">经历</a>
      <a href="#projects">项目</a>
      <a href="#campus">校园</a>
      <a href="#skills">技能</a>
      <a href="#honors">荣誉</a>
    </div>
  </div>
</nav>
```

- [ ] **Step 3: Add all resume section content**

Fill sections with the exact approved resume content:

- Hero: name, role, political status, city, phone, email, identity.
- Core advantages: four original advantage paragraphs.
- Education: school, major, degree, dates, course tags, graduation design.
- Experience: 康保县医疗保障局见习生 and the three bullet points.
- Projects: two project cards with role/tools/results from the spec.
- Campus: two campus experience entries.
- Skills/certificates: five skills and two certificates.
- Honors: eight honor entries in reverse chronological order.

- [ ] **Step 4: Manual content check**

Open `E:\JIANLI\index.html` in a text editor and confirm no content appears that is not present in the spec.

### Task 2: Implement Visual System and Responsive Layout

**Files:**
- Modify: `E:\JIANLI\index.html`

- [ ] **Step 1: Add root theme variables and global reset**

Add CSS variables for the required colors, system font stack, spacing, and base styles.

- [ ] **Step 2: Implement desktop layout**

Create:

- Fixed centered navigation with transparent default state.
- Hero two-column grid.
- Contact card on the right.
- 2x2 advantage grid.
- Timeline styles for experience and campus.
- Two-column project cards.
- Two-column skills/certificates grid.
- Honor award grid.

- [ ] **Step 3: Implement mobile layout**

Add media queries under `768px`:

- All major grids become one column.
- Navigation links become horizontally scrollable.
- Hero typography scales down.
- Cards keep stable padding and no overlapping text.

- [ ] **Step 4: Add decorative background**

Use CSS pseudo-elements and gradients only:

- Subtle blue/green line glow behind hero.
- Low-contrast grid or radial accent that does not dominate the page.

### Task 3: Implement Interactions

**Files:**
- Modify: `E:\JIANLI\index.html`

- [ ] **Step 1: Add CSS transitions and entrance animation**

Use `.reveal` and staggered `animation-delay` classes for sections and cards.

- [ ] **Step 2: Add card hover states**

Cards should translate upward slightly and deepen border/shadow on hover.

- [ ] **Step 3: Add JavaScript scroll behavior**

Implement vanilla JS for:

- Smooth navigation behavior through CSS `scroll-behavior: smooth`.
- Navbar `is-scrolled` class after scroll.
- Active nav link using `IntersectionObserver`.
- Skill progress bars animate when visible.
- Back-to-top button visibility and click handler.

### Task 4: Verify Locally

**Files:**
- Verify: `E:\JIANLI\index.html`

- [ ] **Step 1: Check file exists**

Run:

```powershell
Test-Path E:\JIANLI\index.html
```

Expected: `True`

- [ ] **Step 2: Check no external dependencies**

Run:

```powershell
Select-String -Path E:\JIANLI\index.html -Pattern "https://|http://|cdn|fonts.googleapis|unpkg|jsdelivr"
```

Expected: no matches.

- [ ] **Step 3: Check required links**

Run:

```powershell
Select-String -Path E:\JIANLI\index.html -Pattern "tel:19531238160|mailto:19531238160@163.com|© 2025 院耀辉 · Built with AI"
```

Expected: three matches.

- [ ] **Step 4: Manual browser check**

Open `E:\JIANLI\index.html` in a browser and verify:

- Desktop is two-column where specified.
- Mobile width collapses to one column.
- Navigation highlights while scrolling.
- Skill bars animate into view.
- Back-to-top appears after scrolling.
- Text does not overlap.
