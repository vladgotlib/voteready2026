# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-page static HTML website ("Your Vote Counts") that helps Americans prepare to vote in the November 2026 elections amid potential new voter ID requirements (SAVE America Act). The target audience is low-income and vulnerable citizens who may be disenfranchised by stricter voting laws.

## Architecture

This is a **single self-contained HTML file** (`your-vote-counts.html`) with no build system, no JavaScript framework, and no external dependencies beyond Google Fonts. All CSS is inline in a `<style>` block. There is no JS beyond a single `onclick="window.print()"`.

## Development

Open `your-vote-counts.html` directly in a browser — no server or build step required. For live reload during development, use any static file server (e.g., `npx serve .` or VS Code Live Server extension).

## Design System

- **Fonts**: Playfair Display (headings), Source Sans 3 (body) — loaded from Google Fonts
- **Color palette**: CSS custom properties defined in `:root` — ink, paper, red, blue, gold, green, gray, each with a `-light` variant
- **Layout**: Single-column, max-width 720px, mobile-responsive with breakpoint at 500px
- **Print styles**: Alert banner, nav, share bar, and CTA links are hidden when printing

## Content Sections

The page follows a specific narrative flow: alert banner → explanation of what's happening → 7-step action timeline → documents table → free help resources → CTA with share buttons. The timeline items use urgency-coded colors (urgent=red, important=gold, action=blue, go=green).

## Key Considerations

- All external links (vote.org, voteriders.org, usa.gov, lawhelp.org) must remain accurate and functional
- Dates and deadlines in the timeline are specific to the 2026 election cycle
- The document cost/wait-time table should be kept current
- Content must remain nonpartisan and accessible to low-literacy readers
- Mobile-first: the responsive table collapses to stacked cards on small screens using `data-label` attributes
