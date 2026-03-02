<h1 align="center">Naylence</h1>

<p align="center">
  Secure messaging and runtime fabric for agents — designed around explicit trust boundaries so multi-agent systems can operate safely across networks, runtimes, and trust domains.
</p>

<p align="center">
  <a href="https://naylence.io"><b>Website</b></a> ·
  <a href="https://docs.naylence.io"><b>Docs</b></a> ·
  <a href="https://discord.gg/NVjacrm22X"><b>Discord</b></a> ·
</p>

---

## What is Naylence?

Naylence is a messaging and runtime layer for **agents, tools, and clients** that need:
- secure, authenticated messaging across networks and trust domains
- logical-address routing — callers are decoupled from network topology
- reliability primitives: flow control, delivery guarantees, and load balancing

## Security model (built-in)

- **Trust-domain isolation** — agents declare which trust domain they belong to; the fabric is designed to enforce boundaries at the messaging layer.
- **Tiered security profiles** — four supported profiles selected by name: development (no auth), gated (OAuth 2 / JWT at the edge), overlay (message signing), and strict-overlay (signing + sealed encryption, via the advanced security packages).
- **Overlay → strict-overlay** — overlay signs envelopes with Ed25519 key pairs for provenance and tamper evidence; strict-overlay upgrades to X.509 certificate-based signing, SPIFFE-style workload identities, and end-to-end sealed envelope encryption.
- **Policy-based authorization** — rule-ordered allow/deny policies for routing and addressing permissions (connect, send, receive).
- **Pluggable auth & token layer** — designed for multiple token providers (static, OAuth 2 client-credentials, PKCE, shared-secret) and verifiers (JWKS, shared-secret), composable via the factory/profile system.

## Start here

- **Docs:** https://docs.naylence.io
- **Quickstarts:** (pick one)
  - TypeScript (Node / browser): `npm i @naylence/agent-sdk`
  - Python: `pip install naylence-agent-sdk`
- **Examples:** explore working demos in the [TypeScript examples](https://github.com/naylence/naylence-examples-ts) and [Python examples](https://github.com/naylence/naylence-examples-python) repos.

## Key repositories

### SDKs
- **Python SDK:** [`naylence-agent-sdk-python`](https://github.com/naylence/naylence-agent-sdk-python)
- **TypeScript SDK:** [`naylence-agent-sdk-ts`](https://github.com/naylence/naylence-agent-sdk-ts)

### Advanced security packages
Optional add-ons for high-assurance deployments that need sealed envelope encryption, SPIFFE/X.509 identities, or secure sticky sessions.
- **Advanced security (Python):** [`naylence-advanced-security-python`](https://github.com/naylence/naylence-advanced-security-python)
- **Advanced security (TypeScript):** [`naylence-advanced-security-ts`](https://github.com/naylence/naylence-advanced-security-ts)

### Examples
- **TypeScript examples:** [`naylence-examples-ts`](https://github.com/naylence/naylence-examples-ts)
- **Python examples:** [`naylence-examples-python`](https://github.com/naylence/naylence-examples-python)

## Getting help

- Questions: Join our Discord server at https://discord.gg/NVjacrm22X.
- Bugs: Issues in the relevant repo (include logs + minimal repro)

## Contributing

PRs welcome. If you’re not sure where to start, open a discussion with what you’re trying to build and your target environment (browser, Node, Python, k8s, etc).
