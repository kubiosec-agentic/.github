# kubiosec-agentic

Practical, hands-on material on **identity and authorization for AI agents and modern workloads** — from the OAuth/OIDC fundamentals through to running, securing, and *auditing* real token flows on MCP, Microsoft Entra, and AWS.

It reads as one learning track: start with the concepts, then drop into runnable labs.

## The learning track

| | Repo | What it is |
|---|---|---|
| 📖 **Read first** | [**oauth-deepdive**](https://github.com/kubiosec-agentic/oauth-deepdive) | A protocol-level guide to OAuth 2.0/2.1, OIDC, tokens, workload & agent identity, and the MCP authorization profile. The conceptual backbone for everything below. |
| 🔐 **Lab — tokens** | [**JWT_tooling**](https://github.com/kubiosec-agentic/JWT_tooling) | Sign and verify RS256 JWTs with OpenSSL, publish a JWKS, and protect a FastMCP server as an OAuth 2.1 resource server. Secure-by-default validators with an opt-in attack-demo flag for JKU injection. |
| 🪪 **Lab — Entra** | [**entra-agent-id-labs**](https://github.com/kubiosec-agentic/entra-agent-id-labs) | Nine labs wiring an AI agent to a protected resource on Microsoft Entra: from a plain client-credentials app registration up to a real Entra Agent ID blueprint, on-behalf-of-a-user, governance, and a zero-credential sidecar. |
| 🛰️ **Lab — AWS** | [**aws-sts-attribution**](https://github.com/kubiosec-agentic/aws-sts-attribution) | Near-real-time detection and **attribution** of AWS STS role-assumption events — GitHub Actions OIDC and MCP-gateway sessions — so every federated call can be traced back to a repo/branch/workflow or a specific human + tool. The audit layer for workload identity. |

## How they connect

```
            oauth-deepdive  (the concepts)
                   |
   +---------------+---------------------+
   v               v                     v
JWT_tooling   entra-agent-id-labs   aws-sts-attribution
(JWT / JWKS    (Entra Agent ID,      (federated identity ->
 / MCP RS)      OBO, governance)      STS, then attribution)
```

The guide explains *how* a token is obtained and validated; the labs let you
**do it** — issue one, protect a server with it, federate a workload identity,
and then see the resulting calls attributed in an audit trail.

## Notes

- Several labs are **training/reference material**, not production code — dev-only secret paths are flagged as anti-patterns and should be replaced with federated credentials before any real use.
- The Entra labs target **preview** surface; verify against your own tenant.
