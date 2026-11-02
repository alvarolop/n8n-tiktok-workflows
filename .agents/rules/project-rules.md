# TikTok AI Monitor - Project Rules

## Environment & Tech Stack
- **Engine:** n8n Community Edition
- **Container Management:** `compose.yaml` (Universal: Podman / Docker on Windows & Linux Fedora)
- **Scraper:** Apify (`clockworks~free-tiktok-scraper`)
- **AI Model:** Google Gemini 2.5 Flash (`gemini-2.5-flash`)
- **UI:** n8n webhook dashboard (`/webhook/tiktok-feed`)
- **Secrets:** Keep API keys in `.env`. Pass them with `podman compose --env-file .env up -d`. Never put keys in the workflow JSON.
- **License:** MIT
- **Conventions:** Keep project cross-platform, minimal, and free of OS-specific scripts.
