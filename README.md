# wlangeeks.com

The WLAN Geeks LLC company site — a single static page, served by GitHub Pages.

Built 2026-08-31 so the legal entity has a public web presence for Azure Artifact
Signing organization identity validation, which requires a "Website url" belonging
to the legal business entity. The domain previously resolved to a firewall and
served nothing.

## DNS

Nameservers stay at Google Cloud DNS. **Do not move them** — the domain carries live
Microsoft 365 mail records (MX, SPF, autodiscover) and a nameserver migration means
recreating every one of them by hand. Only the web records change:

| Type  | Name | Value |
|-------|------|-------|
| A     | @    | 185.199.108.153 |
| A     | @    | 185.199.109.153 |
| A     | @    | 185.199.110.153 |
| A     | @    | 185.199.111.153 |
| CNAME | www  | <user>.github.io |

The `CNAME` file in this repo must contain the apex domain, or GitHub Pages drops the
custom domain on the next deploy.
