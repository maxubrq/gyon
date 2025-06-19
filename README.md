# Gyon Browser

> **Security‑first. Joy‑infused. Four letters.**

![build](https://img.shields.io/badge/build-passing-brightgreen)
![license](https://img.shields.io/badge/license-MIT-blue)
![release](https://img.shields.io/badge/release-alpha-orange)

---

## Table of Contents

1. [Vision](#vision)
2. [Feature Matrix](#feature-matrix)
3. [Quick Start](#quick-start)
4. [Magic in Action](#magic-in-action)
5. [Security Architecture](#security-architecture)
6. [Contributing](#contributing)
7. [Roadmap](#roadmap)
8. [License](#license)
9. [Community & Support](#community--support)

---

## Vision

Gyon aims to make the **safest** browser on the planet also the **most delightful** to use.  We eliminate whole classes of memory‑safety and UXSS bugs by building the core in **Rust** and hard‑sandboxing every process—then layer on *playful, friction‑killing interactions* that feel like magic.

---

## Feature Matrix

| Kano Category       | Gyon Highlights                                                                                                                                                                                    |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Must‑Be**         | Standards‑compliant rendering • TLS 1.3‑only • 24 h CVE patch window • Crash‑free >99.9 %                                                                                                          |
| **One‑Dimensional** | <1 s first paint on mid‑range laptop • Memory ≤ Chrome‑10 % • Battery drain ≤ Safari                                                                                                               |
| **Attractive**      | Vertical “Spaces” sidebar • Built‑in tracker blocker with live badge • Offline mini‑game                                                                                                           |
| **Magic**           | **Task Alchemist** (select → *Summarise & Cite*) • **Instant Containers** (auto‑isolated tabs) • **Ghost Login** (password‑less one‑tap auth) • **Cross‑Device Handoff** (exact scroll state sync) |
| **Indifferent**     | Weather widgets • UI skin marketplace                                                                                                                                                              |
| **Reverse**         | Auto‑play previews • Mandatory sign‑in                                                                                                                                                             |

---

## Quick Start

### Pre‑built binaries *(recommended)*

1. Download the latest release for your OS from the [releases page](https://github.com/gyon-browser/gyon/releases).
2. Unzip and run `gyon`.

### Build from source

```bash
# 1 – Clone
$ git clone https://github.com/gyon-browser/gyon.git && cd gyon

# 2 – Install toolchain
$ rustup override set stable
$ rustup target add x86_64-unknown-linux-gnu # or your target triple

# 3 – Build & run
$ cargo run --release
```

> **Note:** UI components use Tauri + Svelte; `npm install` will run automatically during the first build.

---

## Magic in Action

| Feature            | 10‑second demo                 |
| ------------------ | ------------------------------ |
| Task Alchemist     | ![](docs/gifs/alchemist.gif)   |
| Instant Containers | ![](docs/gifs/containers.gif)  |
| Ghost Login        | ![](docs/gifs/ghost-login.gif) |

---

## Security Architecture

* **Memory‑Safe Core** – Rendering engine forked from Servo, rewritten & audited in Rust.
* **Per‑Site Isolation** – One process per eTLD+1; strict `--no-same-site` overrides.
* **OS Sandboxing** – `pledge`/`unveil` (OpenBSD), `seccomp‑bpf`/Landlock (Linux), App Sandbox (macOS).
* **Signed, Reproducible Updates** – Detached Sig + Transparency log; shipped within 24 h of CVE disclosure.
* **Continuous Fuzzing** – AFL++ + libFuzzer coverage in CI; public crash stats dashboard.

See [`docs/security.md`](docs/security.md) for the full threat model and hardening checklist.

---

## Contributing

We love code and ideas—even more when they come with tests.

1. Read the [CONTRIBUTING](CONTRIBUTING.md) guide.
2. Make sure `cargo test && npm test` is clean.
3. Open a Draft PR early for design feedback.
4. For security‑critical fixes, email **[security@gyon.app](mailto:security@gyon.app)** for a coordinated disclosure window.

> **Code Style:** `rustfmt` & `clippy` must pass; UI uses Prettier + eslint.

---

## Roadmap

| Quarter | Milestone                                                                           |
| ------- | ----------------------------------------------------------------------------------- |
| Q3 2025 | MVP: Servo core + basic UI shell, site isolation, auto‑update alpha                 |
| Q4 2025 | Beta: Magic features v1, public bug bounty, macOS notarisation                      |
| Q1 2026 | v1.0: Cross‑device handoff, extension store (WASM‑only), external security audit #2 |

See [`docs/roadmap.md`](docs/roadmap.md) for granular issues.

---

## License

This project is dual‑licensed under **MIT** and **Apache‑2.0**.  You may choose either license.

---

## Community & Support

* **Discord:** `https://discord.gg/gyon`
* **X (Twitter):** `@GyonBrowser`
* **Blog:** [`blog.gyon.app`](https://blog.gyon.app)

Raise issues, request features, or just share screenshots of your favourite "Magic" moment.  Welcome aboard!

---

<sub>© 2025 Gyon Contributors</sub>
