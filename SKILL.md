# xfind

Cross-section search across the agent's workspace — memory, skills, goals,
projects, docs. Give it query terms, get ranked filepaths + context snippets.

## Use when

- Starting a task where relevant prior work might exist
- You need to find something across memory, skills, goals, or projects
- Instead of guessing or re-researching

## Quick start

```bash
xfind <query terms>           # search with personal defaults
XFIND_ROOTS="/path/a /path/b" xfind <query>   # override search roots
```

## Scripts (bin/)

| Script | When to use |
|--------|-------------|
| `xfind` | Cross-section search. Set `XFIND_ROOTS` to override the default roots. |

## References

- `AUDIT.md` — no network calls, credentials, personal names, or IPs
- `references/` — usage patterns and examples
