# QP-001 Quantum Processor Simulator

A small, local **classical quantum-circuit simulation** project for learning with Qiskit, Aer, and PennyLane. It does not submit jobs to quantum hardware.

## Quick start

Use Python 3.10–3.12 and a virtual environment:

```bash
python -m venv .venv
# Linux/macOS
source .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
jupyter lab
```

Open `QP_001_Quantum_Processor_Simulator.ipynb` and run the cells from top to bottom. In Google Colab, upload the notebook and run its first setup cell; it installs the notebook dependencies into the active kernel.

## What the notebook demonstrates

- Bell- and GHZ-state preparation and sampling with Qiskit Aer
- A differentiable PennyLane circuit and gradient
- Depolarizing noise on an 8-qubit GHZ circuit
- A majority-vote decoder for a known computational-basis state under independent bit flips
- A reusable PennyLane simulator class with configurable depolarizing noise

## Notes and limitations

- Simulation is not hardware execution. Cost and memory use grow quickly with qubit count; noisy density-matrix simulation can be especially expensive.
- The GHZ all-zero/all-one population score is not a full state-fidelity measurement because it does not verify relative phase.
- The repetition-code cell is an educational bit-flip demonstration, not a complete fault-tolerant quantum error-correcting code. It does not model syndrome extraction or phase-error correction.
- Noise channels are illustrative and are not calibrated hardware properties.
- Shot-based outputs vary between runs unless a simulator seed is explicitly configured.

## Troubleshooting

- Install dependencies into the same Python environment that runs Jupyter.
- If installation fails, use a supported Python version and a fresh virtual environment.
- Reduce shot counts or qubit counts if simulation is slow or memory-heavy.
