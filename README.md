# claude-transcript

Convert Claude Code JSONL session files to readable markdown transcripts.

## Provenance

This is a fork of the [`claude-transcript`](https://pypi.org/project/claude-transcript/) package published on PyPI (v1.0.0) by John Lam (`jlam@iunknown.com`). The package metadata declares `anthropics/claude-transcript` as the upstream repository, but that URL returns a 404 — either private or not yet published. With no public repo or issue tracker available, this fork exists to track bug fixes and keep the tool working.

If the upstream repo becomes public, this fork should be reconciled or retired.

Original license: MIT.

## Changes from upstream

- **v1.1.0**: Fix `datetime.replace(minute=60)` crash in `_find_related_sidechain` when sidechain entries land at minute :59 — use `timedelta` instead of raw arithmetic.

## Install

```bash
# From GitHub
uv tool install git+https://github.com/prefrontalsys/claude-transcript

# From local clone
git clone https://github.com/prefrontalsys/claude-transcript.git
uv tool install --force ./claude-transcript
```

## Usage

```bash
claude-transcript session.jsonl
claude-transcript session.jsonl -o output.md
claude-transcript session.jsonl --upload-gist
```

## Features

- Zero dependencies — pure Python 3.8+
- Parses all JSONL entry types: tool operations, sidechains, timing info
- Optional GitHub Gist upload via `gh` CLI
