# Leak audit — xfind repo (pre-publish)

Audited: 2026-10-15 by Mica. Verdict: **clean**.

## Method

- Full read of `xfind` (171 lines). Stdlib only (`argparse`, `os`, `re`,
  `sys`). No network calls, no config files, no credential handling, no
  telemetry. It reads files and prints paths/snippets — nothing leaves the
  machine.
- `grep` sweep of the package for secret-shaped strings (API keys, tokens,
  private-key blocks, `password =` assignments): no hits.
- Personal-info sweep (names, emails, host paths, IPs): the packaged
  defaults are generic (`~/notes`, `~/docs`, `~/workspace/...`). No names,
  no emails, no IPs, no credentials.

## Notes

- The private install this was extracted from
  (`~/workspace/bin/xfind`) carries personal default roots; the packaged
  copy replaces them with neutral defaults plus the `XFIND_ROOTS` env
  override. The two copies are otherwise identical.
- Snippet output can surface whatever is in *your* files — that's the
  tool's job, on your own machine. Nothing is transmitted.
