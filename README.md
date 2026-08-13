# psyscan-library-primal

Public, versioned index of vetted task and experiment cards for
[psychscanner-primal](https://github.com/saurabhr/psychscanner-primal),
the slim, Hub-optimized distribution of psychscanner.

This repo is not the place to write library code — it's a curated data index.
Every card under `tasks/` and `experiments/` is a plain `psychscanner-primal`
task/experiment card (plain `.json` — primal has no special file-extension
convention), and every card here has been verified to actually load and run
end-to-end against the built-in mock LLM before being merged.

This index is separate from `psychscanner-primal`'s `environments/` folders,
which package tasks for Prime Intellect Hub distribution — those still live
in the source repo. This index is the general "official, vetted cards" list.

## Using a card

```python
from psychscanner import task_library

card = task_library("my_task", dirs="path/to/psyscan-library-primal/tasks")
```

## Compatibility

`pyproject.toml` pins the `psychscanner-primal` version this index was
validated against (`psychscanner-primal>=0.1.0`).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
