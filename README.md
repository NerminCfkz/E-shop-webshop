# E-Shop.ba

A self-contained, multilingual e-commerce storefront built as a single HTML file — no build step, no dependencies, no server required. Open it in a browser and it works.

![language](https://img.shields.io/badge/lang-BS%20%7C%20EN%20%7C%20DE-informational)
![type](https://img.shields.io/badge/type-single--file%20HTML-blue)

## Overview

E-Shop.ba is a demo multi-category marketplace (electronics, home & kitchen, books, fashion, toys, sports) with a full shopping flow: browse, search, filter, read reviews, add to cart, and check out — plus customer accounts and a lightweight admin panel for managing the catalog.

Everything runs client-side in `eshop-ba.html`. Data (accounts, custom products/categories) is kept in the browser's `localStorage`, with an in-memory fallback if storage is unavailable.

## Features

- **Catalog** — 14 seeded products across 6 categories, with a category dropdown filter and live search
- **Product detail view** — opens as a small in-page modal with description, price, and rating
- **Reviews** — star ratings and written comments per product; customers can post their own
- **Cart & checkout** — slide-out cart drawer, quantity controls, and a payment step (card or cash on delivery)
- **Accounts** — sign up / sign in / profile, with client-side password hashing (SHA-256) and session persistence
- **Admin panel** — a seeded admin account can add new products and new categories directly from the UI
- **Multilingual** — full UI translation across **Bosnian, English, and German**, switchable at runtime
- **Customer support chat widget** — simple rule-based assistant for common questions (shipping, returns, payment)
- **Responsive design** — works down to small mobile widths
- **Intro animation** — short branded splash on load

## Getting started

No installation needed.

```bash
# clone the repo, then just open the file
open eshop-ba.html      # macOS
start eshop-ba.html     # Windows
xdg-open eshop-ba.html  # Linux
```

Or double-click it in your file explorer. Everything — markup, styles, and logic — lives in that one file.

### Admin access

A default admin account is seeded automatically on first load:

| Email | Password |
|---|---|
| `admin@eshop.ba` | `admin123` |

Sign in with it to see the **Manage products** option in the profile menu, which lets you add new products and categories.

> Change or remove this default account before using the page anywhere public — see [Limitations](#limitations) below.

## Tech stack

Plain HTML, CSS, and vanilla JavaScript. No frameworks, no bundler, no npm install. Translations and product data are defined as JS objects inline in the file.

## Limitations

This is a **frontend-only demo**, which comes with real constraints worth knowing before using it for anything beyond a prototype:

- **Data isn't shared** — accounts, orders, and custom products live only in one browser, on one device. Nothing is visible to other visitors or synced anywhere.
- **Not secure for real use** — the "admin" check and password handling run entirely in client-side JavaScript, which anyone can inspect or bypass. There's no real authentication boundary.
- **No real payments** — the card/cash checkout step is a UI mock; no payment is actually processed.
- **Storage can be cleared** — clearing browser data, using a different browser, or opening the file in a sandboxed preview will reset everything.

## Roadmap / backend

A matching backend (Flask + SQLite, with JWT auth and server-side admin checks) has been built separately to address the limitations above — real accounts, real order totals computed server-side, and an admin role that can't be spoofed from the browser. Wiring the frontend to call that API instead of `localStorage` is the natural next step.

## License

Add a license of your choice (MIT is a common default for demo projects like this).

## Author

Built by Nermin Osmanbašić.

