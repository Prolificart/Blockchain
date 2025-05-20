# Blockchain

# Heat Stamp Token Presale Setup (Solana Devnet)

This guide outlines the complete setup and successful execution of the Heat Stamp token presale across four phases using the Solana CLI and SPL Token tools.

---

## ✨ Project Summary

* **Token Name:** Heat Stamp
* **Blockchain:** Solana (Devnet)
* **Token Type:** SPL Token
* **Total Supply:** 5,000,000 tokens
* **Presale Allocation:** 2,000,000 tokens (divided into 4 phases)

---

## 💱 Presale Phase Structure

| Phase   | Tokens Minted | Price (SOL) | Notes               |
| ------- | ------------- | ----------- | ------------------- |
| Phase 1 | 500,000       | 0.10        | Early Access        |
| Phase 2 | 500,000       | 0.25        | Round 2             |
| Phase 3 | 500,000       | 0.50        | Round 3             |
| Phase 4 | 500,000       | 1.00        | Final Presale Round |

Remaining 3,000,000 tokens are retained in the team wallet.

---

## 📂 Key Files & Wallets

Each presale phase was assigned its own Solana wallet:

```bash
~/phase1.json
~/phase2.json
~/phase3.json
~/phase4.json
```

Wallets were funded via:

```bash
solana airdrop 2 --keypair ~/phaseX.json
```

---

## ⚖️ Mint Details

* **Mint Address:** `3Noi6dovrgiNjiaLyppe3AtoqwPDQDCbXYHpQSkXsw7e`
* **Mint Authority:** Default wallet (`~/.config/solana/id.json`)

---

## 🚀 Token Account Creation (One per Phase)

Created token accounts for each phase using:

```bash
spl-token create-account <MINT_ADDRESS> --owner ~/phaseX.json --fee-payer ~/.config/solana/id.json
```

Verified using:

```bash
spl-token accounts --owner ~/phaseX.json
```

---

## 💸 Minting Tokens

After creating token accounts, 500,000 Heat Stamp tokens were minted into each phase:

```bash
spl-token mint <MINT_ADDRESS> 500000 <TOKEN_ACCOUNT_ADDRESS>
```

---

## ✅ Final Status

| Phase   | Wallet Created | Token Account | Minted Tokens |
| ------- | -------------- | ------------- | ------------- |
| Phase 1 | ✅              | ✅             | ✅ 500,000     |
| Phase 2 | ✅              | ✅             | ✅ 500,000     |
| Phase 3 | ✅              | ✅             | ✅ 500,000     |
| Phase 4 | ✅              | ✅             | ✅ 500,000     |

Team Reserve: 3,000,000 Heat Stamp (in original wallet)

---

## 🌌 Next Steps

* ✨ Set metadata (token name, symbol, logo)
* 🌐 Transition to Mainnet
* 💼 Build frontend for presale interface
* ⏳ Optional: Lock tokens with vesting logic

---

**Author:** Bruce J.
**Network:** Devnet
**Date:** 2025
