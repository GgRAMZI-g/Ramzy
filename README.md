# Ramzy

A modern web application built with Vite and Vue 3.

## Getting Started

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager

### Installation

```bash
npm install
```

### Development

Run the development server:

```bash
npm run dev
```

The app will be available at `http://localhost:5173`

### Build

Build for production:

```bash
npm run build
```

Output will be in the `dist/` directory.

### Preview

Preview the production build locally:

```bash
npm run preview
```

## Deployment

This repo includes a GitHub Actions workflow that automatically builds and deploys to GitHub Pages on every push to `main`.

To enable GitHub Pages:
1. Go to Settings → Pages
2. Set Source to "Deploy from a branch"
3. Select branch: `gh-pages`

The workflow will create the `gh-pages` branch automatically on first run.
