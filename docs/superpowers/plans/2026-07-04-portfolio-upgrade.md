# ISSS608-VAA Portfolio Upgrade Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Upgrade the ISSS608-VAA Quarto website into a more practical, visually polished, professional, and exploratory visual analytics portfolio.

**Architecture:** Keep the existing Quarto website structure and add a portfolio layer through Markdown/HTML/CSS. Preserve all existing hands-on exercise URLs and avoid editing analytical R code. Use one new gallery page plus shared CSS components so the site feels coherent without destabilising exercise rendering.

**Tech Stack:** Quarto website, QMD, YAML, HTML snippets, CSS, existing Sketchy theme.

---

## File Structure

- Modify `/Users/yangyang/yyangcrl/ISSS608-VAA/index.qmd`: keep the hero and add exploratory portfolio sections.
- Create `/Users/yangyang/yyangcrl/ISSS608-VAA/hands-on-gallery.qmd`: visual exercise gallery with grouped cards.
- Modify `/Users/yangyang/yyangcrl/ISSS608-VAA/about.qmd`: replace placeholder content with a professional profile.
- Modify `/Users/yangyang/yyangcrl/ISSS608-VAA/_quarto.yml`: add the gallery link and group the hands-on menu.
- Modify `/Users/yangyang/yyangcrl/ISSS608-VAA/styles.css`: add reusable portfolio, gallery, tag, timeline, and navigation styles.
- Optionally modify hands-on exercise QMD files only to append low-risk final navigation blocks; skip if full render risk is high.

### Task 1: Prepare Working Copies

**Files:**
- Read: `/Users/yangyang/yyangcrl/ISSS608-VAA/index.qmd`
- Read: `/Users/yangyang/yyangcrl/ISSS608-VAA/about.qmd`
- Read: `/Users/yangyang/yyangcrl/ISSS608-VAA/_quarto.yml`
- Read: `/Users/yangyang/yyangcrl/ISSS608-VAA/styles.css`
- Create local editable copies under `/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/`

- [ ] **Step 1: Copy current files into the writable workspace**

Run:

```bash
mkdir -p "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade"
cp /Users/yangyang/yyangcrl/ISSS608-VAA/index.qmd "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/index.qmd"
cp /Users/yangyang/yyangcrl/ISSS608-VAA/about.qmd "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/about.qmd"
cp /Users/yangyang/yyangcrl/ISSS608-VAA/_quarto.yml "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/_quarto.yml"
cp /Users/yangyang/yyangcrl/ISSS608-VAA/styles.css "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/styles.css"
```

Expected: local working copies exist.

### Task 2: Homepage Portfolio Sections

**Files:**
- Modify local copy: `/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/index.qmd`

- [ ] **Step 1: Replace the lower homepage content with portfolio sections**

Use the existing hero and add these sections after the stats block:

```markdown
## Explore by Method

:::: vaa-method-grid
::: vaa-method-card
[Statistical Graphics]{.vaa-tag} [Foundations]{.vaa-tag}
### See the Grammar of Visual Analytics
From basic ggplot2 layers to uncertainty-aware statistical graphics, these exercises build the foundation for reading and constructing analytical visuals.
[Start with Exercise 1](Hands-on_Ex/Hands-on_Ex01/Hands-on_Ex01.html)
:::
::::
```

Expected: homepage links visitors into methods, journey, and featured work.

### Task 3: Hands-on Gallery Page

**Files:**
- Create: `/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/hands-on-gallery.qmd`

- [ ] **Step 1: Create grouped gallery cards**

Create a QMD page with front matter:

```yaml
---
title: "Hands-on Exercise Gallery"
format:
  html:
    toc: false
---
```

Add cards for all 20 hands-on exercises, grouped into Foundations, Statistical Visualisation, Interactive Visualisation, Network/Text/Time, Geospatial Analytics, and Dashboard Design.

Expected: every hands-on exercise has one visible card and one valid link.

### Task 4: About Page

**Files:**
- Modify: `/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/about.qmd`

- [ ] **Step 1: Replace placeholder content**

Replace the page with a professional profile for Yang Yang, including portfolio purpose, tools, methods, and learning reflection.

Expected: no `1 + 1` placeholder remains.

### Task 5: Navbar Configuration

**Files:**
- Modify: `/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/_quarto.yml`

- [ ] **Step 1: Add gallery and grouped hands-on navigation**

Add a top-level `Hands-on Gallery` link and keep existing exercise links under grouped headings.

Expected: all existing exercise href values remain unchanged.

### Task 6: Shared Visual System

**Files:**
- Modify: `/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/styles.css`

- [ ] **Step 1: Add reusable CSS classes**

Add styles for:

```css
.vaa-section-kicker {}
.vaa-method-grid {}
.vaa-method-card {}
.vaa-tag {}
.vaa-timeline {}
.vaa-timeline-item {}
.vaa-gallery-grid {}
.vaa-gallery-card {}
.vaa-feature-grid {}
.vaa-profile-panel {}
.vaa-page-actions {}
```

Expected: responsive card/timeline layouts work on desktop and mobile.

### Task 7: Copy Into Project And Render

**Files:**
- Copy to `/Users/yangyang/yyangcrl/ISSS608-VAA/`

- [ ] **Step 1: Copy edited files into the project**

Run:

```bash
cp "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/index.qmd" /Users/yangyang/yyangcrl/ISSS608-VAA/index.qmd
cp "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/about.qmd" /Users/yangyang/yyangcrl/ISSS608-VAA/about.qmd
cp "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/_quarto.yml" /Users/yangyang/yyangcrl/ISSS608-VAA/_quarto.yml
cp "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/styles.css" /Users/yangyang/yyangcrl/ISSS608-VAA/styles.css
cp "/Users/yangyang/Documents/VAA HANDSON/portfolio_upgrade/hands-on-gallery.qmd" /Users/yangyang/yyangcrl/ISSS608-VAA/hands-on-gallery.qmd
```

Expected: project files are updated.

- [ ] **Step 2: Render the site**

Run:

```bash
quarto render
```

Expected: render completes without errors.

### Task 8: Visual And Link Verification

**Files:**
- Read rendered files under `/Users/yangyang/yyangcrl/ISSS608-VAA/_site`

- [ ] **Step 1: Confirm required outputs exist**

Run:

```bash
test -f _site/index.html
test -f _site/hands-on-gallery.html
test -f _site/about.html
```

Expected: all commands return success.

- [ ] **Step 2: Check rendered links**

Run:

```bash
rg -n "hands-on-gallery|Hands-on_Ex/Hands-on_Ex10|about.html" _site/index.html _site/hands-on-gallery.html _site/about.html
```

Expected: key links are present.

- [ ] **Step 3: Capture desktop and mobile screenshots**

Run Chrome headless for:

```bash
file:///Users/yangyang/yyangcrl/ISSS608-VAA/_site/index.html
file:///Users/yangyang/yyangcrl/ISSS608-VAA/_site/hands-on-gallery.html
file:///Users/yangyang/yyangcrl/ISSS608-VAA/_site/about.html
```

Expected: text is readable, cards do not overlap, mobile layout stacks cleanly.

## Self-Review

- Spec coverage: homepage, gallery, About page, navbar, CSS, compatibility, and verification are covered.
- Placeholder scan: no TBD/TODO/FIXME placeholders.
- Scope check: plan avoids analytical R code rewrites and preserves existing URLs.
