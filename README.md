# h2c-rewriter-haproxy

HAProxy ingress annotation rewriter for [helmfile2compose](https://github.com/helmfile2compose/helmfile2compose) — translates `haproxy.org/*` Ingress annotations into reverse proxy entries. Also serves as the default fallback rewriter for unclassified Ingress resources.

**The Herald** — one of the Seven Bishops, the founding extensions of the helmfile2compose distribution.

## Type

`IngressRewriter`

## Supported annotations

- `haproxy.org/server-ssl` — backend HTTPS
- `haproxy.org/server-ca` — CA certificate for backend verification
- `haproxy.org/server-sni` — SNI for backend TLS
- `haproxy.org/path-rewrite` — strip prefix

## Note

This is a **build-time only** extension, designed to be concatenated by `build-distribution.py` into a single-file distribution. It uses internal core imports that are resolved at build time. It is **not** designed for runtime loading via `--extensions-dir`.

## Install

Listed in `distribution.json` — installed automatically when building a distribution via `h2c-manager`.
