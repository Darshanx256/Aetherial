# Aetherial

A deterministic JavaScript benchmark designed to measure raw silicon execution speed and sustained thermal throttling.

## Methodology

Modern browser engines utilize JIT compilation and Dead Code Elimination to bypass repetitive loops. Aetherial circumvents these optimizations to measure pure computational throughput.

* **JIT Evasion:** Forces instruction execution via a mathematically dependent verification checksum.
* **Deterministic Workload:** Uses a seeded Mulberry32 PRNG (0xDEADC0DE) to guarantee identical mathematical workloads across platforms.
* **Cache Isolation:** Zero memory allocation during the core loop restricts execution to CPU registers and L1 cache, eliminating RAM latency variables.

## Usage Modes

* **Sprint (3s):** Measures peak burst performance and maximum clock speed.
* **Marathon (12x):** Executes sequential sprints to track performance degradation under thermal saturation.

## Key Metrics

* **Peak Burst:** Highest recorded throughput (Ops/sec).
* **Sustained Floor:** Lowest recorded throughput during a marathon run.
* **Thermal Stability:** Ratio of Sustained Floor to Peak Burst. High percentages (>90%) indicate effective cooling and minimal thermal throttling.

## Setup

Aetherial is self-contained and requires no dependencies.

1. Clone the repository.
2. Open `index.html` in a modern browser.

*Note: For precise bare-metal testing, execute in a private/incognito window with all browser extensions disabled.*
