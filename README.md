# Resumind - AI Resume Analyzer

A resume analyzer web app that scores your resume for ATS readiness and gives practical improvement tips.

## Live Demo

Add your deployed Netlify URL here: 

- [<https://your-site-name.netlify.app>](https://resumindjude.netlify.app/)

Example:

- <https://resumindjude.netlify.app>

## Features

- Upload a resume PDF
- Convert first page to image preview
- Analyze resume with AI
- Get ATS score and detailed section feedback
- Save analysis records for later review

## Tech Stack

- React 19
- React Router 7 (SPA mode)
- TypeScript
- Vite
- Tailwind CSS v4
- Zustand
- Puter (auth, storage, KV, AI)

## How It Works

1. Sign in with Puter.
2. Upload resume PDF.
3. App uploads PDF and preview image to Puter storage.
4. App sends resume + prompt to Puter AI.
5. App stores feedback and shows review page.

## Project Structure

- app: routes, components, client logic
- constants: AI prompt and response format
- public: static assets
- types: shared TypeScript types
- build: production output

## Local Setup

Requirements:

- Node.js 20+
- npm

Install:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

Open:

- <http://localhost:5173>

Type check:

```bash
npm run typecheck
```

Production build:

```bash
npm run build
npm run start
```

## Deployment (Netlify)

This project is already configured with netlify.toml.

Required settings:

- Build command: npm run build
- Publish directory: build/client
- Environment variable: NODE_VERSION=20

Important:

- Keep SPA redirect enabled so routes like /upload and /resume/:id do not 404 on refresh.

## Docker (Optional)

Build image:

```bash
docker build -t resumind .
```

Run container:

```bash
docker run -p 3000:3000 resumind
```

Open:

- <http://localhost:3000>

## Notes

- Runtime depends on external Puter and CDN services.
- AI analysis can take 30 to 60 seconds depending on network and provider response time.
