# 🍫 Cocoa & Craft — Global Chocolate Atlas

An interactive data visualisation exploring **2,789 chocolate bar reviews** from around the world. Filter by rating, cocoa percentage, and review year to discover how bean origins, manufacturer locations, and flavour profiles connect across the globe.

**[→ Live site](https://dddcr.github.io/choco-atlas)**

---

## Features

**Dual-layer world map** — two simultaneous layers rendered with D3 + TopoJSON:
- 🟤 **Bean Origins** — countries shaded by average rating (red → green scale)
- 🔵 **Manufacturer Hubs** — bubbles sized by review count, coloured by average rating

**Interactive brushing** — hover any country, bubble, or flavour word to highlight all related locations across both map layers simultaneously.

**Flavour word cloud** — the top 60 most memorable characteristics from filtered reviews, sized by frequency and coloured by average rating. Hovering a word lights up the origins where that flavour was tasted.

**Top-10 leaderboard** — dynamically re-ranks bean origins or manufacturer hubs as you adjust filters. Clicking a row brushes the map.

**Filter rail** with:
- Rating range slider (1.0 – 4.0)
- Cocoa % range slider (42% – 100%)
- Review year range slider
- Minimum reviews threshold
- Toggle: require ≥ 30 reviews (statistical reliability)

---

## Dataset

`choco_bar_rating.csv` — sourced from the [Manhattan Chocolate Society](http://flavorsofcacao.com/chocolate_database.html) via Kaggle.

| Column | Description |
|---|---|
| Company (Manufacturer) | Chocolate maker name |
| Company Location | Country of manufacturer |
| Review Date | Year of review |
| Country of Bean Origin | Where the cocoa beans are from |
| Specific Bean Origin or Bar Name | Farm / region / bar name |
| Cocoa Percent | % cocoa content |
| Ingredients | Ingredient list |
| Most Memorable Characteristics | Tasting notes |
| Rating | Score from 1.0 (unpleasant) to 4.0 (outstanding) |

2,789 reviews · 10 columns

---

## Tech Stack

- **D3.js** v7.8.5 — map projection, scales, data binding
- **TopoJSON** v3.0.2 — world geometry
- **Google Fonts** — Fraunces (serif), Manrope (sans), JetBrains Mono
- Zero build step — single self-contained `index.html`, no framework, no bundler

---


## Colour Scale

Map colours follow a **RdYlGn diverging 5-bin ramp** anchored to the rating range 3.00 – 3.40 (the bulk of the score distribution):

| Colour | Rating |
|---|---|
| 🔴 Red | ≤ 3.00 |
| 🟠 Orange | 3.00 – 3.08 |
| 🟡 Yellow | 3.08 – 3.16 |
| 🟢 Light green | 3.16 – 3.32 |
| 🟢 Dark green | ≥ 3.40 |

---

## License

Data: public domain via [Kaggle](https://www.kaggle.com/datasets/rtatman/chocolate-bar-ratings). Visualisation code: MIT.
