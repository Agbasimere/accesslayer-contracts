# Access Layer Contracts

This folder contains the on-chain smart contracts for Access Layer on Stellar using Soroban.

These contracts are where the trust-sensitive marketplace rules should live. The goal is to keep pricing, ownership, and fee logic on-chain while leaving general application features to the server and client.

## Purpose

The contracts layer will be responsible for:

- registering creators on-chain
- minting and burning creator keys
- enforcing bonding curve pricing
- handling buy and sell execution
- distributing creator and protocol fees
- exposing ownership and supply state to the app

## Tech

- Rust
- Soroban SDK
- Stellar

## Workspace layout

- [Cargo.toml](./Cargo.toml): Rust workspace configuration
- [creator-keys](./creator-keys): first Soroban contract crate

## Current state

The initial `creator-keys` contract is only a starting point. It currently supports:

- simple creator registration
- a basic purchase action that increments creator supply
- reading stored creator data

This is not the final marketplace logic. It is a clean scaffold for the real contract design.

## Expected next steps

1. Define the creator data model and storage keys more carefully.
2. Add buy and sell functions with payment handling.
3. Add bonding curve math and fee splits.
4. Add tests for pricing, supply changes, and permissions.
5. Prepare deployment scripts for Stellar testnet.

## Commands

From this folder:

```bash
cargo check
```

Later, once Soroban tooling is added, this folder should also include commands for test execution, contract build output, and deployment.

