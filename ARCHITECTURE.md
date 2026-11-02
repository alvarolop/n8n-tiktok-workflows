# Architecture & System Design — TikTok AI Monitor

## System Overview
Cross-platform automated TikTok content monitoring pipeline built on **n8n**, **Apify**, and **Google Gemini AI**.

## Target Deployment Environments
- **Local Development:** Managed via Podman Compose (`deploy/local/compose.yaml`).
- **Production Cluster:** Managed via Helm on Red Hat OpenShift (`deploy/openshift/values.yaml`).

## Directory Structure
- `workflows/`: Exported n8n workflow definitions in JSON format (`n8n-tiktok-workflow.json`).
- `deploy/local/`: Container orchestration files for local environments.
- `deploy/openshift/`: Helm values and cluster deployment configs.

## Technical Architecture & Guardrails
- **Core Engine:** n8n v2+ (Community Edition).
- **Data Scraping:** Apify actor (`clockworks~free-tiktok-scraper`).
- **AI Processing:** Google Gemini 2.5 Flash via REST API.
- **Frontend / UI:** Native HTML dashboard rendered via n8n webhook (`/webhook/tiktok-feed`).
- **Security & Secrets:**
  - All secrets and keys reside strictly in `.env` (or Kubernetes/OpenShift Secrets).
  - Never commit API tokens, passwords, or credentials directly inside workflow JSON files or values files.