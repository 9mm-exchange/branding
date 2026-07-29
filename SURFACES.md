# 9MM Pro — Ecosystem Surface Directory

This is the canonical naming and boundary reference. It keeps the family coherent
without pretending that every product shares the same flow, claims, integrations,
release state, or implementation of this reference.

## Family identity

- Masterbrand: `9MM.PRO`, all caps in JetBrains Mono, with the `.` in brass.
- Standard product lockup: `9MM.PRO / PRODUCT_LABEL`.
- 9x exception: `9X.SWAP` is its established standalone routing lockup; retain
  `9MM.PRO` in surrounding navigation, metadata, or attribution as appropriate.
- Use the masterbrand mark plus a typeset lockup. Do not invent new product logos
  or use unapproved third-party/chain artwork as a product mark.

## Product and environment map

| Surface | Canonical label | Role | State and boundary |
|---|---|---|---|
| `9mm.pro` | `9MM.PRO` | Masterbrand hub and suite discovery | `LIVE`. Product discovery, ecosystem tokens, collections, and docs. It does not replace a product's source of truth. |
| `dex.9mm.pro` | `9MM.PRO / DEX` | V2/V3 trading and liquidity | `LIVE`. Trading-specific UI and execution remain product-owned. |
| `9x.9mm.pro` | `9X.SWAP` | Multi-chain DEX aggregation and cross-chain price discovery | `LIVE`. Routing and execution language belongs here, not in Claim or Gate. |
| `claim.9mm.pro` | `9MM.PRO / CLAIM` | Holder rewards and verified claims | `LIVE`. Use neutral shared language: holder rewards, verified claims, non-custodial. Eligibility, cadence, allocation, and disclosures are product-owned. |
| `claim-dev.9mm.pro` | `9MM.PRO / CLAIM` | Pre-production Claim environment | `DEV`. An environment descriptor, never a separate consumer product or product mark. Do not present its schedules or states as production facts. |
| `gate.9mm.pro` | `9MM.PRO / ROYAL_GATE` | Royal Club eligibility and Telegram access | `LIVE` when the product states it. Distinct from Claim: access verification is not a reward, transaction, or claim. |
| `xch.9mm.pro` | `9MM.PRO / XCH_TERMINAL` | Chia market terminal and routed market discovery | `BETA` when the product states it. Chia-specific markets, data, and disclosures stay product-owned. |
| `launch.9mm.pro` | `9MM.PRO / LAUNCH` | Robinhood Chain token launchpad | `SOON`. Public access, wallet/RPC/API/proof/claim behavior, and chain support must not be inferred from this reference. |

## Status vocabulary

Use an explicit text label with any color or icon. A status only describes the
surface or presentation state; it never proves an on-chain, financial, legal, or
security claim.

| Label | Meaning | Allowed use |
|---|---|---|
| `LIVE` | Publicly available surface | A product may use it only for its own confirmed availability. |
| `BETA` | Public test/beta surface | Pair with the relevant product disclosure. |
| `DEV` | Non-production environment | Keep out of customer-facing product navigation unless the context is clearly developer-facing. |
| `SOON` | Informational future surface | No wallet, RPC, API, proof, claim, allocation, or transaction implication. |
| `UNAVAILABLE` | A known feature/data path cannot be used | Product-owned runtime state, not a marketing status. |

Robinhood Chain and Arc Chain are `SOON` informational placeholders until their
respective products explicitly support them. Their source artwork is included for
accurate presentation only; it does not declare either network active or enable
wallet, RPC, API, proof, claim, or transaction behavior.

## Reusable shell primitives

These visual patterns are reference recipes, not shared runtime components. Use
them only when you choose to implement an equivalent local pattern in a product.

- `.product-lockup` for the masterbrand/product relationship.
- `.system-status` for a text-first `LIVE`, `SOON`, `DEV`, or `BETA` status.
- `.step-rail` for ordered flow progress such as connect, sign, and verify.
- `.network-chip` and `.network-chip.is-soon` for active versus informational
  network references.

Keep the semantic meaning local to the product. A Gate step rail must not imply a
Claim transaction; a Claim status must not imply an entitlement; and an upcoming
network chip must not enable a connection path.

## Asset inventory and ownership

The pack currently contains masterbrand marks/favicons/fonts; chain assets for
PulseChain, Base, Ethereum, Sonic, Chia, Robinhood, and Arc; 9MM and PUSSY token
art; 9x and nineEx protocol art; and OG/PUSSY NFT art. Use only assets physically
present in this repository and approved for the intended surface. See
[`assets/README.md`](assets/README.md) for source provenance.

BSC and Solana artwork remain in `assets/chains/` for compatibility but are
legacy/unassigned: they are not part of the active-suite directory. Chain and
protocol art is context-specific; it must never be recast as a new 9MM product
mark.

## Copy guardrails

- Prefer short, declarative terminal language: `PROOF_GATED`,
  `CROSS_CHAIN_PRICE_DISCOVERY`, `NON_CUSTODIAL_INTERFACE`.
- Use Claim-neutral shared language. Product-specific rules control rewards,
  rounds, resets, allocations, eligibility, and legal statements.
- `allocated` does not mean `claimable`; `SOON` does not mean supported; and a
  status/trust claim needs product-specific evidence.
- A product owns its legal, technical, and transactional copy. Do not copy it
  into this reference unless it is a stable brand convention.
