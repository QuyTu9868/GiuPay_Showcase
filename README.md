# GiuPay

**Decentralized escrow payment dApp on Arc Testnet.**

GiuPay lets any shop accept USDC payments on-chain with buyer protection built in: funds sit in a smart-contract escrow for 14 days, disputes can be opened and resolved on-chain, and every completed purchase mints a soulbound warranty NFT as proof of purchase.

> 🔒 Source code is kept in a private repository for now. This repo shares what the project does, how it works, and links to verify it on-chain. Reach out if you'd like a closer look.

---

## What it does

- **Shop onboarding** — register a shop, admin verifies identity (email + 2FA) and confirms it on-chain via `ShopRegistry`.
- **On-chain escrow payments** — buyers pay in USDC directly on Arc, or bridge in from Ethereum / Base / Arbitrum / OP Sepolia via **Circle's CCTP**, landing straight into escrow.
- **14-day buyer protection** — funds auto-release to the shop after 14 days if no dispute is raised.
- **On-chain dispute resolution** — buyer opens a dispute, the shop can agree to refund (signs on-chain themselves), or an admin steps in to resolve.
- **Warranty SBT** — a soulbound ERC-721 is minted automatically once payment clears, acting as verifiable proof of purchase + warranty period. It burns itself once the warranty window expires.
- **Buyer ↔ shop chat** and **reviews** for every completed order.

## Tech stack

| Layer | Stack |
|---|---|
| Frontend | Next.js, wagmi + viem, RainbowKit |
| Backend | Node.js, Express, PostgreSQL |
| Smart contracts | Solidity (Hardhat), OpenZeppelin |
| Storage | IPFS (Pinata) |
| Payments | Native USDC on Arc, Circle CCTP for cross-chain bridging |

## Deployed contracts (Arc Testnet)

All verified and viewable on [Arc Explorer](https://testnet.arcscan.app):

| Contract | Address |
|---|---|
| ShopRegistry | `0x6E18Ba8Ce0841Ff58831629a5dd34AE37932cd6b` |
| PaymentEscrow | `0x38800A873C6bC877E025529D0798ae57cBFAaA69` |
| WarrantySBT | `0x2460C32eDA3134bCF3e284455Ed64d8c68F831C9` |

## Status

🚧 Testnet build, actively developed. Live demo link coming soon.

## Contact

Built by [@QuyTu9868](https://github.com/QuyTu9868).
