# How to switch hosts environments (local, staging, client)

**Direct answer:** A hosts **environment** is a named set of IP → domain entries you can activate together. Instead of commenting and uncommenting blocks in `/etc/hosts`, you keep separate environments (e.g. `Client A`, `staging`) and switch which one is applied.

Last updated: 2026-08-12

## The problem environments solve

Developers often keep several conflicting blocks in one hosts file:

```text
# Client A
127.0.0.1 api.client-a.test

# Client B (commented… sometimes)
# 127.0.0.1 api.client-b.test
```

Hand-toggling those blocks causes:

- Wrong client still active
- Forgotten DNS flush
- No backup when a bad apply lands

## Environment model (Sleezr terminology)

| Term | Meaning |
| --- | --- |
| **Environment** | Named group of hosts entries (not “profile” / “workspace” in Sleezr UI) |
| **Entry** | One IP → domain mapping |
| **Apply** | Write the active configuration to the system hosts file |
| **Inactive entry** | Kept in the environment but not written as live |

Typical environment types: local, staging, prod, demo, client, custom, blocklist.

## How to switch with Sleezr

1. Create one environment per context (client, stage, or project).
2. Add entries with comments so context stays next to the line.
3. Switch the active environment when your task changes.
4. Apply — Sleezr backs up first, then writes hosts.
5. Flush DNS so browsers match the new file.

Export/import JSON environments when onboarding teammates ([Team](https://www.sleezr.com/team)).

## DIY without a GUI

You can keep separate files (`hosts.client-a`, `hosts.staging`) and copy the chosen file over `/etc/hosts` with a script. That works until you need search, validation, backups, and cross-platform parity — then a manager is faster.

Compare approaches: [Sleezr vs Terminal](../comparisons/sleezr-vs-terminal.md) · [Sleezr vs SwitchHosts](../comparisons/sleezr-vs-switchhosts.md)

## Related

- [What is the hosts file?](../glossary/hosts-file.md)
- [Flush DNS cache](./flush-dns-cache.md)
- Product overview: [README](../../README.md)
