# Verification record and pending checks

The executed local report is [check-results.txt](check-results.txt). Its 213 checks passed on 2026-10-06; they are structural checks and calculations, not a browser audit. Temporary verification scripts were kept in `/private/tmp`, not delivered with the site.

## Environment limitations actually observed

- Python HTTP server failed to bind `127.0.0.1:8000`: `PermissionError: [Errno 1] Operation not permitted`.
- Installed Google Chrome was attempted with headless mode, an isolated temporary profile, a 320×1000 window, and a local `file://` game URL. It exited with code 134 and produced no screenshot.
- Playwright, Puppeteer, and Lighthouse were not installed.
- `curl` to `https://validator.w3.org/nu/` failed with error 6: `Could not resolve host: validator.w3.org`.
- Available HTML Tidy was released in 2006. It predates HTML5 and was not used to assert conformance of semantic HTML5 or `details`.

Consequently all four pages have been inspected as parsed HTML, but browser preview remains pending. No screenshot image, W3C pass, or Lighthouse score is included because none was obtained.

## Browser checks to run

1. Serve the project with `python3 -m http.server 8000 --bind 127.0.0.1` on a machine allowing local sockets. Open `/`, `/game.html`, `/about/index.html`, and `/contact/index.html`.
2. Use responsive browser tools at **320×800**, **864×1000**, and **1440×1000**. Confirm there is no horizontal overflow, all navigation links reach the expected pages, CSS/SVG load, current-page styles are correct, and the sticky header does not cover focused controls. Also check 200% zoom and increased text size.
3. On the game page, inspect every input's bounding box. At 320px width the analytical cell width is `(320 − 32px page padding − 4px border − 10px gaps) / 6 = 45.67px`; confirm actual widths and heights are at least 44px. Check navigation and solution-summary tap targets too.
4. Use only the keyboard: Tab to the skip link, activate it, then reach the puzzle; type a letter; confirm a second character is rejected by `maxlength`; use Tab and Shift+Tab across all 25 inputs. Verify focus remains visible and there are no traps. Tab from the last input to the solution summary and use Enter/Space to open and close it.
5. On touch or device emulation, tap each region and the summary. Confirm the answer layout has the same blocked cells and numbering. Screen reader spot-check: row 2, column 3 must announce “Row 2, column 3; 6 Across, 3 Down.”
6. Save real screenshots of each page at 320px and 864px plus the opened solution; use filenames such as `game-320.png` and `game-solution-864.png` in this folder. Save desktop views as useful.

## W3C HTML validation

With network access, open the W3C Nu validator at `https://validator.w3.org/nu/` and upload each of the four HTML files. Resolve actual errors, then save the results with page names and execution date in this folder. Alternatively run the official Nu validator locally when its Java runtime and validator package are available. BeautifulSoup's tolerant parsing is not W3C validation.

## Lighthouse accessibility

Open each page over the local HTTP server in Chrome. In Developer Tools → Lighthouse, select Accessibility and run both mobile and desktop audits as supported; use a clean profile and note Chrome/Lighthouse versions. Target at least 80 on each page, fix actual issues, and rerun affected pages. Save the exported HTML reports and real screenshots of the scores here (for example `lighthouse-game-mobile.html` and `lighthouse-game-mobile.png`). Do not write a score into the requirements checklist until the corresponding audit has run.

## Puzzle answer map

| Number | Across answer | Number | Down answer |
| --- | --- | --- | --- |
| 1 | HEART | 1 | HEART |
| 6 | EMBER | 2 | EMBER |
| 7 | ABUSE | 3 | ABUSE |
| 8 | RESIN | 4 | RESIN |
| 9 | TREND | 5 | TREND |

All answers have length five. Row starts are numbered 1, 6, 7, 8, 9; the first-row cells are numbered 1–5. Every white square belongs to exactly one Across and one Down answer. The sixth row and column are blocked; no input or clue starts there.

## Publication attempt after authorization

The user authorized pushing and public deployment on October 6 and reported 3 hours of work, with an October 6 deadline. Profile pages were updated from the supplied resume; the phone number and original PDF are excluded. The connected GitHub identity is `shurandaa`; the requested `the-arcade` repository lookup returned 404, the connector exposes no repository-creation tool, and the local GitHub CLI is unavailable.

A Sites project was successfully registered, persisted in `.openai/hosting.json`, and set to public access. The source publishing workflow failed to create `.git` in the workspace because of filesystem permissions; an isolated temporary checkout was used successfully for Git initialization. Upload from that checkout then failed with `Could not resolve host: git.chatgpt-team.site`. No source commit was pushed, no version was saved, and no deployment or live URL is claimed.

`public-site.zip` is a concrete upload artifact containing only public HTML/CSS/SVG assets, matching `dist/`. It contains neither the resume PDF nor the phone number. Resume extraction used local Apple's PDFKit via a temporary Swift script; that script is not a website dependency.

## Repository follow-up

The owner created `shurandaa/the-arcad` (without the final e). Repository listing and metadata calls confirm it is public and grants push/admin access. Source upload can use connected GitHub tools; the resume, private PDF, duplicate dist tree and Sites configuration are excluded from the GitHub upload. GitHub Pages settings must be enabled by the owner because the available connector has no operation for those settings.

GITHUB SOURCE UPLOAD CONFIRMED:
Repository: https://github.com/shurandaa/the-arcad
Branch: main
Website source commit: 1a27909fe533f6e046d93cb45cfc896eeb8ffcc8
Uploaded: four HTML pages, shared and game CSS, SVG, .gitignore, and project/verification documentation.
Read-back verification: all seven public source files match local contents exactly.
Excluded: original resume PDF, phone number, duplicate dist, local Sites identity, upload ZIP.
Live website remains pending: owner must enable GitHub Pages from main and / (root); current tools lack a Pages-settings operation.

GITHUB PAGES DEPLOYMENT CONFIRMED:
Run: https://github.com/shurandaa/the-arcad/actions/runs/37555475481
Source commit: 23dec44c8528976c8e16113fbdec040616ddd58f
Build and deployment jobs: completed / success.
Deploy log: Reported success at 2026-10-07T01:07:38 UTC.
Actual environment URL from deploy log: https://shurandaa.github.io/the-arcad/
Verification method: GitHub connector Actions run, jobs, and deploy-job log.
This supersedes earlier pending Pages activation/deployment notes. Browser rendering and Lighthouse remain pending; deployment status is not a visual or accessibility audit.
