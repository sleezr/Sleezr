# What is DNS cache?

**Direct answer:** A **DNS cache** stores recent domain → IP answers so the OS and apps do not ask resolvers every time. After you change the hosts file, an old cached answer can make the browser keep the previous IP until you flush the cache.

Last updated: 2026-08-12

## Why it matters for hosts edits

1. You update `/etc/hosts` (or the Windows hosts file).
2. The file is correct.
3. The browser still loads the old site.
4. Flushing DNS (and refreshing the browser) fixes it.

That mismatch is one of the most common “hosts is broken” false alarms.

## How to flush

See the full command list: [How to flush DNS cache](../guides/flush-dns-cache.md)

Sleezr can run the correct flush after you apply hosts changes so you do not memorize OS-specific commands.

## Related terms

- [Hosts file](./hosts-file.md)
- [Hosts environment](./hosts-environment.md)
