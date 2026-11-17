# Demo: a fresh Campaign Page Kit project

This repo shows what your store repo looks like **after Step 4** of the go-live guide: Page Kit and Campaigns OS installed, Codex connected, 1 starter template added. Nothing is set up for a store yet. It uses the same simple layout as the guide.

Compare it with the configured demo: https://github.com/Yonderminds/demo-configured-campaign. That repo is a real campaign, set up for one store, built and tested.

The full step-by-step guide is in the configured demo: [GO-LIVE.md](https://github.com/Yonderminds/demo-configured-campaign/blob/main/GO-LIVE.md).

---

## How this repo was made

All commands were run in the repo folder:

```bash
npm init -y
npm install --save-exact next-campaign-page-kit@0.3.0
npm install --save-dev --save-exact @nextcommerce/campaigns-os@1.71.2
npx --no-install campaigns-os install-agent-context --target .
npx campaign-init --non-interactive --template apollo --slug demo --name "Demo Campaign" --ai-context codex
```

Then:

- 4 lines added to `.gitignore` (`node_modules/`, `_site/`, `.env`, `.env.*`), as in Step 3.
- The Step 4b lines added to the top of `AGENTS.md`. (Here `campaign-init --ai-context codex` made `AGENTS.md` with Page Kit's rules. In your repo, do not use `--ai-context` after Step 4b, because it replaces the file.)
- This README.

The guide's other setup commands (`qa install-browser`, `install-skills`, `npx skills add`) change your **computer**, not the repo, so they leave nothing here. In your own repo, the starter template is added by Codex in Step 10, not by hand.

## What is inside

| File or folder | What it is |
|---|---|
| `package.json` | Page Kit and Campaigns OS, and the commands `npm run dev` and `npm run build` |
| `_data/campaigns.json` | The campaign list. Has the **demo store** name, links and phone number |
| `src/demo/` | The **apollo** starter template: 9 pages (presell, landing, checkout, 5 upsell styles, receipt) |
| `src/demo/assets/config.js` | Page settings. Has the **demo** Campaign API key |
| `AGENTS.md` | Instructions for Codex. The top lines point to the Campaigns OS instructions (Step 4b) |
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
| No Shopify URLs, no AppLovin key | `shopify-urls.json` and `axon_event_key` (Steps 11 and 12) |
| No hosting | A hosting workflow and your own domain (Step 13) |
| No checks or test records | Campaigns OS build and QA records in `.campaign-runtime/` |
