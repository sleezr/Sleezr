# How to flush DNS cache (macOS, Windows, Linux)

**Direct answer:** After you change the hosts file, flush the OS DNS cache (and hard-refresh the browser) or you may keep resolving the old IP. Commands differ by OS; a hosts file manager like [Sleezr](https://www.sleezr.com) can run the right flush after Apply.

Last updated: 2026-08-12

## Why flush DNS after hosts edits?

The operating system caches DNS answers. Your hosts file may say the new IP while the browser or resolver still uses the previous one. Flushing clears that cache so the new mapping is used.

## macOS

```bash
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
```

On some versions you may also need:

```bash
sudo killall -HUP mDNSResponderHelper
```

Then quit/reopen the browser or hard-refresh.

## Windows

Open **Command Prompt or PowerShell as Administrator**:

```bat
ipconfig /flushdns
```

Optional: restart the browser. Corporate DNS clients (VPN, security agents) may need their own refresh.

## Linux

Depends on the resolver:

```bash
# systemd-resolved (common)
sudo resolvectl flush-caches

# nscd
sudo systemctl restart nscd

# dnsmasq
sudo systemctl restart dnsmasq
```

If unsure: `resolvectl status` helps confirm systemd-resolved is active.

## Browser cache vs DNS cache

Flushing OS DNS is not the same as clearing browser HTTP cache. After a hosts change:

1. Flush OS DNS.
2. Hard-refresh or restart the browser.
3. If still wrong, check VPN / AdGuard / NextDNS / Pi-hole / MagicDNS overrides.

## Using Sleezr

Sleezr can flush DNS as part of the apply workflow so you do not memorize per-OS commands. Details: [sleezr.com](https://www.sleezr.com) · Docs: [docs.sleezr.com](https://docs.sleezr.com)

## Related

- [What is DNS cache?](../glossary/dns-cache.md)
- [Edit hosts on macOS](./edit-hosts-file-macos.md)
- [Edit hosts on Windows](./edit-hosts-file-windows.md)
