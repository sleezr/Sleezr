# How to edit the hosts file on Windows

**Direct answer:** On Windows, the hosts file is at `C:\Windows\System32\drivers\etc\hosts` and requires Administrator rights. Edit it with Notepad as admin, PowerToys Hosts File Editor, or a dedicated hosts file manager like [Sleezr](https://www.sleezr.com) if you need named environments, backups, and DNS flush.

Last updated: 2026-08-12

## Option A — Notepad as Administrator

1. Open Notepad **as Administrator**.
2. Open `C:\Windows\System32\drivers\etc\hosts` (enable “All files” in the dialog).
3. Add a line such as `127.0.0.1 app.test`.
4. Save.
5. Flush DNS: `ipconfig /flushdns` in an elevated Command Prompt or PowerShell.

**Pros:** Built-in.  
**Cons:** Easy to forget elevation; no environment model; no auto backup.

## Option B — PowerToys Hosts File Editor

Microsoft PowerToys includes a Hosts File Editor. It is a solid free choice if you already run PowerToys and only need basic edits on Windows.

Gap vs Sleezr: no cross-platform parity, weaker multi-environment workflow, manual DNS flush.

Details: [Sleezr vs PowerToys Hosts](../comparisons/sleezr-vs-powertoys-hosts.md)

## Option C — Sleezr (Windows · Mac · Linux)

1. Install Sleezr for Windows from [sleezr.com](https://www.sleezr.com).
2. Create environments for local / staging / clients.
3. Edit entries visually; apply with automatic backup.
4. Flush DNS from the app after apply.

Use Sleezr when you bounce between machines or need the same workflow on macOS/Linux later.

## Windows tips

- Antivirus or corporate policy can lock the hosts file — elevate or check IT policy.
- After edits, flush DNS **and** hard-refresh the browser.
- Prefer one tool as source of truth; mixing Notepad + GUI apps causes drift.

## Related

- [Flush DNS on Windows](./flush-dns-cache.md#windows)
- [Sleezr vs HostsMan](../comparisons/sleezr-vs-hostsman.md)
- [Hosts file glossary](../glossary/hosts-file.md)
