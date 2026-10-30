# Solana Mainnet Pre-Merge Checklist

Source: r0bre (Accretion), https://x.com/r0bre/status/2116187118565507387

Every PR that touches an on-chain program, and every mainnet deploy or upgrade, must pass all ten items before merge. If an item doesn't apply, write "N/A" and give the reason.

1. **Upgrade authority**: behind a multisig (not 1-of-m, not m-of-m) plus a timelock.
2. **Account validation**: every account checks owner, discriminator, seeds, signer and writable.
3. **CPI targets**: every CPI target is pinned to a known program ID.
4. **remaining_accounts**: treated as hostile. Check count, order, owner and duplicates.
5. **No plain `init` on front-runnable addresses**: never use plain init on an address someone else can create first (especially ATAs). Use idempotent create, or `init_if_needed` with full constraints.
6. **Closing accounts**: accounts are closed properly (`close =`, zeroed data or discriminator) so they can't be revived in the same transaction.
7. **Math**: checked math, rounding in the protocol's favor, no lossy `as` casts.
8. **Accounting**: internal accounting doesn't trust raw token balances, which anyone can donate to.
9. **Operations**: monitoring, a pause switch, and an incident plan with named owners and contacts.
10. **security.txt**: embedded in the program (`solana-security-txt`).
