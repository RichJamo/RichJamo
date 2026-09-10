### Richard Jamieson

Protocol architect and engineering lead. I design, build and secure DeFi infrastructure:
Solidity contracts, cross-chain vault systems, and the off-chain services that settle them
on-chain.

I am Senior Smart Contract Engineer at [Hydrex](https://hydrex.fi), a concentrated-liquidity
DEX on Base, and the sole engineer on its liquidity-mining reward system. Before that I
founded Amana DeFi, an omnichain yield aggregator on ZetaChain, and wrote its protocol layer.

Most of my protocol work sits in private repositories. The green squares above are Hydrex:
governance, emissions and treasury contracts, and the reward pipeline behind them. You cannot
read any of it. So here is what I can actually show you.

### Public work

**[clean-report-problem](https://github.com/RichJamo/clean-report-problem).** I tried four
ways to hide a critical bug from an AI code auditor. Three failed. One got me caught, and the
fourth was not an attack at all. Seventy runs, every transcript committed.

**[hydrex-periphery](https://github.com/RichJamo/hydrex-periphery).** Hydrex's auxiliary
contracts, in Foundry. The token, the Basedrop campaign, escrow, and the conduits that
automate parts of the protocol.

**[Amana-monorepo](https://github.com/AmanaDefi/Amana-monorepo/pulls?q=is%3Apr+author%3ARichJamo).**
Fifty-two pull requests across the vault system, the Solana integration, and the Balancer and
Curve strategies. It is public, and browsable.

**[hydrex-optimiser](https://github.com/RichJamo/hydrex-optimiser).** Python that indexes
voting and bribe data on Linea, then solves for a weekly vote allocation.

### Security

I was the sole counterpart to external auditors across four engagements at Hydrex. The
decentralisation workstream I delivered came back with zero high-severity findings across
fifteen contracts, and no failed remediations. I took Amana through audit by Linum Labs. I
took Crystl Finance's V3 vaults through HashEx, where both reports are public. I compete in
audit contests, with accepted findings on HackenProof.

Most of the bugs I have found in production did not throw an error. They balanced. They
reconciled. They were quietly paying the wrong number to the wrong person, for weeks, and the
only way to catch that is to reason about state transitions rather than wait for something to
go red.

Solidity · Foundry · ERC-4626 · cross-chain · TypeScript · NestJS · PostgreSQL · Python

[richardjamieson.co.za](https://richardjamieson.co.za/) · jamieson.rich@gmail.com
