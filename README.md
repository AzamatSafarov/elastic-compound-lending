# Elastic Compound Lending

Elastic Compound Lending is a real GitHub fork of the official Compound III frontend.

- Upstream frontend: `compound-finance/webb3-frontend`
- Fork: `AzamatSafarov/elastic-compound-lending`
- License: GPL-3.0
- Purpose: lending interface foundation for the Elastic DeFi product line

This repository intentionally keeps the Compound architecture instead of rebuilding the lending UI from scratch.

## What this is

This is a Compound III frontend fork. It contains the production-style frontend architecture used by the Compound III app:

- wallet connection;
- supported network configuration;
- Compound market views;
- supply / borrow interface flows;
- transaction history integration;
- governance / extension surfaces;
- V3 API integration points.

## Backend dependency

The frontend expects a Compound V3 API backend via:

```env
VITE_V3_API_HOST=...
```

The matching backend has also been forked separately:

```text
https://github.com/AzamatSafarov/elastic-compound-backend-api
```

Upstream backend:

```text
https://github.com/compound-finance/webb3-backend-api
```

## Current status

| Area | Status |
|---|---|
| GitHub fork | Done |
| Upstream | `compound-finance/webb3-frontend` |
| License | GPL-3.0 |
| Local install | Verified |
| Production build | Verified |
| Compound V3 API backend | Forked separately |
| ZKsync support | Not enabled yet |
| Custom Compound market on ZKsync | Not deployed |

## Important limitation

This frontend only becomes a real ZKsync lending product if a compatible Compound III / Comet market exists on ZKsync or is deployed and audited.

Without a ZKsync Comet market, the fork can still be used as the lending frontend foundation, but it cannot create real Compound lending positions on ZKsync by itself.

## Required environment variables

```env
VITE_V3_API_HOST=https://your-compound-v3-api.example
VITE_V3_RPC_PROVIDER_HOST=https://your-rpc-proxy.example
VITE_V3_WALLET_CONNECT_PROJECT_ID=your_walletconnect_project_id
```

`VITE_V3_API_HOST` is required for markets, rewards, summaries, account history, and other backend-powered data.

`VITE_V3_RPC_PROVIDER_HOST` is required for blockchain RPC reads/writes through the configured networks.

`VITE_V3_WALLET_CONNECT_PROJECT_ID` is required only if WalletConnect support is enabled.

## Development

Install dependencies:

```bash
yarn install
```

Run locally:

```bash
yarn dev
```

Build:

```bash
yarn build
```

Preview production build:

```bash
yarn preview
```

## Fork policy

This repository is a GPL-3.0 derivative of the official Compound III frontend. Keep GPL-3.0 notices, upstream attribution, and source availability intact.
