# Neurogas Documentation Server

## Growing Neural Gas (GNG)

A high-performance **Growing Neural Gas** implementation built with a Rust core, exposed through both a native Rust API and a Python wrapper.

---

## Architecture

```mermaid
flowchart TD
    A["Python Application"]
    B["neurogas_py<br/>Python API (wrapper)"]
    C["neurogas — Rust Core<br/>GNG algorithm · network update · learning · topology management"]

    A -->|"import / call"| B
    B -->|"FFI / PyO3 bindings"| C

    style A fill:#4b8be6,color:#fff,stroke:#2c5aa0,stroke-width:2px
    style B fill:#ffb347,color:#1a1a1a,stroke:#c78a2e,stroke-width:2px
    style C fill:#4caf50,color:#fff,stroke:#2e7d32,stroke-width:2px
```

- **`neurogas`** — The Rust crate. Contains the full GNG algorithm (network growth, weight adaptation, topology updates, edge ageing).
- **`neurogas_py`** — A thin Python binding (via PyO3/FFI) that re-exposes the Rust API with Pythonic ergonomics.

> The Python layer adds **zero algorithmic logic**. All computation lives in Rust.


*Last updated: 2026*

