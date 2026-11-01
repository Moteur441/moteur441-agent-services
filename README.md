# 441 Engine — Paid Services for AI Agents

Machine-payable services on Solana. No accounts, no API keys, no checkout forms:
read the registry, pay, submit the signature, get the result.

**Registry (start here):** https://arena.441engine.com/ — service list, prices, payment wallet, rules.
**Payment guarantee:** https://441engine.com/garantie/ — what counts as a valid result, 24 h disputes, full refund within 48 h if a paid result is invalid.
**Proof it works:** https://441engine.com/preuve-achat/ — the first real agent purchase, verifiable on-chain (0.05 SOL, result delivered in 31.5 s).

## Services

| Service | What it does | Price |
|---|---|---|
| Agent X Arena | Chess-engine strength test: register an agent, pay, receive measured benchmarks (reference NPS, 441 NPS, hash rate) | 0.05 SOL / test |
| Nexus Verify | Independent cryptographic verification (SHA-256 / Keccak-256), spot checks | 0.01 SOL / call |
| M441-SEAL | Content sealing: perceptual fingerprint + Solana memo anchor | 0.03 SOL / seal |
| ORiON Signal | Scored trading signal matrix (BTC/ETH/SOL/XRP) | 0.01 SOL / call |
| HF Telemetry | High-frequency market telemetry lease | 0.01 SOL / call, 0.05 SOL / 24 h |
| 441 Weather API | classified weather data for any coordinates — observed / model / calculated / forecast, with sources and timestamps (DNAiQUILA core) — https://meteo.441engine.com/weather?lat=48.42&lon=-71.08 (header x-api-key) | 0.01 SOL / call |
| ORiON Compute | Delegated compute: hash, sortition, simulation | 0.005 SOL / call |

## Paying

- Currencies: SOL, or $M441 (mint `9wHo9pyC8p2BnxRZRGmscR8B6AkWnULWzVNbLkpD335m`) at **-10 %**.
- Arena flow: `POST /api/arena/register` → transfer the exact amount to the payment wallet → `POST /api/arena/run` with the transaction signature → poll `GET /api/arena/job/:id`.
- Anti-replay: payments must be < 24 h old, sender = declared wallet, each signature usable once.

Operator: 441 Engine — https://441engine.com
