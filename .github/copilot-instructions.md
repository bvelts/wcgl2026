# AI Coding Guidelines for WGL 2026 Website

## Project Overview
This is a static HTML website for the Whitecourt Winter Golf League (WGL 2026), hosted on GitHub Pages with custom domain `rnkgolf.com`. It consists of an index page with overall standings and individual pages for each weekly event.

## Architecture
- **Static Site**: No build process; edit HTML/CSS directly
- **Shared Components**: Navigation bar and styles are duplicated across all pages
- **Data Display**: Bootstrap tables for leaderboards and proxy results
- **Styling**: Bootstrap 5.3.3 + custom `style.css` with green golf-themed background

## Key Files
- `index.html`: Overall leaderboard with player standings (points, handicap, events)
- `week{X}.html`: Individual event pages with proxy contests and weekly results
- `style.css`: Custom styles (green background, container styling)
- `CNAME`: GitHub Pages custom domain configuration

## Coding Patterns
- **Navigation**: Identical Bootstrap navbar on every page linking to all weeks
- **Tables**: 
  - Leaderboard: Pos (with emojis 🏆🥈🥉), Player, Gross/Net/Dif, WGC Points
  - Proxy: Contest type (🏌️‍♂️ KP, 💣 Hole Out), Player, Distance
- **Scoring**: Net scores calculated as Gross - Handicap; WGC Points based on position
- **Course Details**: Displayed via `window.alert()` with tees, pins, stimp, gimme, etc.
- **Player Data**: Consistent naming and handicap values across pages

## Conventions
- Use Bootstrap classes: `table table-striped table-bordered`, `table-dark` for headers
- Position indicators: 🏆 for 1st, 🥈 for 2nd, 🥉 for 3rd, numbers for others
- Handicap display: One decimal place (e.g., 4.0)
- Points/Events: Integers
- Distance formats: Feet/inches for KP (5'1"), yards for hole out (21.8y)

## Workflows
- **Updates**: Edit HTML tables directly for new scores/results
- **New Week**: Copy existing week page, update nav links, add new week{X}.html
- **Styling**: Modify `style.css` for global changes
- **Deployment**: Push to GitHub main branch for automatic Pages deployment

## Golf-Specific Terms
- **Proxy**: Closest to pin (KP) and hole out contests
- **Gross/Net**: Total strokes vs. adjusted for handicap
- **Dif**: Difference from par (not shown in tables, but used in calculations)
- **WGC Points**: League points awarded per position, equal to the number of players that played (e.g., 5 for 1st in a 5-player week)