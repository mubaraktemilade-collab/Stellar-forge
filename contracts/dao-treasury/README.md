# DAO Treasury

The DAO treasury is a Soroban smart contract that holds a token balance and releases it only through committee-approved spending proposals. A designated admin can manage configuration with a timelock, but asset transfers require the configured unique-signer threshold and cannot be executed by one key alone.

## Public functions

- `__constructor` initializes the admin, treasury token, committee, signature threshold, and configuration timelock.
- `deposit` transfers an approved amount of the treasury token from a depositor into the contract and records the new balance.
- `propose` creates a spending proposal for a recipient and amount, authorized by a committee member or the admin.
- `execute_proposal` verifies the proposal signatures and executes the transfer once the configured quorum is reached.
- `cancel_proposal` cancels a pending proposal when called by the admin or the original proposer.
- `queue_config_change` queues an updated committee or signature threshold for approval after the timelock delay.
- `apply_config_change` applies a queued threshold or committee change after the timelock has elapsed.
- `cancel_config_change` removes a pending configuration change when called by the admin.
- `set_admin` replaces the contract administrator when called by the current admin.
- `admin` returns the current administrator address.
- `token` returns the token contract address used by the treasury.
- `committee` returns the currently authorized committee addresses.
- `threshold` returns the number of unique committee signatures required to execute a proposal.
- `timelock_delay` returns the number of ledgers required before a queued configuration change can be applied.
- `nonce` returns the current proposal nonce used to prevent replay.
- `proposal_count` returns the number of proposals created by the contract.
- `get_proposal` returns the details for a proposal ID, if it exists.
- `pending_change` returns the queued configuration change, if any.
- `balance` returns the treasury's current token balance.
- `bft_min_threshold` calculates the Byzantine-fault-tolerant minimum threshold for the current committee size.

## Build and test

Build the contract from the repository root:

```bash
cargo build --manifest-path contracts/dao-treasury/Cargo.toml --target wasm32-unknown-unknown --release
```

Run the contract tests:

```bash
cargo test --manifest-path contracts/dao-treasury/Cargo.toml
```
