# Implementation writeup

This document describes the actual Codex-assisted implementation. It does not represent the owner's personal experience or a claim that the owner wrote the code manually.

## Most challenging implementation issue and constraints

The main technical issue was maintaining correct crossword relationships while keeping the interface usable with HTML and CSS alone. The chosen word square makes every crossing verifiable, while native inputs and a `details` disclosure provide entry and solution reveal without client-side logic. The 320px width requirement also limits the space available for six columns, margins, gaps, and borders; the implemented calculation leaves approximately 45.67px per square. Automatic navigation, scoring, and correction were excluded because they require behavior beyond the permitted implementation. The owner's subjective challenge or experience is **[pending: supply your own reflection]**.

## Puzzle construction and alternatives

The grid uses `display: grid` with six equal columns, 25 open cells, and an intentionally blocked bottom row and right column. Its five-letter word square is HEART / EMBER / ABUSE / RESIN / TREND; reading each column yields the same five words, with separate original Across and Down clues. Clue numbers follow row-major starting positions: Across 1, 6, 7, 8, 9 and Down 1 through 5. Every input's associated hidden label identifies its coordinates and both intersecting clue numbers, and the solution repeats the same structure with static letters. A table was considered because it expresses rows and columns, but Grid fits the explicit requirement and lets square sizes remain fluid; a conventional asymmetric blocked puzzle would allow more varied answers but would require a different verified word set. A fully open 5×5 word square was also possible, but this version includes clearly distinguishable blocked squares as requested.

## Design decisions worth highlighting

The design takes its direction from a quiet puzzle notebook: a warm white page, dark ink, and one deep green accent. The dark green marks playable actions and selected navigation while maintaining measured text contrast, and neutral borders establish groups without turning every section into a card. A serif headline adds personality while system UI text and bold letters keep instructions and inputs readable. Colors, spacing, and the type scale are centralized in the shared stylesheet, while the original three-square SVG gives the site a small identity without external imagery. The four-slot collection shows the intended future scope, but only the actual crossword has a playable link.

## Additions with more time or resources

The first priority would be completing browser verification and obtaining genuine Lighthouse screenshots in an environment that permits Chrome and local HTTP preview. The supplied resume has now been applied and the owner has authorized publication. The next publishing step requires network access for source upload and repository creation capability. Three additional games could fill the reserved slots, with the same accessible navigation and styling. If the HTML/CSS-only constraint were relaxed, automatic movement, letter validation, a reset control, and explicitly local saved progress could be considered, with appropriate accessibility testing. None of those behaviors is claimed in the current version.

## Actual user time

**Actual hours spent by the user: 3 hours (user reported).** The user supplied this figure on October 6, 2026. Automated implementation time and tool execution are not a separate measure of the user's personal effort. The reported deadline is October 6; no submission timestamp or 48-hour extra-credit eligibility is claimed.

## Implementation assumptions

The owner supplied a resume and authorized publication of the name, professional history, email, GitHub, and LinkedIn. The About and Contact pages now use that supplied information; the phone number and original PDF are excluded from publication. The project was built in the empty current workspace without a framework, runtime dependencies, or fabricated Git history. Relative links were chosen to support both direct file previews and static hosting under a subdirectory. The puzzle intentionally repeats its five answers across and down, and that twist is disclosed to players. The owner authorized pushing and public deployment on October 6, 2026. Publishing outcomes are recorded in README.md; a deadline date is not submission evidence.

## Sources actually used

All site code, the SVG mark, and the puzzle clues were created for this project with Codex assistance. No external code, design template, fonts, icon collection, puzzle source, or asset dependency was copied or imported. The website uses fonts already present on the visitor's system, with Georgia and system UI fallbacks. Existing Python and BeautifulSoup were used only for local inspection outside the delivered source, and the available Chrome binary was attempted for verification but failed to render. The Sites building skill guided the local workflow; the user's explicit static-code constraints determined the delivered structure. The supplied resume is the source for profile content.
