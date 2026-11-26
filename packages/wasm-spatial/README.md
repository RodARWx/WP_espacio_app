# @espacio/wasm-spatial — WebAssembly Spatial & QR Engine

- **Owner Role:** Frontend & Architecture
- **Tech Stack:** Rust + wasm-pack (`--target web`) + wasm-opt
- **Workspace Dependencies:** None (Compiled to `.wasm` + TS bindings)
- **Related Jira Tickets:** `GPWP-36, GPWP-41 (ADR-014), GPWP-50, GPWP-52`

## Responsibility
Browser-native `.wasm` module (< 80 KB gzipped) providing client-side 2D `ReferenceSketch` image compression/packing preview and offline QR cryptographic signature verification.
