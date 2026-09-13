

# 🌸 AnimeFinder

> A fast, modern anime discovery app built with React and Vite. Search thousands of titles, filter by genre and status, and find out exactly where to legally stream each one — all backed by the free Kitsu API.
> <img width="1721" height="968" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/139c1bc7-c345-4cd7-8694-4463c0bf1c28" />


## ✨ Features

* **Live Search:** Debounced, as-you-type search across the full Kitsu anime catalog.
* **Advanced Filtering:** Sort by popularity, rating, favorites, or release date. Narrow results by airing status, type (TV/Movie/OVA), age rating, and genre.
* **Genre Browsing:** Tap any genre tag on a title to instantly filter the catalog by that specific genre.
* **Detailed Anime View:** An expandable modal featuring a full synopsis, genres, user rating, embedded YouTube trailer, and legal streaming links.
* **Streaming Platform Detection:** Automatically recognizes and brands links from Crunchyroll, Netflix, Hulu, Prime Video, Disney+, HIDIVE, Funimation, Tubi, YouTube, Bilibili, JioCinema, and more.
* **Personalized Recommendations:** A lightweight, on-device engine that learns from your searches (stored in `localStorage`) and surfaces a "Recommended for You" rail.
* **Pagination:** Browse large result sets page by page seamlessly.
* **Smooth Animations:** Modal and list transitions powered by Framer Motion.
* **Responsive UI:** Styled with Tailwind CSS for a clean, premium experience on both desktop and mobile.

## 🛠️ Tech Stack

*No backend, database, or API key is required — the app talks directly to Kitsu's public REST API from the client.*

| Category | Technology |
| --- | --- |
| **Framework** | React 19 |
| **Build Tool** | Vite |
| **Styling** | Tailwind CSS 4 |
| **Animation** | Framer Motion |
| **Utilities** | `react-use` (debouncing) |
| **Data Source** | Kitsu API |
| **Linting** | ESLint |

## 🚀 Getting Started

### Prerequisites

* **Node.js:** v18 or later
* **Package Manager:** `npm` (bundled with Node.js), `yarn`, `pnpm`, or `bun`.

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com//vite-react-animeapp.git
cd vite-react-animeapp

```


2. **Install dependencies:**
```bash
npm install

```


3. **Start the development server:**
```bash
npm run dev

```


4. **Open the app:** Visit the URL printed in your terminal (typically `http://localhost:5173`).

## 📜 Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite dev server with hot module reload (HMR). |
| `npm run build` | Build an optimized production bundle to the `dist/` directory. |
| `npm run preview` | Preview the production build locally. |
| `npm run lint` | Run ESLint across the project to check for code quality. |

## 📂 Project Structure

```text
vite-react-animeapp/
├── public/                # Static assets (platform icons, hero art, placeholders)
├── src/
│   ├── Components/
│   │   ├── Animecard.jsx  # Grid card + expandable detail modal for each anime
│   │   ├── Loader.jsx     # Loading state indicator
│   │   └── Search.jsx     # Search input bar
│   ├── App.jsx            # Main app logic: search, filters, pagination, recommendations
│   ├── App.css            # App-level styles
│   ├── index.css          # Global styles and Tailwind entry point
│   └── main.jsx           # React application entry point
├── index.html
├── vite.config.js
└── package.json

```

## 🧠 How It Works

### Data Fetching

Anime data is fetched from the **Kitsu Edge API** (`[https://kitsu.io/api/edge](https://kitsu.io/api/edge)`). Search terms, sort orders, and active filters (status, type, age rating, genres) are translated into dynamic query parameters, and results are paginated 20 items at a time.

### Streaming Link Detection

When an anime card is expanded, the app requests that title's streaming links and genres from Kitsu. It then matches each URL against a set of known platform domains to display a beautifully branded button (complete with platform name, theme color, and icon) rather than a raw, ugly link.

### Recommendation Engine

Every time a search returns valid results, the top match is recorded in a simple, on-device scoring system persisted to your browser's `localStorage`. Titles you search for repeatedly rise to the top of a "Recommended for You" rail shown on the home screen. **No account or server-side tracking is involved** — recommendations live entirely and privately in your browser.

## 🤝 Contributing

Contributions are always welcome! To propose a change:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request.

*Please run `npm run lint` before submitting a pull request to ensure code consistency.*

## ⚖️ Attribution & License

This project uses the [Kitsu API](https://kitsu.docs.apiary.io/) for all anime metadata, artwork, and streaming link information. AnimeFinder is not affiliated with Kitsu or any of the streaming platforms it links to.

This project is open-source and available under the [MIT License](https://www.google.com/search?q=LICENSE). *(Note: Ensure you add a LICENSE file to your repo if you wish to distribute this code).*
