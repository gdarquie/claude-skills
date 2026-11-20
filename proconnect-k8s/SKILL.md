---
name: proconnect-k8s
description: Rules for ProConnect k8s deploy repo (proconnect-k8s), esp. sops secrets. Use before reading/editing/running anything there.
---

# ProConnect k8s

## Sops (strict)

- Never decrypt sops files (`sops -d`, `sops edit`, `helm secrets`, `kustomize` w/ ksops, any tool/plugin rendering them).
- Never `cat`/`Read` encrypted files: values useless and risk of leak. Detect via `.sops.yaml` rules, filename (`*.enc.*`, `secrets*`), or `sops:` / `ENC[` markers (`grep -l`, never print content).
- Never keep a trace of secret values: not in chat, files, commits, logs, memory, PR, scratchpad.
- Exception: **local env only** (kind cluster) may be decrypted if truly needed to run/test. Even then: pipe straight to the consumer (e.g. `sops -d … | kubectl apply -f -`), no file on disk, no printing, no trace kept.
- Need a non-local secret value or structure → ask user.

## Other

- Prefer kind + local env to test changes.
- Commits/PRs: follow `proconnect-commit`.
