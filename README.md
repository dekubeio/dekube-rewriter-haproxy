# dekube-rewriter-haproxy

HAProxy ingress annotation rewriter for [dekube](https://dekube.io) — translates `haproxy.org/*` Ingress annotations into reverse proxy entries. Also serves as the default fallback rewriter for unclassified Ingress resources.

**The Herald** — one of the Eight Monks, the founding extensions of the helmfile2compose distribution.

> Heresy level: 2/10 — announces what others have decreed, translates annotations into action.

## Type

`IngressRewriter`

## Supported annotations

- `haproxy.org/server-ssl` — backend HTTPS
- `haproxy.org/server-ca` — CA certificate for backend verification
- `haproxy.org/server-sni` — SNI for backend TLS
- `haproxy.org/path-rewrite` — strip prefix

## Install

Via [dekube-manager](https://github.com/dekubeio/dekube-manager):

```sh
python3 dekube-manager.py haproxy
```

Or listed in `distribution.json` — installed automatically when building a distribution.
