### Richard Jamieson

Full-stack engineer, mostly backend. Since 2021 I've worked in crypto, writing smart
contracts and the backend services and front ends that sit around them.

At [Hydrex](https://hydrex.fi), a DEX on Base, I started on the contracts, then built the
service that pays out the protocol's liquidity rewards and ran it as its only engineer:
NestJS and TypeScript on PostgreSQL, with TimescaleDB and Redis. I was there on contract from
November 2025 to September 2026, and I've stayed on part-time since as a consulting engineer.
Before that I founded Amana DeFi, a cross-chain yield aggregator on ZetaChain.

Most of that work sits in private repositories. The green squares above are mostly Hydrex:
the reward service, and the governance, emissions and treasury contracts around it. You cannot
read any of it, though the service is written up on
[my site](https://richardjamieson.co.za/work/hydrex.html). So here is what I can actually
show you.

### Public work

**[Amana DeFi](https://github.com/AmanaDefi/Amana-monorepo).** An omnichain yield aggregator
on ZetaChain: a Next.js front end over ERC-4626 vaults on six mainnet chains, routing deposits
into twenty-one yield strategies across Aave, Compound, Convex, Balancer and Fluid. I founded
it and wrote 94% of the Solidity: the vault base and strategy layer, the per-chain swap
helpers, a gas tank that funds cross-chain calls, a zap contract, the treasury and the price
oracle, with 9,309 lines of tests. I also wrote much of the front end, 282 commits to
`frontend/`, second only to the lead front-end developer: React with TanStack Query, wagmi and
viem.

The hard part was share pricing. A vault on one chain holds its assets in a strategy on
another, so `totalAssets()` can only read the figure that arrived on the last cross-chain
confirmation. A deposit in flight is real but invisible, and anyone depositing in that window
buys shares against a stale NAV, at the expense of the holders already in. I moved the mint to
confirmation rather than to deposit, which removes the window instead of narrowing it.

**[aavev3-indexer-envio](https://github.com/RichJamo/aavev3-indexer-envio).** A TypeScript
indexer for Aave v3 on Base, built on Envio. Thirteen contract groups behind one GraphQL schema
of about twenty entities. Written to learn the framework, not to run in production.

**[clean-report-problem](https://github.com/RichJamo/clean-report-problem).** I tried four
ways to hide a critical bug from an AI code auditor. Three failed. One got me caught, and the
fourth was not an attack at all. Seventy runs, every transcript committed.

**[audit-harness](https://github.com/RichJamo/audit-harness).** The enforcement half of the
method I use in audit contests, with Claude Code doing much of the hunting. It holds two rules
in place: a hypothesis is killed only by a proof of concept that fails, never by an argument,
and a person decides scope, not the model. While those rules were written only in prose, one
audit broke the first on 7 of 11 parked rows. Now a ledger tool and two Claude Code hooks refuse
the change instead. MIT-licensed.

**[hydrex-periphery](https://github.com/RichJamo/hydrex-periphery).** Hydrex's auxiliary
contracts, in Foundry. The token, the Basedrop campaign, escrow, and the conduits that
automate parts of the protocol.

**[hydrex-lp-selection](https://github.com/RichJamo/hydrex-lp-selection).** Python that picks
which liquidity pools Hydrex should back each week, then scores last week's picks. Forked from a
colleague's dashboard; the discovery, selection and retention layers are mine. It has run daily
on GitHub Actions since July 2026.

**[hydrex-optimiser](https://github.com/RichJamo/hydrex-optimiser).** Python that indexes
voting and bribe data on Linea, then solves for a weekly vote allocation.

### Security

I was the sole counterpart to external auditors across four engagements at Hydrex. The
decentralisation workstream I delivered came back with zero high-severity findings across
fifteen contracts. I took Amana through audit by Linum Labs, and Crystl Finance's vaults
through HashEx, where both reports are public. Since June 2026 I've done independent security
research, with confirmed findings on HackenProof and Cyfrin CodeHawks.

TypeScript · Node.js · NestJS · PostgreSQL · Redis · React · Next.js · Solidity · Foundry · Python

[richardjamieson.co.za](https://richardjamieson.co.za/) · [LinkedIn](https://www.linkedin.com/in/richard-jamieson-9a06964/) · jamieson.rich@gmail.com
