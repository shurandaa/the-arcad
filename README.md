# The Arcade

A small, English-language personal arcade built with HTML and CSS only. The site includes a landing page, a playable mini crossword, an About page, and a Contact page. The About and Contact pages use Shuran Zhao’s supplied resume. The owner authorized publication of the profile, email, GitHub, and LinkedIn; the phone number and original PDF are not published.

## Project structure

```text
index.html                 Landing page and four game slots
 game.html                 Playable crossword and solution
 game/game.css             Crossword-specific styles
 about/index.html          Resume-based profile and project notebook
 contact/index.html        Email, GitHub and LinkedIn contacts
 assets/site.css           Shared design tokens, layouts, responsive styles
 assets/mark.svg           Original local grid mark and favicon
 verification/check-results.txt  Actual local check results and limitations
 verification/README.md    Browser, validator, and Lighthouse follow-up
 README.md                 Preview and deployment instructions
 REQUIREMENTS.md           Grading checklist and verification status
 WRITEUP.md                Implementation reflection and personal fields
 .gitignore                Excludes local secrets, private resume and development artifacts
 dist/                     Exact public assets for Sites static deployment
 .openai/hosting.json       Registered Sites identity and static configuration
 verification/public-site.zip  Public assets only, ready for static upload
```

## Local preview

Open `index.html` directly in a browser; relative page, stylesheet, and image paths support `file://` preview. For a local HTTP preview, run this from the project root in an environment that allows local sockets:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Visit `http://127.0.0.1:8000/`. This environment rejected socket binding, and Chrome headless exited without rendering. The site needs no installation or build step.

## Actual functionality

- Shared sticky navigation, current-page highlighting, skip link, and visible keyboard focus.
- Twenty-five single-character inputs in a 6×6 CSS Grid, with eleven blocked cells along the bottom and right edges.
- Five five-letter Across answers and five Down answers. This is intentionally a word-square puzzle: both directions use HEART, EMBER, ABUSE, RESIN, and TREND, with original clues.
- Associated labels identify each input's row, column, and Across/Down clues. Tab follows row order; Shift + Tab moves backward.
- A native `details`/`summary` disclosure reveals the numbered solution and textual answer lists.
- Three clearly labeled future game slots. No unsupported game links are presented.

Inputs display uppercase characters through CSS, but the stored character is not normalized and non-letter characters are not automatically rejected. There is no automatic advancement, correction, scoring, reset control, or persistent progress. Browser restoration may retain form values, but the site does not save them. The Contact page provides the owner-supplied email, GitHub, and LinkedIn links. External destinations have not been independently tested.

## Verification

Executed on 2026-10-06: **213 local checks passed** using Python 3, BeautifulSoup's HTML parser, ElementTree, and direct WCAG contrast calculations. Checks cover relative links and assets on all four pages, IDs, landmarks, image alt attributes, puzzle letters and mappings, input/label associations, solution numbering, and absence of JavaScript/runtime packages. Checked text color pairs exceed 4.5:1. Analytical sizing gives 45.67px cells at a 320px viewport; this is not a browser measurement.

See [actual results](verification/check-results.txt) and [follow-up instructions](verification/README.md). W3C validation, rendered previews at 320px/864px/wider widths, keyboard/touch testing, Lighthouse score, and genuine screenshots are **pending**. Local parsing does not establish W3C conformance or browser accessibility. No passing browser result or screenshot has been fabricated.

## Static deployment

The owner authorized pushing and public deployment on October 6, 2026. A Sites project has been registered with public access, but no version has been uploaded or deployed. The source workflow was attempted from an isolated writable temporary checkout after the workspace denied writing `.git`; upload then failed because `git.chatgpt-team.site` could not be resolved. The saved `.openai/hosting.json` identifies the same project for a later retry; do not register a replacement site. The owner created the public `shurandaa/the-arcad` repository (note the spelling). It is accessible through the connected GitHub tools, which successfully uploaded all source and documentation to `main` despite local DNS restrictions.

Complete the pending browser checks when the required tools become available. Any static host that serves `index.html` and nested directories can serve the project without a build. Upload the four HTML pages plus `assets/`, `game/game.css`, `about/`, and `contact/` with their relative paths intact; documentation and verification artifacts need not be public.

For GitHub Pages after authorization:

1. Create or select the owner's GitHub repository; initialize Git locally if needed and commit the project.
2. Set its real remote and push to the selected branch.
3. In repository Settings → Pages, choose deployment from that branch and `/ (root)`.
4. Open the URL reported by GitHub, then test all four pages and their assets there. Relative paths also support a project site under a repository subpath.

Do not invent a repository name or published URL before those actions succeed.

- GitHub repository: **https://github.com/shurandaa/the-arcad** (verified accessible public repository).
- Live site: **https://shurandaa.github.io/the-arcad/** (GitHub Pages deployment succeeded).

## Resources and authorship

All delivered HTML, CSS, the local SVG mark, and puzzle clues were created for this implementation with Codex assistance. No third-party code, design template, puzzle source, icon set, web font, JavaScript, styling framework, or runtime package was imported. System fonts are used (system UI and Georgia, with fallbacks). BeautifulSoup was already available and used only as a development-time inspection tool; verification scripts remained outside the delivered repository.

## Current owner-provided information

Profile content is sourced from the supplied `SHURAN ZHAO.pdf`. This source document remains local and is excluded by `.gitignore`; it is absent from `dist/` and `verification/public-site.zip`. The archive contains only the four HTML pages, shared CSS, game CSS, and the original SVG. The owner reported **3 hours** of work and a deadline of **October 6**; no early-submission credit or successful submission is claimed.

## Next publication steps

1. The public repository is https://github.com/shurandaa/the-arcad. Use this exact repository name; it differs from the originally suggested `the-arcade`.
2. Source upload to `main` succeeded through the GitHub connector. Enable GitHub Pages from `main` and `/ (root)` using repository Settings → Pages. Sites remains an optional alternative if network access for its source workflow is restored.
3. For a manual static-host upload, extract `verification/public-site.zip` and upload its contents. This archive does not include the private resume or documentation.
4. Record the actual repository and successful live-site URLs and finish the pending browser and Lighthouse checks.

## GitHub Pages activation

The owner enabled GitHub Pages from `main` and `/ (root)`. The actual [Pages deployment](https://github.com/shurandaa/the-arcad/actions/runs/37555475481) completed successfully for source commit `23dec44c8528976c8e16113fbdec040616ddd58f`. Its deploy-job log reported success and the environment URL https://shurandaa.github.io/the-arcad/ at 2026-10-07 01:07:38 UTC (October 6 in America/Los_Angeles). Deployment success does not establish browser layout, interaction, Lighthouse, or validator results; these remain pending.

The website source commit is `1a27909fe533f6e046d93cb45cfc896eeb8ffcc8`. All seven public HTML/CSS/SVG files were read back through the GitHub connector and matched local contents exactly. `dist/`, `.openai/hosting.json`, and the upload ZIP are local-only convenience artifacts and are not part of the GitHub source tree.
