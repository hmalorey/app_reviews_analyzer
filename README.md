# App Reviews Analyzer

## Problem to solve

Product managers lack a fast, reliable way to keep a pulse on what users are saying in app store reviews. Without it, store rating drops go unnoticed and critical issues flagged by users get missed — slowing down the team's ability to react and fix.

## Goal of this project

Build a notebook to explore how to scrape, analyze, and run mobile app reviews through AI: extracting product and business insights in the minimum amount of time.

This is a **prelude to an actual live app** ([AppLens](https://github.com/hmalorey/applens_live_app)).

The objectives were to:
- Understand which libraries to use and which objects to manipulate
- Draft an MVP and validate the technical architecture
- Experiment with AI-powered analysis (Claude, Gemini, Groq) on real review data

## Key learnings

- **Core object** — a review has: `date`, `username`, `review`, `market`, `language`, `rating`, `source`
- **App Store scraping** — used the old iTunes RSS feed instead of the official App Store Connect API to bypass JWT authentication and ship faster. Undocumented but stable, works for any public app.
- **Play Store scraping** — used `google-play-scraper`, an unofficial scraper that requires no auth, wrapping the same endpoint the Play Store web UI uses.
- **Data manipulation** — used `pandas` to merge, filter, and aggregate reviews across stores and markets
- **AI analysis** — used the Claude API to generate structured product insights (top issues + strengths) directly from raw review text, with JSON output for easy consumption

## Stack

- **Scraping** — iTunes RSS feed (App Store) + `google-play-scraper` (Play Store)
- **Analysis** — Claude API (`claude-opus-4-6`) with structured JSON output
