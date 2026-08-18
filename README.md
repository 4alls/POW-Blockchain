# POW-Blockchain

POW Blockchain coded in Python, it explains hashing and foundational principles that this technology uses.

## Overview

A minimal Proof-of-Work blockchain built from scratch in a Jupyter notebook (`block.ipynb`), with no external blockchain libraries — everything (hashing, chaining, mining) is implemented by hand to understand how it actually works.

## Features

- **SHA-256 hashing** — each block's hash is derived deterministically from its own fields (`hashlib` + `json.dumps(..., sort_keys=True)`).
- **Chained blocks** — each block stores the hash of the previous one (`previous_hash`), so tampering with any block breaks the chain.
- **Merkle tree** — a block's transactions are summarized into a single `merkle_root`; changing a single transaction changes the block's hash.
- **Proof of Work** — `proof_of_work()` brute-forces a `nonce` until the block's hash satisfies the required difficulty (leading zeros).
- **Dynamic difficulty adjustment** — `adjust_difficulty()` raises or lowers the mining difficulty after each block, based on how long mining took versus a target block time.
- **Chain validation** — `is_chain_valid()` walks the whole chain and checks that every block's hash, proof of work, and link to the previous block are still valid.
- **Pending transactions pool** — transactions are queued with `add_new_transaction()` and grouped into a block on the next `mine()` call.



