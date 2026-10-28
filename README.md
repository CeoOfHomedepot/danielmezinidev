# Daniel Mezini — Developer Portfolio

Personal portfolio for game systems, backend integrations, and software development.

**Live site:** [danielmezinidev.com](https://danielmezinidev.com/)

## Run locally

The site uses plain HTML and CSS. There is no build step or JavaScript dependency.

From the repository root, run:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Open [localhost:8000](http://localhost:8000). Opening `index.html` directly also works.

## Structure

```text
index.html          Content, project overview, resume links, and contact details
css/style.css       Design tokens, layout, responsive and accessibility styles
assets/resume.pdf   Downloadable resume
assets/favicon.svg  Browser icon
CNAME               Custom domain for GitHub Pages
```

The legacy `asset/resume.pdf` path remains available for existing links. If the resume is replaced, update both PDF copies together.

## Design and accessibility

- All content and navigation work without JavaScript.
- Native section links support direct URLs and browser history.
- Layout adapts to narrow screens without a fixed sidebar.
- Keyboard users get a skip link, visible focus indicators, and a native disclosure for engineering notes.
- Reduced-motion preferences disable smooth scrolling and transitions.
- System fonts avoid a third-party font request; print styles provide a text layout.
- The resume has direct view and download links instead of depending on an embedded PDF viewer.

## Updating content

Edit project descriptions in `index.html` and shared styles in `css/style.css`. Keep published claims tied to evidence. The entity-framework overview describes the implementation from the original portfolio; it is not a published performance benchmark. Add benchmark numbers only with hardware, workload, measurement method, and reproducible results.

The framework source URL previously linked from the site was unavailable when checked. The interface therefore links to the existing Roblox demonstration and describes source availability in the engineering notes. Add public project repositories or demo recordings when available; do not use disabled or placeholder links.

Education and the dated RPG and Discord projects come from the existing resume. Recheck the expected graduation date and availability when updating the resume. Update the footer year when appropriate.

## Deployment and checks

GitHub Pages serves this static site with the domain in `CNAME`. No application server or package installation is needed for production.

Before publishing changes:

1. Check desktop and narrow layouts, including 320px, 390px, and tablet widths.
2. Navigate with the keyboard and open the engineering notes with Enter or Space.
3. Follow the section links and use browser Back to verify navigation.
4. Open and download the resume; check the email, telephone, Roblox, and GitHub destinations.
5. Check reduced-motion and print layouts. Confirm long text does not overflow.
6. Verify that new project claims have supporting material and all local asset links resolve.

The backend specialization section reflects Daniel's confirmed experience with inventories, trading, guild roles, server-side combat calculations and client visuals, world/zone handling, and the modular quest/event/NPC systems described in his earlier portfolio.
