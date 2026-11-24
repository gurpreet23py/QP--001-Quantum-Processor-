# QP-001 Quantum Processor Simulator

A small, local **quantum-circuit simulation** project for learning with Qiskit, Aer, and PennyLane. It does not submit jobs to quantum hardware.

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

Open `QP_001_Quantum_Processor_Simulator.ipynb` and run the cells from top to bottom.

## What the notebook demonstrates

- Bell- and GHZ-state preparation and sampling with Qiskit Aer
- A differentiable PennyLane circuit and gradient
- Depolarizing noise on an 8-qubit GHZ circuit
- A majority-vote decoder for a known computational-basis state under independent bit flips
- A reusable PennyLane simulator class with configurable depolarizing noise

## Notes and limitations

- Simulation is not hardware execution. Cost and memory grow quickly with qubit count.
- The GHZ all-zero/all-one population score is not full state fidelity.
- The repetition-code cell is educational bit-flip majority decoding, not a complete fault-tolerant quantum error-correcting code.
- Noise channels are illustrative and are not calibrated hardware properties.
- Shot-based outputs vary between runs unless a simulator seed is configured.

## Troubleshooting

- Install dependencies into the same Python environment that runs Jupyter.
- Use a supported Python version and a fresh virtual environment if installation fails.
- Reduce shot counts or qubit counts if simulation is slow or memory-heavy.
