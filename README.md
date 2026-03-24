# people-treasury
A decentralized treasury system for direct democracy using FROST and SLIP39
# People's Treasury

**English** | [中文](./README_zh.md)

A decentralized treasury system where **every citizen holds a key**. No representatives, no middlemen.

## Why

Governments spend public money. Citizens should control it.

This project uses threshold signatures (FROST) and secret sharing (SLIP39) to let any M out of N citizens approve a spending transaction, while keeping the final signature indistinguishable from a single-user wallet.

## How it works

- **Public key**: One single public key on-chain (no 2000 public keys)
- **Signing**: Any M of N citizens can collaboratively sign a transaction using FROST
- **Recovery**: If a citizen loses their key, any T other citizens can recover it using SLIP39
- **Governance**: All operations (spending, recovery, member changes) are recorded on-chain

## Components

- `frost/` - FROST threshold signature implementation (Rust)
- `slip39/` - Secret sharing for key recovery (Rust)
- `contract/` - Solana smart contract (Anchor)
- `client/` - CLI wallet for citizens
- `docs/` - Whitepaper and specifications

## Roadmap

### Phase 1: Core Crypto (2026.04 – 2026.05)
- [ ] FROST 3-of-5 prototype (local Rust)
- [ ] FROST 1000-of-2000 simulation (local Rust)
- [ ] SLIP39 30-of-2000 recovery prototype

### Phase 2: On-chain Integration (2026.06 – 2026.07)
- [ ] Solana smart contract with dynamic member list (Anchor)
- [ ] Integration: FROST signature → Solana transaction

### Phase 3: Client & UX (2026.08 – 2026.10)
- [ ] CLI wallet for citizens (Rust)
- [ ] Mobile wallet prototype (Flutter)

### Phase 4: Production & Submission (2026.11 – 2027.01)
- [ ] Testnet deployment
- [ ] Whitepaper and demo video
- [ ] **Hackathon submission** ✅

## Getting Started

```bash
# Clone
git clone https://github.com/yourusername/people-treasury.git
cd people-treasury

# Build FROST demo
cargo build --release
cargo run --example frost_3of5

# Run SLIP39 demo
cargo run --example slip39_3of5
