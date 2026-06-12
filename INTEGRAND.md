# Onyx @ integrand.ai

This is the integrand.ai fork of [onyx-dot-app/onyx](https://github.com/onyx-dot-app/onyx) — the self-hosted chat + enterprise RAG client we deploy for clients under our forward-deployed model.

## Fork policy

**This fork stays minimal.** Upstream Onyx moves fast; we rebase regularly. All heavy customization lives in [integrand-gateway](https://github.com/abel30567/integrand-gateway), not here.

What this fork carries:
- LLM provider config pointed at the integrand-gateway proxy (one base URL — Headroom compression, guardrails, and telemetry apply transparently)
- integrand.ai branding/theme overlays
- Client-specific connector configs (per-deployment branches, never merged to main)

What this fork must NOT carry:
- Gateway logic, compression, or guardrail code (belongs in integrand-gateway)
- Customer data, brains, or prompts of any kind (Forkscale principle: only architecture is forked)

## Why Onyx as the client tier

- Enterprise RAG: hybrid search, contextual retrieval, knowledge graphs over client documents
- 40+ knowledge connectors, MCP support, agents, deep research
- Works with any LLM — which is exactly what makes the gateway pattern possible

## Deployment topology

```
Onyx (this fork) → integrand-gateway → model providers
       │                  │
  client's docs      client's SIEM
```

Upstream README: see README.md.

---
© Dattebayo Labs · integrand.ai