# Implementation writeup

## AI usage disclosure

I used ChatGPT to help come up with the UI design concept. I also used AI assistance to deploy the website.

## Most challenging implementation issue and constraints

The hardest part was making sure all the crossword answers lined up correctly while keeping the site easy to use with only HTML and CSS. I chose a word square because it made each crossing easy to check. Standard input fields let users enter letters, and a `details` element lets them reveal the solution without JavaScript.

Fitting the grid into a 320px-wide screen was another challenge. After accounting for margins, gaps, and borders, each of the six columns has about 45.67px of space. I left out automatic navigation, scoring, and answer checking because those features go beyond the HTML/CSS-only requirement.

## Puzzle construction and alternatives

I built the puzzle with CSS Grid using six equal columns. It has 25 open cells, with the bottom row and rightmost column blocked off. The answers form a five-letter word square: HEART / EMBER / ABUSE / RESIN / TREND. Reading down the columns gives the same five words, but I wrote different clues for Across and Down.

The clue numbers follow the starting cells from left to right, top to bottom: Across uses 1, 6, 7, 8, and 9, while Down uses 1 through 5. Each input has a visually hidden label with its position and both clue numbers. The solution uses the same layout, with fixed letters instead of inputs.

I considered using a table because it naturally organizes rows and columns, but CSS Grid meets the assignment requirement and makes it easier to resize the squares. A more traditional crossword could have offered more variety in the answers, but I would have needed to build and check a different word set. I also considered a fully open 5×5 grid, but kept the blocked cells to meet the requirement.

## Design decisions worth highlighting

I wanted the site to feel like a simple puzzle notebook, with a warm white background, dark text, and a deep green accent. Green highlights actions and the current navigation item. I checked the text contrast and used subtle borders to separate sections without putting everything in its own card.

The serif heading adds some personality, while system fonts keep the instructions easy to read. Bold letters help the puzzle entries stand out. I kept the colors, spacing, and font sizes in one shared stylesheet so the pages stay consistent. I also created a small three-square SVG mark to give the site its own identity without using external images.

The collection has space for four games to show how the site could grow, but only the completed crossword has a playable link.

## Additions with more time or resources

My first priority would be to finish checking the site in a browser and capture actual Lighthouse screenshots. That would require an environment where Chrome and a local HTTP preview work properly.

The supplied resume has been added, publication has been authorized, and the site has been deployed successfully through GitHub Pages. The remaining work is mainly browser and accessibility testing.

## Actual time

**Actual hours spent: 3 hours**

## Sources actually used

I wrote the site code and puzzle clues manually and created the SVG mark myself. I did not copy or import external code, templates, fonts, icons, puzzles, or other assets. The site uses fonts already installed on the visitor’s device, including Georgia and system UI fallbacks.

I used Python and BeautifulSoup to inspect the files locally; neither is part of the delivered website. I also tried the available Chrome binary for testing, but it failed to render the site.

The Sites building skill helped guide the workflow, while the HTML/CSS-only requirements shaped the final implementation. The profile content came from the supplied resume.
