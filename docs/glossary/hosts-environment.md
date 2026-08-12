# What is a hosts environment?

**Direct answer:** A **hosts environment** is a named set of hosts entries you activate together — for example `Client A`, `staging`, or `local`. Instead of commenting blocks inside one hosts file, you switch environments and apply the active set to the system hosts file.

Last updated: 2026-08-12

## Why environments beat comment blocks

Commenting and uncommenting lines does not scale when you juggle several clients or stages. Environments keep each context intact, make the active set obvious, and reduce “wrong client still live” mistakes.

## Sleezr vocabulary

| Term | Meaning |
| --- | --- |
| Environment | Named group of mappings |
| Entry | Single IP → domain row |
| Apply | Write to the system hosts file |
| Inactive | Entry kept but not applied |

How-to: [Switch hosts environments](../guides/switch-hosts-environments.md)

## Related

- [Hosts file](./hosts-file.md)
- [Sleezr vs Terminal](../comparisons/sleezr-vs-terminal.md)
