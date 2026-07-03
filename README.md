# Car Table

**High-volume data table with infinite scroll** — paginated JSON chunks, Pinia state, and Vue 3 Composition API.

## Overview

Displays classic automobile dataset records (MPG, cylinders, horsepower, weight, etc.) in a scrollable table. Data loads in pages from static JSON files (`cars-1.json` … `cars-5.json`) as the user reaches the bottom of the page — simulating server-side pagination without a backend.

## Stack

- **Framework:** Vue 3, TypeScript
- **State:** Pinia 3
- **Build:** Vite 6, vue-tsc
- **Data:** Static JSON in `public/data/`

## Features

- Typed `Car` interface for all dataset fields
- Infinite scroll via window scroll listener
- Loading indicator between page fetches
- Null-safe rendering for optional MPG values
- Five paginated data files (~400 rows total)

## Getting Started

```bash
git clone https://github.com/AlimFullstack/Car-Table-Project.git
cd Car-Table-Project
npm install
npm run dev
```

Open the URL shown in the terminal (typically `http://localhost:5173`).

### Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Development server |
| `npm run build` | Typecheck + production build |
| `npm run preview` | Preview production build |

### How pagination works

`useCarsStore` increments `fileIndex` after each successful fetch. Scrolling to the document bottom triggers `loadMoreCars()` until all five JSON files are loaded.
