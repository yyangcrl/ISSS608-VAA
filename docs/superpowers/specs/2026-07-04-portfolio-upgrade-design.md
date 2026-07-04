# ISSS608-VAA Portfolio Upgrade Design

Date: 2026-07-04

## Goal

Upgrade the ISSS608-VAA Quarto website from a functional coursework site into a practical, visually polished, professional, and exploratory visual analytics portfolio. The upgrade should preserve the current Sketchy/teal studio theme and avoid destabilising working hands-on exercise content.

## Approved Scope

The upgrade will focus on the website shell, portfolio framing, navigation, and lightweight page-level polish.

Included:

- Improve the homepage with richer exploratory sections.
- Add a new hands-on exercise gallery page.
- Replace the placeholder About page with a professional portfolio profile.
- Improve the navbar structure while preserving existing URLs.
- Extend the shared CSS visual system with reusable portfolio components.
- Add light, consistent finishing blocks to hands-on pages where safe.
- Render and visually verify the site after changes.

Excluded:

- Rewriting analytical R code inside exercises.
- Changing datasets or generated analytical outputs.
- Removing existing pages or changing existing exercise URLs.
- Heavy redesign of every exercise page.

## Existing Context

The project is a Quarto website at `/Users/yangyang/yyangcrl/ISSS608-VAA`. It currently contains:

- `index.qmd` with a visual analytics portfolio cover page.
- `about.qmd`, currently placeholder content with a test R chunk.
- `_quarto.yml` with a long hands-on exercise dropdown.
- `styles.css` defining the current visual system.
- Twenty hands-on exercise pages under `Hands-on_Ex`.
- Take-home exercise and VAST challenge pages that should not be the focus of this upgrade.

## Recommended Approach

Use the Full Portfolio Upgrade approach:

- Keep the current cover page direction.
- Add structured browsing through a hands-on gallery.
- Add homepage sections that help visitors explore by method and learning journey.
- Make the About page professional and complete.
- Improve navigation groupings without breaking direct links.
- Keep exercise content stable, adding only low-risk portfolio framing where appropriate.

This is preferred over a minimal polish because it addresses navigation and discovery, and preferred over a deep exercise redesign because it avoids unnecessary risk to already-rendering analytical content.

## Site Structure

The upgraded site will have:

- Home: visual cover, explore-by-method, learning journey, featured work, and quick links.
- Hands-on Gallery: a new `hands-on-gallery.qmd` page with all hands-on exercises shown as cards.
- Hands-on Exercise menu: grouped entries for easier scanning.
- Take-home Exercise menu: preserved with tidy labels.
- About: professional profile page for Yang Yang and the portfolio.

Existing hands-on exercise URLs must remain valid.

## Homepage Design

The homepage will keep the existing hero and add:

- Explore by Method cards:
  - Statistical Graphics
  - Interactivity
  - Network and Text Analytics
  - Time-oriented Data
  - Geospatial Analytics
  - Dashboard Design
- Learning Journey timeline:
  - Foundations
  - Statistical visualisation
  - Interactivity
  - Network and text analysis
  - Time-oriented data
  - Geospatial analytics
  - Dashboard design
- Featured Work section:
  - Latest dashboard exercise
  - Network/text exercises
  - Geospatial exercises
  - Exercise gallery link

The homepage should feel exploratory without becoming a landing-page advertisement.

## Hands-on Gallery Design

Create `hands-on-gallery.qmd` with:

- A concise page intro.
- Grouped exercise sections:
  - Foundations
  - Statistical Visualisation
  - Interactive Visualisation
  - Network, Text, and Time
  - Geospatial Analytics
  - Dashboard Design
- One card per hands-on exercise, containing:
  - Exercise number/name.
  - Topic label.
  - Two to four method tags.
  - One short description.
  - Link to the existing exercise page.

The gallery should make browsing the coursework easier than using the long dropdown alone.

## About Page Design

Replace `about.qmd` with a polished profile page containing:

- Yang Yang as the portfolio author.
- Course and portfolio purpose.
- Methods and tools used.
- A short learning reflection.
- A compact list of strengths demonstrated by the portfolio.

Remove the placeholder `1 + 1` code chunk.

## Navigation Design

Update `_quarto.yml` so visitors can access:

- Home
- Hands-on Gallery
- Hands-on Exercise grouped dropdown
- Take-home Exercise dropdown
- About

The long hands-on menu should be grouped by learning area where Quarto menu structure permits it. If nested grouping creates compatibility issues, use separator-style text labels while preserving all page links.

## Exercise Page Finishing Blocks

Where safe, hands-on pages may receive a lightweight closing block containing:

- Key takeaway.
- Practical use.
- Previous/next exercise navigation.

This must not alter executable analysis chunks or analytical conclusions. If a page is structurally fragile, skip the finishing block for that page rather than risk breaking rendering.

## Visual System

Extend `styles.css` with reusable classes for:

- Section headers.
- Portfolio cards.
- Method tags.
- Gallery grids.
- Timeline steps.
- Featured work blocks.
- Exercise closing blocks.
- Responsive mobile layouts.

The CSS should stay compatible with Quarto HTML output and the existing Sketchy theme. The palette should continue using teal, muted ink, paper, gold, red, and blue accents rather than introducing a different visual identity.

## Compatibility And Safety

Implementation must:

- Preserve existing exercise URLs.
- Avoid changing datasets.
- Avoid heavy edits to working R code.
- Use Quarto/Markdown/HTML/CSS only for the new portfolio layer.
- Keep mobile layouts readable.
- Avoid text overlap and oversized headings inside compact cards.
- Keep card border radius at 8px or less.

## Verification Plan

After implementation:

- Run a full Quarto render from the project root.
- Confirm `index.html`, `hands-on-gallery.html`, and `about.html` are created.
- Check a sample of hands-on exercise pages still renders.
- Verify navbar links resolve in the rendered site.
- Capture desktop and mobile screenshots of the homepage and gallery.
- Fix any broken links, overflow, duplicated titles, or visual layout problems before completion.

## Success Criteria

The upgrade is successful when:

- The site feels like a coherent visual analytics portfolio, not only a submission folder.
- Visitors can browse exercises visually by method and topic.
- The About page is complete and professional.
- The homepage provides clear exploratory paths.
- Existing exercise content and links continue to work.
- The full site renders without errors.
