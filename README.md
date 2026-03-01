# claude-transcript

Convert Claude Code JSONL session files to readable markdown transcripts.

Forked from the PyPI `claude-transcript` package (v1.0.0, John Lam) because the
declared upstream repo (`anthropics/claude-transcript`) is a 404.

## Changes from upstream

- **v1.1.0**: Fix `datetime.replace(minute=60)` crash when sidechain entries land at minute :59 — use `timedelta` instead of raw arithmetic.

## Install

```bash
uv tool install --force ~/projects/claude-transcript
```

## Usage

```bash
claude-transcript session.jsonl
claude-transcript session.jsonl -o output.md
claude-transcript session.jsonl --upload-gist
```
