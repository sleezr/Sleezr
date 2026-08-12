# Local development domains (app.test, localhost alternatives)

**Direct answer:** **Local development domains** are hostnames (like `app.test` or `api.myapp.local`) that resolve to `127.0.0.1` or another local IP via the hosts file. They make cookies, HTTPS, and multi-service setups closer to production than raw `localhost:3000` URLs.

Last updated: 2026-08-12

## Typical hosts line

```text
127.0.0.1   app.test api.app.test
```

## Why teams use them

- Separate cookies / storage per project hostname
- Test subdomain routing locally
- Match staging hostnames before DNS cutover
- Avoid port-only URLs in screenshots and docs

## How to manage many local domains

When you have dozens of mappings across clients, a hosts file manager with search and environments beats a single growing `/etc/hosts` file. See [Switch hosts environments](../guides/switch-hosts-environments.md) and [Sleezr](https://www.sleezr.com).

## Related

- [What is the hosts file?](./hosts-file.md)
- [Flush DNS cache](../guides/flush-dns-cache.md)
