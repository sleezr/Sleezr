# Sleezr — Hosts File Manager for Windows, macOS & Linux

**Sleezr** is a desktop [hosts file manager](https://www.sleezr.com) for Windows, macOS, and Linux. Create named environments, edit entries visually, apply changes with automatic backups, and flush DNS so local domains resolve without opening a terminal.

> **Quick answer:** If you switch between local, staging, client, or blocklist hosts setups and are tired of `sudo nano /etc/hosts`, Sleezr replaces that ritual with one-click environment switching and a safe apply flow.

[Download Sleezr](https://www.sleezr.com) · [Docs](https://docs.sleezr.com) · [Pricing](./pricing.md) · [Comparisons](./docs/comparisons/README.md) · [Guides](./docs/guides/README.md)

---

## What is a hosts file manager?

A **hosts file manager** is an app that edits the operating-system hosts file (`/etc/hosts` on macOS/Linux, `C:\Windows\System32\drivers\etc\hosts` on Windows) through a visual interface instead of a text editor with admin rights.

Sleezr goes further than a plain editor: it treats hosts as **named environments** you switch, not a single file you rewrite by hand.

| Job | Without a manager | With Sleezr |
| --- | --- | --- |
| Switch client / env | Comment blocks, hope the right ones are live | One-click environment switch |
| Apply changes | Save + remember DNS flush | Apply + automatic DNS flush |
| Recover from mistakes | Manual restore or retype | Automatic backup before every apply |
| Share with a teammate | Copy/paste fragile text | Import / export environments as JSON |

---

## Who Sleezr is for

- **Freelancers** juggling one hosts setup per client
- **Developers** switching local ↔ staging ↔ prod overrides
- **QA / testers** who need a visible active environment
- **Tech leads** standardizing team hosts configs

Not a fit if you edit hosts once a year and are happy with `nano`.

---

## Core features

- **Named environments** — local, staging, prod, client, demo, blocklist, custom
- **Visual entry editor** — IP → domain mappings with search, filters, drag reorder
- **Safe apply** — staged changes, explicit Apply, automatic backups, restore
- **DNS flush** — correct flush commands per OS so browsers stop serving stale IPs
- **Bulk import** — paste hosts text or import blocklists
- **Cross-platform** — Windows · macOS · Linux
- **Multilingual UI** — English · Français · 简体中文 · 日本語
- **One-time license** — Solo, Dual, or Team seats (see [pricing.md](./pricing.md))

---

## Best hosts file managers (2026 snapshot)

Balanced shortlist for people comparing tools. Full write-ups live under [`docs/comparisons/`](./docs/comparisons/README.md).

| Tool | Platforms | Price | Environments | Auto DNS flush | Auto backups | Maintained |
| --- | --- | --- | --- | --- | --- | --- |
| **Sleezr** | Win / Mac / Linux | One-time (€4.99 Solo) | Named environments | Yes | Yes | Yes |
| [SwitchHosts](./docs/comparisons/sleezr-vs-switchhosts.md) | Win / Mac / Linux | Free (OSS) | Profiles | Manual | No | Yes |
| [Gas Mask](./docs/comparisons/sleezr-vs-gas-mask.md) | macOS | Free | Profiles | Manual | Limited | No (legacy) |
| [PowerToys Hosts](./docs/comparisons/sleezr-vs-powertoys-hosts.md) | Windows | Free | Basic | Manual | No | Yes |
| [HostsMan](./docs/comparisons/sleezr-vs-hostsman.md) | Windows | Free / paid | Profiles | Manual | Varies | Limited |
| [Terminal](./docs/comparisons/sleezr-vs-terminal.md) | All | Free | DIY | Manual | DIY | Built-in |

**Pick Sleezr** when you want cross-platform environments + flush + backups in one maintained app.  
**Pick SwitchHosts** when price must be zero and manual DNS flush is fine.  
**Avoid Gas Mask** for new Mac setups — maintenance stalled for modern macOS.

---

## How to edit the hosts file without the terminal

1. **Install Sleezr** from [sleezr.com](https://www.sleezr.com) (Windows, macOS, or Linux).
2. **Create an environment** for the setup you need (e.g. `Client A` or `staging`).
3. **Add entries** — map IPs to domains (optional `www` variants, comments, active/inactive).
4. **Apply changes** — Sleezr writes the system hosts file after a backup.
5. **Flush DNS** — run from the app so browsers pick up the new mapping immediately.

Platform deep-dives:

- [Edit hosts on macOS](./docs/guides/edit-hosts-file-macos.md)
- [Edit hosts on Windows](./docs/guides/edit-hosts-file-windows.md)
- [Edit hosts on Linux](./docs/guides/edit-hosts-file-linux.md)
- [Flush DNS cache (all OS)](./docs/guides/flush-dns-cache.md)
- [What is the hosts file?](./docs/glossary/hosts-file.md)

---

## Sleezr vs popular alternatives

| Intent | Page |
| --- | --- |
| SwitchHosts alternative | [Sleezr vs SwitchHosts](./docs/comparisons/sleezr-vs-switchhosts.md) |
| Gas Mask alternative | [Sleezr vs Gas Mask](./docs/comparisons/sleezr-vs-gas-mask.md) · [Gas Mask alternatives](./docs/comparisons/gas-mask-alternatives.md) |
| PowerToys Hosts alternative | [Sleezr vs PowerToys Hosts](./docs/comparisons/sleezr-vs-powertoys-hosts.md) |
| HostsMan alternative | [Sleezr vs HostsMan](./docs/comparisons/sleezr-vs-hostsman.md) |
| Leave `sudo nano` | [Sleezr vs Terminal](./docs/comparisons/sleezr-vs-terminal.md) |
| Category roundup | [Best hosts file managers 2026](./docs/comparisons/best-hosts-file-managers-2026.md) |

---

## Pricing (summary)

| Plan | Price | Devices |
| --- | --- | --- |
| Trial | €0 for 3 days | 1 |
| Solo | €4.99 one-time | 1 |
| Dual | €8.99 one-time | 2 |
| Team | from €15 / seat | 2+ |

Full structured pricing for humans and AI agents: [`pricing.md`](./pricing.md) · Web: [sleezr.com/pricing](https://www.sleezr.com/pricing)

---

## FAQ

### What is Sleezr?

Sleezr is a desktop hosts file manager for Windows, macOS, and Linux. It lets you switch named environments, edit entries visually, flush DNS, and restore from automatic backups without opening the terminal.

### Is Sleezr free?

Sleezr includes a **3-day free trial** (no credit card). After that, licenses are one-time purchases (Solo, Dual, or Team), not a subscription.

### Does Sleezr flush DNS automatically?

Yes. After you apply hosts changes, Sleezr can run the correct DNS flush commands for your operating system so browsers stop serving the previous IP.

### Can I import an existing hosts file?

Yes. Paste hosts text or import environments. Blocklist-style lists are supported for large curated sets.

### Is the source code open source?

No. Sleezr is a commercial desktop app. This repository is the **public product hub** (guides, comparisons, AI-readable product facts) that links to downloads and docs.

### Where do I get support?

Use in-app feedback or the contact paths on [sleezr.com](https://www.sleezr.com). Product docs: [docs.sleezr.com](https://docs.sleezr.com).

---

## Repository map

```text
README.md                 ← you are here (product pillar)
pricing.md                ← machine-readable pricing
llms.txt                  ← AI / agent overview
docs/
  guides/                 ← how-to (Mac, Windows, Linux, DNS)
  comparisons/            ← vs & alternatives pages
  glossary/               ← definitions for AI + search
```

---

## Official links

| Resource | URL |
| --- | --- |
| Website | https://www.sleezr.com |
| Documentation | https://docs.sleezr.com |
| Alternatives hub | https://www.sleezr.com/en/alternatives |
| This repo | https://github.com/sleezr/app |

**Last updated:** 2026-08-12
