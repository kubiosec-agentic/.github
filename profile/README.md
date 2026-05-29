# kubiosec-agentic

Training material for **building, securing, and hacking agentic AI systems** — from the low-level internals of agent frameworks to the identity and authorization that holds it all together.

## 🚀 Flagship course

[**agentic-labs**](https://github.com/kubiosec-agentic/agentic-labs) — *Building, Securing and Hacking Agentic Systems.* A hands-on, SSH-accessible lab course that goes beyond the hype into the foundations of agentic AI: the OpenAI Chat Completions / Responses APIs and Agents SDK, building and chaining agents with LangChain and custom tools, MCP servers and the MCP Inspector, debugging agents with mitmproxy and tracing, and a set of security pitfalls and hacking challenges. For DevOps engineers, ethical hackers, network specialists, pen-testers, and developers. **#HACKTOLEARN**

## 🔑 Identity & authorization deep-dive track

A focused companion track on how agents and workloads actually authenticate and get authorized — the part that breaks most often in practice. Start with the guide, then drop into the runnable labs:

| | Repo | What it is |
|---|---|---|
| 📖 **Read first** | [**oauth-deepdive**](https://github.com/kubiosec-agentic/oauth-deepdive) | A protocol-level guide to OAuth 2.0/2.1, OIDC, tokens, workload & agent identity, and the MCP authorization profile. The conceptual backbone for the labs below. |
| 🔐 **Tokens** | [**JWT_tooling**](https://github.com/kubiosec-agentic/JWT_tooling) | Sign and verify RS256 JWTs with OpenSSL, publish a JWKS, and protect a FastMCP server as an OAuth 2.1 resource server. Secure-by-default validators with an opt-in attack-demo flag for JKU injection. |
| 🪪 **Microsoft Entra** | [**entra-agent-id-labs**](https://github.com/kubiosec-agentic/entra-agent-id-labs) | Nine labs wiring an AI agent to a protected resource on Microsoft Entra: from a plain client-credentials app registration up to a real Entra Agent ID blueprint, on-behalf-of-a-user, governance, and a zero-credential sidecar. |
| 🛰️ **AWS** | [**aws-sts-attribution**](https://github.com/kubiosec-agentic/aws-sts-attribution) | Near-real-time detection and **attribution** of AWS STS role-assumption events — GitHub Actions OIDC and MCP-gateway sessions — so every federated call traces back to a repo/branch/workflow or a specific human + tool. The audit layer for workload identity. |

```
                 oauth-deepdive  (the concepts)
                        |
   +--------------------+----------------------+
   v                    v                      v
JWT_tooling      entra-agent-id-labs    aws-sts-attribution
(JWT / JWKS       (Entra Agent ID,       (federated identity ->
 / MCP RS)         OBO, governance)       STS, then attribution)
```

The guide explains *how* a token is obtained and validated; the labs let you **do it** — issue one, protect a server with it, federate a workload identity, and then see the resulting calls attributed in an audit trail.

## Notes

- Much of this is **training/reference material**, not production code — dev-only secret paths are flagged as anti-patterns and should be replaced with federated credentials before any real use.
- The Entra labs target **preview** surface; verify against your own tenant.
