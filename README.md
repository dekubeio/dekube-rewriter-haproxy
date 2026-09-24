# dekube-rewriter-haproxy

HAProxy ingress annotation rewriter for [dekube](https://dekube.io) — translates `haproxy.org/*` Ingress annotations into reverse proxy entries. Also serves as the default fallback rewriter for unclassified Ingress resources. It runs last (`priority = 1100`), so when the nginx or traefik rewriter is present, it claims its own annotated classless Ingresses first.

**The Herald** — one of the Eight Monks, the founding extensions of the helmfile2compose distribution.

> Heresy level: 2/10 — announces what others have decreed, translates annotations into action.

## Type

`IngressRewriter`

## Supported annotations

- `haproxy.org/server-ssl` — backend HTTPS
- `haproxy.org/server-ca` — CA certificate for backend verification
- `haproxy.org/server-sni` — SNI for backend TLS
- `haproxy.org/path-rewrite` — strip prefix

## Limitations

- Rules without `host` and `spec.defaultBackend` (catch-all for any host) are skipped with a warning — reverse proxy entries are keyed by hostname.

## Install

Via [dekube-manager](https://github.com/dekubeio/dekube-manager):

```sh
python3 dekube-manager.py haproxy
```

Or listed in `distribution.json` — installed automatically when building a distribution.
