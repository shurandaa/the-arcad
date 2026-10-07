# Requirements and verification

Status key: **Complete** = present in source; **Local check passed** = executed inspection; **Pending** = external action or unavailable browser/network verification. Full evidence is in `verification/check-results.txt`; local checks do not substitute for W3C or Lighthouse.

| Grading category | Weight | Implementation and status |
| --- | --- | --- |
| Repository / code quality / live URL | 10% | **Complete:** readable static source, `.gitignore`, README, requirements, writeup, verification notes; no scripts/frameworks/runtime dependencies. **Local check passed:** prohibited runtime scan. **Verified:** public GitHub repository `shurandaa/the-arcad`. **Pending:** successful live URL; local DNS blocked shell uploads, but the connected GitHub tools successfully uploaded source and documentation to `main`. Sites identity is saved in `.openai/hosting.json` and public assets are ready in `dist/`. |
| Four pages / file organization | 10% | **Complete:** `index.html`, `game.html`, `about/index.html`, `contact/index.html`; shared `assets/site.css`, page-specific `game/game.css`, local SVG. **Local check passed:** all four parsed, relative assets and links resolve. **Pending:** rendered previews. |
| Navigation | 15% | **Complete:** same `nav` and real link list on every page, owner name in title, `aria-current`, sticky header, skip link, focus indicator, mobile arrangement. **Local check passed:** four page links and exactly one current item per page. **Pending:** keyboard and scrolling browser checks. |
| Puzzle | 15% | **Complete:** 6×6 CSS Grid, 25 text inputs with `maxlength="1"`, 11 blocked cells, corner numbering, Across/Down lists, accurate labels, native solution reveal with matching grid. **Local check passed:** every crossing, answer, input association, clue mapping, and solution number/letter. Original clues use an intentional five-word square, with repeated Across/Down answers disclosed. **Pending:** live entry, Tab/Shift+Tab, keyboard/touch disclosure. |
| Mobile design | 10% | **Complete:** responsive shared/game CSS, fluid typography and artwork, stacked navigation and puzzle layout. **Local check passed:** analytical 320px sizing, 45.67px cells including margins/gaps/borders. Navigation controls are at least 44px high; primary action 48px; summary 48px. **Pending:** browser measurements, overflow and reachability at 320px, 864px, and desktop. |
| HTML elements | 10% | **Complete / Local check passed:** header, nav, main, footer, section, a, img, p, lists, label, input. `about/index.html` contains a meaningful nested h1→h6 project notebook; other pages use relevant levels. **Pending:** W3C validation (DNS unavailable). |
| CSS features | 10% | **Complete:** tokens and font-family/background/margin/padding in `assets/site.css`; sticky/relative positioning; navigation flex; puzzle grid; media queries; hover, focus-visible, focus-within and open states; contact `::before` and clue `::marker`; restrained transition/transform; reduced-motion rule. |
| Accessibility | 10% | **Complete:** English language, native controls, visible focus, accurate labels, decorative empty alt, current-page markup, skip link, responsive native disclosure. **Local check passed:** text contrast pairs ≥4.5:1, image alt attributes and labels. **Pending:** actual keyboard/touch checks, assistive technology testing, Lighthouse ≥80 and genuine screenshots. No Lighthouse score is claimed. |
| Design | 10% | **Complete:** coherent warm paper/neutral ramp/forest-green accent, centralized type and spacing scale, restrained original grid mark, readable paragraphs and limited decoration. **Pending:** browser visual review and screenshots. |

## Owner fields and external actions

- Name, experience, education and skills: **COMPLETE**, sourced from the supplied resume; no unprovided personal interests added.
- Email, GitHub and LinkedIn: **COMPLETE**, using supplied resume destinations. Phone number and original PDF excluded.
- GitHub repository URL: **https://github.com/shurandaa/the-arcad**, verified public and writable. Source upload to `main` is complete, with seven public files verified against local content.
- Live site URL: **PENDING**, source is uploaded to GitHub; owner must enable Pages from `main` and `/ (root)`. Sites remains registered but undeployed.
- User's actual hours: **3 hours**, user reported in `WRITEUP.md`; deadline **October 6**.
- Extra credit requires submission at least 48 hours before the actual deadline. Deadline and submission evidence are unknown, so no extra credit is claimed.
