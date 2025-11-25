Caddy reverse-proxy for this project

Files:
- Caddyfile: reverse proxy rules for `porto` (localhost:3000) and `server-monitoring` (localhost:8081).

How to run:

1. Build and run with Docker Compose:

```
# from project root
docker compose up --build
```

2. Replace `example.com` in `caddy/Caddyfile` with your real domain if you want TLS via Let's Encrypt.
3. To use your own certs, place `Origin-Certificate.pem` and `Private-Key.pem` in `cert/` (already mounted by compose) and leave the `tls` directive in the `Caddyfile`.

Notes:
- Frontend dev server runs on port 3000 (craco default). The compose maps the same port so you can reach it directly at http://localhost:3000.
- The monitoring websocket service listens on port 8081.
