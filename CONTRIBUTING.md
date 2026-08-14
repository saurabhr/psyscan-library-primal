# Contributing a task or experiment card

1. Add your card as a single file:
   - task card → `tasks/<name>.json`
   - experiment card → `experiments/<name>.json`
2. Validate it locally:
   ```bash
   pip install -e .  # installs the pinned psychscanner-primal version
   python scripts/validate_contribution.py tasks/<name>.json
   ```
   This checks, in order: required fields are present, the filename/content
   isn't a duplicate of an existing card, and — the hard requirement — **the
   card actually runs end-to-end** against the built-in mock LLM. A card that
   raises during a real run will not be merged.
3. Regenerate the ledger and commit it:
   ```bash
   python scripts/index_ledger.py build
   ```
4. Open a PR. CI re-runs the same two checks on every changed card.

## Existing seed cards

`tasks/rm_singleturn_demo.json` was copied in from `psychscanner-primal`'s
own `examples/tasks/` (shared byte-for-byte with `psychscanner`'s copy of
the same file) to bootstrap this index — it's not auto-synced. This repo is
now the source of truth for it going forward; if either main repo's copy
ever changes, treat that as the one that drifted, not this one.

This is separate from packaging a card for the Prime Intellect Hub
(`environments/<name>/` in `psychscanner-primal`) — that flow still lives in
the source repo and covers `verifiers`-style environment packages, not
individual cards.
