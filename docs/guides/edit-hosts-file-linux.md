# How to edit the hosts file on Linux

**Direct answer:** On most Linux distros the hosts file is `/etc/hosts` and needs root to edit. Use `sudo` with your editor, or a cross-platform hosts file manager like [Sleezr](https://www.sleezr.com) when you want named environments and a safer apply/backup loop.

Last updated: 2026-08-12

## Option A — Terminal

```bash
sudo nano /etc/hosts
# or
sudo vim /etc/hosts
```

Add a mapping, save, then flush the resolver cache for your stack (often `systemd-resolved`):

```bash
sudo resolvectl flush-caches
# older systems may use: sudo systemd-resolve --flush-caches
```

See [Flush DNS cache](./flush-dns-cache.md#linux) for variants (nscd, dnsmasq, etc.).

## Option B — Sleezr on Linux

1. Install the Linux build from [sleezr.com](https://www.sleezr.com).
2. Create environments for projects or clients.
3. Apply changes (backup first) and flush DNS from the app where supported.

Sleezr is useful when you also work on Windows/macOS and want one mental model.

## Linux gotchas

- **NetworkManager / systemd-resolved** can make “I edited hosts but nothing changed” feel like a browser bug — flush the right cache.
- Containers and VPNs (Tailscale MagicDNS, corporate split DNS) can override expectations; check those before blaming `/etc/hosts`.
- Keep a copy of working configs outside `/etc/hosts` (Sleezr environments or versioned files).

## Related

- [Edit hosts on macOS](./edit-hosts-file-macos.md)
- [Switch hosts environments](./switch-hosts-environments.md)
- [Sleezr vs SwitchHosts](../comparisons/sleezr-vs-switchhosts.md)
