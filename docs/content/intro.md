# psyscan-library-primal

![logo](../logo.png)

Public, versioned index of vetted task and experiment cards for
[psychscanner-primal](https://github.com/saurabhr/psychscanner-primal), the
slim, Hub-optimized distribution of psychscanner.

This repo is not the place to write library code — it's a curated data
index. Every card under `tasks/` and `experiments/` is a plain
psychscanner-primal task/experiment card (plain `.json` — primal has no
special file-extension convention), and every card has been verified to
actually load and run end-to-end against the built-in mock LLM before being
merged — not just checked for valid JSON.

This index is separate from `psychscanner-primal`'s `environments/` folders,
which package tasks for Prime Intellect Hub distribution — those still live
in the source repo. This index is the general "official, vetted cards" list.

## Compatibility

`pyproject.toml` pins the `psychscanner-primal` version this index was
validated against (`psychscanner-primal>=0.1.0`).

## Dedup

`INDEX_LEDGER.json` (repo root, derived, committed) hashes every card's
content so a contribution can't be added twice under different names, and
flags a filename that's already taken.

See [Browse the index](browsing.py) to pull cards from a checkout the same
way your own code would, or [Contributing a card](contributing.md) to add
one.
