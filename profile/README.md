<p align="center">
  <img src="https://github.com/SlaukoKit.png?size=256" alt="SlaukoKit" width="180" />
</p>

<h1 align="center">SlaukoKit</h1>

<p align="center">Self-hosted systems for Linux, built to fail closed.</p>

<p align="center">
  <a href="https://slaukokit.dev">Website</a> ·
  <a href="https://slaukokit.dev/#security">Security model</a> ·
  <a href="https://slaukokit.dev/#notes">Engineering notes</a>
</p>

SlaukoKit builds private, self-hosted software for Linux and writes up how it is
secured. We publish our architecture, threat model, known limits and lessons
from real runs, so you can judge the design rather than take it on trust.

## What we build

| Project | What it is |
| --- | --- |
| **Network** | A private workspace that connects an AI agent across several computers. A Rust hub plus a Rust connector on each machine, and no inbound port on any of them. |
| **AppShell** | The shared interface layer and Tauri window shell behind our desktop and web apps. |
| **Infra** | Shared release tooling for signed update channels, CI runner setup and serialized host operations. |

## How we engineer

- **Devices dial out.** No inbound ports or arbitrary tunnels on workstations.
- **Fail closed.** A bad address, port or config stops startup instead of falling back.
- **One source of truth for the wire.** Protocol types are written once in Rust; the schemas and TypeScript are generated, and CI rejects any drift.
- **Never retry blindly.** IDs are reserved before the first send, and every event is journaled.
- **Signed and immutable releases.** Updates are verified before they're activated, and published site releases are never overwritten.
- **Proof against real processes.** End-to-end acceptance tests start the actual binaries.

## Status

Our repositories are private while the work is in active development. The
security model and engineering notes at [slaukokit.dev](https://slaukokit.dev)
are kept in step with the code, including what isn't verified yet.
