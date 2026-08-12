# What is the hosts file?

**Direct answer:** The **hosts file** is a local text file that maps domain names to IP addresses before DNS is queried. On macOS and Linux it is `/etc/hosts`; on Windows it is `C:\Windows\System32\drivers\etc\hosts`. Developers use it for local domains, staging tests, and temporary overrides.

Last updated: 2026-08-12

## Example entry

```text
127.0.0.1   app.test
::1         app.test
```

That line makes `app.test` resolve to your machine without public DNS.

## Common uses

- Local development with pretty domains
- Pre-DNS cutover testing against a staging IP
- Blocking hosts by pointing them at `0.0.0.0` or `127.0.0.1`
- Per-client overrides for freelancers

## Risks of hand-editing

- Needs admin / `sudo` rights
- Syntax typos fail silently from the user’s point of view
- No built-in environments or backups
- DNS cache can hide successful edits until flushed

## Tools

A [hosts file manager](../../README.md) such as Sleezr edits this file through a UI with environments, backups, and DNS flush. Guides: [macOS](../guides/edit-hosts-file-macos.md) · [Windows](../guides/edit-hosts-file-windows.md) · [Linux](../guides/edit-hosts-file-linux.md)
