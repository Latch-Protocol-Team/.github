<p align="center">
  <a href="https://oxforged.github.io/Hook-Dev/">
    <img src="assets/github-og-1280x640.png" alt="Latch Protocol — launch a DEX or a launchpad on a shared, verified core" width="100%">
  </a>
</p>

<h1 align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/latch-lockup-transparent.png">
    <img src="assets/latch-lockup-onlight.png" alt="Latch Protocol" height="56">
  </picture>
</h1>

<p align="center"><strong>Infrastructure other people ship on.</strong><br>
Launch a DEX or a launchpad from one config file, on a core that is already deployed, verified and exercised.</p>

<p align="center">
  <a href="https://oxforged.github.io/Hook-Dev/">Site</a> ·
  <a href="https://oxforged.github.io/Hook-Dev/docs">Docs</a> ·
  <a href="https://oxforged.github.io/Hook-Dev/app">App</a> ·
  <a href="https://oxforged.github.io/Hook-Dev/ecosystem">Ecosystem</a> ·
  <a href="https://github.com/Latch-Protocol-Team/latch-sdk">SDK</a> ·
  <a href="https://github.com/Latch-Protocol-Team/dex-tokenl-list">Token list</a>
</p>

---

## What you can build

| | You get | You set |
|---|---|---|
| **A launchpad** | Token factory, fair-launch pools that trade from the first block (no curve, no graduation migration), a decaying anti-snipe launch fee, locked LP with a creator / integrator / protocol split, a hosted site with charts, creator and holder pages | your fee wallet, your terms inside the protocol's caps, your brand and theme |
| **A DEX** | Concentrated-liquidity and bin pools, a swap widget with quotes and price impact, pool pages, positions, analytics, a token list | your swap fee, which pools you route, your brand and theme |
| **A Latch** | A hook contract attached to a pool — revenue share, market hours, price bands, permissioned pools, launch guards — listed in an on-chain registry with attested permissions | the terms your pool enforces |

Both site kinds are created from the app in one transaction and read everything they render from the chain: the owner, the brand, the terms, the launches, the trades. Nothing is curated, nothing is invented.

## How it works

- **One shared core per chain.** A vault, a concentrated-liquidity pool manager and a bin pool manager, deployed once, verified once. A tenant deploys a hook and a kit against it — never the core.
- **Latches are hooks.** Every product feature that touches a swap is a hook contract with an attested permission bitmap, so a trader can read exactly what sits in the swap path.
- **Revenue is enforced by contracts, never by SDK code.** Immutable caps in the contracts, per-launch terms frozen at creation, a protocol floor nobody can go below, and a fee controller behind a multisig and a 48-hour timelock.
- **Stocks out of the box.** Tokenised equities are first-class quote assets where a chain lists them, with market-hours and price-band hooks written for them.
- **Admin keys that cannot hurt you.** Immutable contracts, two-step ownership with `renounceOwnership` disabled, delays that scale with how hard an action is to undo, and no key anywhere that can move a user's funds.
- **Latch has no token.** There is nothing to buy; the protocol earns from the fees its contracts enforce.

## Repositories

| Repository | What it is | Licence |
|---|---|---|
| [`latch-sdk`](https://github.com/Latch-Protocol-Team/latch-sdk) | TypeScript SDK: deployments, reads, launch building, market data, token lists — the MIT surface every integration builds against | MIT |
| [`dex-tokenl-list`](https://github.com/Latch-Protocol-Team/dex-tokenl-list) | The Latch token list, in the standard Token Lists schema, generated and verified on chain | MIT |
| `.github` | This profile, and the [ecosystem listing form](https://github.com/Latch-Protocol-Team/.github/issues/new/choose) | — |

The core is a GPL-2.0-or-later derivative of the Infinity architecture (`pancakeswap/infinity-core`), extended and hardened; Latch runs only on its own deployments and is not affiliated with any other protocol. The SDK, widgets and site template are independently authored and MIT, so nothing you ship on Latch has to inherit the GPL.

## Ship on Latch

Two ways in, both from the [app](https://oxforged.github.io/Hook-Dev/app):

1. **Hosted** — build a launchpad or a DEX in the app, pick a theme, set your fee wallet and terms, sign one transaction. Your site is live at `/p/<address>` and can be served from your own domain.
2. **Self-hosted** — take the MIT site template (`create-latch-dex`), set the fee wallet and the chain in `latch.config.ts`, restyle if you like, deploy. It runs against the shared core and needs no Solidity of your own.

The [docs](https://oxforged.github.io/Hook-Dev/docs) cover both, contract by contract.

Listing your launchpad, DEX or Latch in the ecosystem is an [issue form](https://github.com/Latch-Protocol-Team/.github/issues/new/choose), and the listing is read back from the chain before it is shown.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/powered-by-latch-dark.png">
    <img src="assets/powered-by-latch-light.png" alt="Powered by Latch" height="36">
  </picture>
</p>
