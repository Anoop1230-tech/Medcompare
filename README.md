# 💊 MedCompare

**Save on medicines by comparing prices across different online pharmacies.**

MedCompare is a web application that helps users find the best prices for their medications by comparing them across multiple online pharmacies in real time. Enter a medicine name, and MedCompare fetches and displays prices with easy-to-read visual charts so you can quickly spot the cheapest option.

🔗 **Live Demo:** [magenta-shortbread-4e4384.netlify.app](https://magenta-shortbread-4e4384.netlify.app/)

---

## ✨ Features

- **Instant Price Comparison** — Compare medicine prices across multiple online pharmacies in seconds.
- **Visual Price Charts** — Interactive charts (powered by Chart.js) with zoom and pan support to visualize price differences.
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
- **Backend API** — A lightweight Flask service hosted on Render:
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
2. `scripts.js` sends the query to the backend scraping API.
3. The API returns prices from various online pharmacies.
4. Results are rendered as cards and plotted on an interactive price-per-unit chart.
5. A savings summary highlights the best available price.

---

## 📬 Contact

- **Email:** su-24017@sitare.org
- **Phone:** +91 9519612956

---

© 2025 MedCompare. All rights reserved.
