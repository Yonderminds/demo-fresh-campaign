# Demo: a fresh Campaign Page Kit project

This repo shows what you get **right after** you install Campaign Page Kit, before any work for a store.

Compare it with the configured demo: https://github.com/Yonderminds/demo-configured-campaign. That repo is a real campaign, set up for one store, built and tested.

The full step-by-step guide is in the configured demo: [GO-LIVE.md](https://github.com/Yonderminds/demo-configured-campaign/blob/main/GO-LIVE.md).

---

## How this repo was made

These are Step 3 of the go-live guide, then 1 command to add a starter template:

```bash
npm init -y && npm install --save-exact next-campaign-page-kit@0.3.0
npm install --save-dev --save-exact @nextcommerce/campaigns-os@1.71.2
npx --no-install campaigns-os install-agent-context --target .
npx campaign-init --non-interactive --template apollo --slug demo --name "Demo Campaign" --ai-context codex
```

Nothing else was changed, except 4 lines added to `.gitignore` (`node_modules/`, `_site/`, `.env`, `.env.*`) and this README.

## What is inside

| File or folder | What it is |
|---|---|
| `package.json` | Page Kit and Campaigns OS, and the commands `npm run dev` and `npm run build` |
| `_data/campaigns.json` | The campaign list. Has the **demo store** name, links and phone number |
| `src/demo/` | The **apollo** starter template: 9 pages (presell, landing, checkout, 5 upsell styles, receipt) |
| `src/demo/assets/config.js` | Page settings. Has the **demo** Campaign API key |
| `AGENTS.md` | Instructions for Codex |
| `.campaign-runtime/agent-context/` | Campaigns OS instructions for Codex and other AI tools |

## Try it

```bash
npm install
npm run dev
```

Open the address it prints. You see the starter pages with demo products.

**Do not place orders here.** This project uses NEXT's demo store, not your store.

## What changes when you configure it for a store

| In this fresh repo | In a configured repo |
|---|---|
| Demo Campaign API key in `config.js` | Your campaign's Campaign API key (Step 6 of the guide) |
| Demo store name, links and phone in `campaigns.json` | Your store's name, support contact and policy links |
| Template pages with demo text and images | Your pages, built from your Map and your designs (Steps 9 and 10) |
| Demo package IDs | Your campaign's package IDs |
| All 9 template pages | Only the pages in your funnel |
| No hosting | A hosting workflow and your own domain (Step 12) |
| No checks or test records | Campaigns OS build and QA records in `.campaign-runtime/` |
