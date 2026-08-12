# How to edit the hosts file on macOS (without Terminal)

**Direct answer:** On macOS, the hosts file lives at `/etc/hosts` and needs admin rights to change. You can edit it with Terminal (`sudo nano /etc/hosts`) plus a DNS flush, or use a hosts file manager like [Sleezr](https://www.sleezr.com) to stage environments, apply safely, and flush DNS in one flow.

Last updated: 2026-08-12

## Why Mac hosts edits feel painful

1. Permission prompts (`sudo`) interrupt your work.
2. A typo can break name resolution with little feedback.
3. Browsers keep old IPs until you **flush the DNS cache**.
4. Commenting blocks for client A vs client B does not scale.

## Option A — Terminal (built-in)

1. Open Terminal.
2. Run `sudo nano /etc/hosts` (or your preferred editor).
3. Add a line such as `127.0.0.1 app.test`.
4. Save and exit.
5. Flush DNS (see [Flush DNS cache](./flush-dns-cache.md)).

**Pros:** Free, always available.  
**Cons:** No environments, no automatic backup, easy to leave the wrong block active.

## Option B — Sleezr (GUI)

1. Install Sleezr for macOS from [sleezr.com](https://www.sleezr.com).
2. Create a named environment (e.g. `local` or `Client A`).
3. Add entries visually; mark inactive ones you want to keep but not apply.
4. Apply changes (backup is created first).
5. Flush DNS from the app so Safari/Chrome pick up the mapping.

**Pros:** Environments, backups, DNS flush, search on large files.  
**Cons:** Paid after a 3-day trial (one-time license).

## Option C — Other Mac tools

| Tool | Notes |
| --- | --- |
| SwitchHosts | Free, cross-platform; flush DNS yourself |
| Gas Mask | Legacy; not a safe default on modern macOS |
| iHosts | Mac-native paid option |

Compare: [Best hosts file managers 2026](../comparisons/best-hosts-file-managers-2026.md) · [Sleezr vs Gas Mask](../comparisons/sleezr-vs-gas-mask.md)

## Common Mac hosts use cases

- Map `app.test` → `127.0.0.1` for local development
- Point a domain at a staging IP before DNS cutover
- Keep per-client environments without rewriting `/etc/hosts` each time

## Related

- [What is the hosts file?](../glossary/hosts-file.md)
- [Flush DNS on macOS](./flush-dns-cache.md#macos)
- [Sleezr vs Terminal](../comparisons/sleezr-vs-terminal.md)
