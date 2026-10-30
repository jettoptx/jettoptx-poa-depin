
## Solana mainnet pre-merge checklist
<!-- See docs/MAINNET-PREMERGE-CHECKLIST.md (source: r0bre / Accretion). Mark N/A with a reason. -->
- [ ] 1. Upgrade authority behind a multisig (not 1-of-m, not m-of-m) plus a timelock
- [ ] 2. Every account validated: owner, discriminator, seeds, signer, writable
- [ ] 3. Every CPI target pinned to a known program ID
- [ ] 4. remaining_accounts treated as hostile: count, order, owner, duplicates
- [ ] 5. No plain init on addresses others can create first (especially ATAs)
- [ ] 6. Accounts closed properly so they can't be revived
- [ ] 7. Checked math, rounding in the protocol's favor, no lossy casts
- [ ] 8. Accounting doesn't trust raw token balances
- [ ] 9. Monitoring, pause switch, incident plan with names and contacts
- [ ] 10. security.txt present
