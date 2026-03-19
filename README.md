# PoC: Browser Autofill Data Extraction

A single-file, zero-dependency proof of concept that demonstrates how browsers can silently extract personal data through hidden autofill form fields — without alerting the user.

> **Educational purposes only.** This project exists to raise awareness about a real browser security risk and help developers understand how autofill attacks work.

## How It Works

Modern browsers offer to auto-fill form fields based on saved personal data. A malicious site can add **hidden fields** alongside a legitimate form (e.g., a newsletter signup asking only for your name). When the user triggers autofill, the browser may also fill those hidden fields with sensitive data like phone numbers, addresses, or credit card details.

This PoC lets you test **9 CSS hiding techniques** and observe which ones your browser detects and blocks.

## The 9 Hiding Techniques

| # | Technique | CSS Strategy |
|---|-----------|-------------|
| 1 | Off-screen | `position: absolute; left: -9999px` |
| 2 | display:none | `display: none` |
| 3 | visibility:hidden | `visibility: hidden; height: 0` |
| 4 | opacity:0 | `opacity: 0; height: 0` |
| 5 | transform:scale(0) | `transform: scale(0); position: absolute` |
| 6 | clip-path:inset | `clip-path: inset(100%)` |
| 7 | Size zero | `width: 0; height: 0; font-size: 0` |
| 8 | z-index:-1 + opacity | `z-index: -1; opacity: 0.01` |
| 9 | SR-Only (clip rect) | `clip: rect(0,0,0,0); width: 1px; height: 1px` |

## Hidden Field Categories

Each technique deploys **79 hidden fields** across 4 detection strategies:

- **Autocomplete attribute** (26 fields) — Standard `autocomplete="tel"`, `autocomplete="cc-number"`, etc.
- **Heuristic EN** (14 fields) — English field names like `phone_number`, `credit_card`, `ssn`
- **Heuristic ES** (15 fields) — Spanish field names like `telefono`, `tarjeta`, `dni`
- **Placeholder** (8 fields) — No name or autocomplete cues, only placeholder text hints

Fields are grouped into three sensitivity levels: phone/personal, address, and credit card data.

## Usage

1. Open `index.html` in a browser (no server required).
2. Select a **hiding technique** from the tabs.
3. Click the **name field** and pick a suggestion from the browser's autofill dropdown.
4. Click **Submit** — the results panel shows which hidden fields were captured.
5. Repeat with each technique. Results accumulate in the **comparison table**.

## Features

- **Zero dependencies** — Single HTML file, works fully offline
- **Bilingual UI** — Toggle between English and Spanish (ES/EN)
- **Browser detection** — Automatically identifies browser, engine, platform, and version
- **Live feedback** — Submit button shows captured field count in real time
- **Sensitive data masking** — Credit card numbers show only last 4 digits; CVV/SSN are fully masked
- **Comparison table** — Side-by-side results across all 9 techniques with filled/blocked indicators

## Browser Compatibility

Tested on:
- Chrome / Chromium-based (Edge, Opera, Brave)
- Firefox / Gecko
- Safari / WebKit

Results vary significantly between browsers and versions. That's the point — some browsers are better at detecting and blocking hidden field autofill than others.

## Disclaimer

This project is strictly for **educational and security research purposes**. It demonstrates a well-known browser behavior to help developers and security researchers understand the risk. Do not use these techniques maliciously.

## License

MIT
