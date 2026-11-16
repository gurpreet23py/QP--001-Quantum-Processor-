# QP-001 Quantum Processor Simulator

A small, reproducible **classical quantum-circuit simulation** project using Qiskit and Aer. It is designed for learning and experiments on a laptop, Colab, or a supported Python environment; it is not a physical quantum processor.

## Features

- Bell- and GHZ-state circuit sampling
- Configurable single-qubit, two-qubit, and readout noise
- A seeded Aer simulation for repeatable runs
- A three-qubit bit-flip repetition-code demonstration with majority decoding
- Notebook smoke tests and input validation

## Quick start

Use a fresh virtual environment where possible:

```bash
python -m venv .venv
# Linux/macOS
source .venv/bin/activate
# Windows PowerShell
# .venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Open `QP_001_Quantum_Processor_Simulator.ipynb` in Jupyter or upload it to Google Colab, then run cells from top to bottom. In Colab, upload `requirements.txt` too and install with `!python -m pip install -r requirements.txt` if needed. The notebook intentionally avoids automatic installs so it does not unexpectedly alter the host environment.

## Resource guidance

Simulation is not hardware execution. State-vector and density-matrix costs grow exponentially with qubit count, and noisy density-matrix simulations can become expensive even sooner. Start with 2–8 qubits and a modest number of shots; reduce shots/qubits on limited machines. The notebook rejects sizes outside 1–20 as a guardrail, but memory available on a specific machine is the actual limit.

## Interpretation and limitations

- GHZ computational-basis population score counts outcomes equal to all-zero or all-one. It is **not** a full state-fidelity measurement, since it does not verify relative phase.
- The repetition-code example corrects independent bit flips for a known computational-basis state. It is not a complete quantum error-correcting code and does not correct phase errors or protect arbitrary unknown quantum states.
- Noise channels are illustrative models and should not be treated as calibrated hardware properties.
- The notebook does not submit jobs to a real quantum processor. Hardware execution needs provider access and separate backend/transpilation setup.

## Troubleshooting

- Use a fresh environment and a Python version supported by the installed Qiskit/Aer releases if binary installation fails.
- If a plotting dependency is unavailable, the notebook still runs the simulator and tests; plots are optional.
- If a run is slow or memory-heavy, lower shot counts and qubit count.
- Reinstall packages in the active environment with `python -m pip`, not a different `pip` executable.
