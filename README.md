# 💊 MedCompare

**Save on medicines by comparing prices across India's top online pharmacies: Tata 1mg, PharmEasy, Netmeds and Apollo Pharmacy.**

MedCompare is a web application that helps users find the best prices for their medications by comparing them across 4 online pharmacies in real time. Enter a medicine name, and MedCompare fetches live prices with easy-to-read visual charts so you can quickly spot the cheapest option.

🔗 **Live Demo:** [magenta-shortbread-4e4384.netlify.app](https://magenta-shortbread-4e4384.netlify.app/)

---

## 🏥 Supported Pharmacies

| Pharmacy | Chart color | Data |
|---|---|---|
| **Tata 1mg** | 🟢 Green | Live prices |
| **PharmEasy** | 🟣 Purple | Live prices |
| **Netmeds** | 🔴 Red | Live prices |
| **Apollo Pharmacy** | 🔵 Blue | Live prices |

For every product, MedCompare shows the **medicine name, pack size/quantity, current selling price and a direct link** to the product page on the pharmacy's website.

> **MedPlus** is not supported: its website blocks all automated requests.

---

## ✨ Features

- **Instant Price Comparison** — Compare live medicine prices from Tata 1mg, PharmEasy, Netmeds and Apollo Pharmacy in a few seconds.
- **Visual Price Charts** — Interactive price-per-unit charts (powered by Chart.js) with zoom and pan support, with a separate color for each pharmacy.
- **Best Price Finder** — Automatically highlights the lowest price and estimated savings.
- **Dark / Light Mode** — Theme toggle with preference saved in the browser (`localStorage`).
- **Responsive Design** — Works across desktop, tablet, and mobile.
- **Extra Content Pages** — Blog, FAQs, and Health Tips to keep users informed.
- **User Authentication Pages** — Sign In and Sign Up screens.

---

## 🗂️ Project Structure

```
Medcompare/
├── index.html            # Home page (hero, search, features, results)
├── signin.html           # Sign In page
├── signup.html           # Sign Up page
├── blog.html             # Blog page
├── faqs.html             # Frequently Asked Questions
├── health-tips.html      # Health tips content
├── styles.css            # Main stylesheet (theming, layout, animations)
├── scripts.js            # App logic (search, theme toggle, charts, results)
├── chart.min.js          # Chart.js library (bundled)
├── all.min.css           # Font Awesome icons (bundled)
└── placeholder_500x350.png  # Hero image asset
```

---

## 🛠️ Tech Stack

- **HTML5** — Page structure
- **CSS3** — Styling, theming, and animations (plus Bootstrap 5 via CDN)
- **JavaScript (Vanilla)** — Interactivity and data fetching
- **Chart.js** + `chartjs-plugin-zoom` + `Hammer.js` — Price visualizations
- **Font Awesome** — Icons
- **Backend API** — A lightweight Flask service hosted on Render that fetches live prices from all 4 pharmacies in parallel:
  `https://medcompare-backend-wja7.onrender.com/api/scrape`
  (source: [medcompare-backend](https://github.com/Anoop1230-tech/medcompare-backend))

---

## 🚀 Getting Started

Since this is a static front-end project, no build step is required.

### Option 1 — Open directly
Simply open `index.html` in your browser.

### Option 2 — Run a local server (recommended)
Running a local server avoids CORS/file-path issues.

**Using Python:**
```bash
# From the project root
python -m http.server 8000
```
Then visit [http://localhost:8000](http://localhost:8000).

**Using Node (http-server):**
```bash
npx http-server -p 8000
```

**Using VS Code:** Install the **Live Server** extension and click *"Go Live"*.

---

## 📖 How It Works

1. The user enters a medicine name in the search box on the home page.
2. `scripts.js` sends the query to the backend API (`POST /api/scrape`).
3. The backend searches Tata 1mg, PharmEasy, Netmeds and Apollo Pharmacy at the same time and returns a list of matching products from each, with name, quantity, price and link. If one pharmacy is slow or down, the others are still shown.
4. Results are rendered as cards in a separate section for each pharmacy and plotted on an interactive price-per-unit chart.
5. A savings summary highlights the best available price.

### Example response
```json
{
  "1mg (Tata)":      [{ "number": 1, "medicine": "Dolo 650 Tablet", "quantity": "15 units", "price": "₹29.7", "link": "https://www.1mg.com/drugs/..." }],
  "PharmEasy":       [{ "number": 1, "medicine": "Dolo 650Mg Strip Of 15 Tablets", "quantity": "15 Tablet(s) in Strip", "price": "₹29.37", "link": "https://pharmeasy.in/..." }],
  "Netmeds":         [{ "number": 1, "medicine": "Dolo 650 Tablet 15's", "quantity": "15 Tablet(s) in Strip", "price": "₹25.18", "link": "https://www.netmeds.com/product/..." }],
  "Apollo Pharmacy": [{ "number": 1, "medicine": "Dolo-650 Tablet 15's", "quantity": "15 Tablet(s)", "price": "₹32.0", "link": "https://www.apollopharmacy.in/otc/..." }]
}
```

---

## ➕ Adding Another Pharmacy

1. In [medcompare-backend](https://github.com/Anoop1230-tech/medcompare-backend), add a `fetch_<name>()` function to `app.py` and register it in the `SOURCES` dict. The front-end shows a new results section for it automatically.
2. In this repo, add a chart color for the same pharmacy name to the `colors` map in `scripts.js` (it appears twice).

---

## 📬 Contact

- **Email:** su-24017@sitare.org
- **Phone:** +91 9519612956

---

© 2025 MedCompare. All rights reserved.
