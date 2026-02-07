# Proof of Concept for Caddy with Cloudflare DNS Challenge

There is no "official" Caddy image that supports Cloudflare DNS. There however "unofficial" builds, such as [CaddyBuilds/caddy-cloudflare](https://github.com/CaddyBuilds/caddy-cloudflare). This is my attempt in building my own image.

To test whether the Caddy reverse proxy works, it serves `phpinfo()` output from an Apache PHP container. In my case, this was helpful in determining what environment Apache PHP picks up from the reverse proxy.

Start by creating `.env` from the provided `example.env` but with your own values. The Cloudflare API token permissions needed for a custom token are:

- Zone:Zone:Read
- Zone:DNS:Edit

To build run:

```
docker compose build
docker builder prune # optional
docker compose up
```

And most of all - Enjoy!
