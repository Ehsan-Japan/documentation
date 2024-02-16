---
title: PhaseEstimation
description: API reference for qiskit.algorithms.PhaseEstimation
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.PhaseEstimation
---

# PhaseEstimation

<span id="qiskit.algorithms.PhaseEstimation" />

`qiskit.algorithms.PhaseEstimation(num_evaluation_qubits, quantum_instance=None, sampler=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.46/qiskit/algorithms/phase_estimators/phase_estimation.py "view source code")

Bases: `PhaseEstimator`

Run the Quantum Phase Estimation (QPE) algorithm.

This runs QPE with a multi-qubit register for reading the phases \[1] of input states.

The algorithm takes as input a unitary $U$ and a state $|\psi\rangle$, which may be written

$$
|\psi\rangle = \sum_j c_j |\phi_j\rangle,
$$

where $|\phi_j\rangle$ are eigenstates of $U$. We prepare the quantum register in the state $|\psi\rangle$ then apply $U$ leaving the register in the state

$$
U|\psi\rangle = \sum_j \exp(i \phi_j) c_j |\phi_j\rangle.
$$

In the ideal case, one then measures the phase $\phi_j$ with probability $|c_j|^2$. In practice, many (or all) of the bit strings may be measured due to noise and the possibility that $\phi_j$ may not be representable exactly by the output register. In the latter case the probability for each eigenphase will be spread across bitstrings, with amplitudes that decrease with distance from the bitstring most closely approximating the eigenphase.

The main input to the constructor is the number of qubits in the phase-reading register. For phase estimation, there are two methods:

**first. estimate, which takes a state preparation circuit to prepare an input state, and**

a unitary that will act on the input state. In this case, an instance of `qiskit.circuit.PhaseEstimation`, a QPE circuit, containing the state preparation and input unitary will be constructed.

**second. estimate\_from\_pe\_circuit, which takes a quantum-phase-estimation circuit in which**

the unitary and state preparation are already embedded.

In both estimation methods, the QPE circuit is run on a backend and the frequencies or counts of the phases represented by bitstrings are recorded. The results are returned as an instance of `PhaseEstimationResult`.

**Reference:**

**\[1]: Michael A. Nielsen and Isaac L. Chuang. 2011.**

Quantum Computation and Quantum Information: 10th Anniversary Edition (10th ed.). Cambridge University Press, New York, NY, USA.

<Admonition title="Deprecated since version 0.24.0" type="danger">
  `qiskit.algorithms.phase_estimators.phase_estimation.PhaseEstimation.__init__()`’s argument `quantum_instance` is deprecated as of qiskit-terra 0.24.0. It will be removed no earlier than 3 months after the release date. Instead, use the `sampler` argument. See [https://qisk.it/algo\_migration](https://qisk.it/algo_migration) for a migration guide.
</Admonition>

**Parameters**

*   **num\_evaluation\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The number of qubits used in estimating the phase. The phase will be estimated as a binary string with this many bits.
*   **quantum\_instance** ([*QuantumInstance*](qiskit.utils.QuantumInstance "qiskit.utils.QuantumInstance")  *|*[*Backend*](qiskit.providers.Backend "qiskit.providers.Backend") *| None*) – Deprecated: The quantum instance on which the circuit will be run.
*   **sampler** ([*BaseSampler*](qiskit.primitives.BaseSampler "qiskit.primitives.BaseSampler") *| None*) – The sampler primitive on which the circuit will be sampled.

**Raises**

[**AlgorithmError**](algorithms#qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – If neither sampler nor quantum instance is provided.

## Methods

### construct\_circuit

<span id="qiskit.algorithms.PhaseEstimation.construct_circuit" />

`construct_circuit(unitary, state_preparation=None)`

Return the circuit to be executed to estimate phases.

This circuit includes as sub-circuits the core phase estimation circuit, with the addition of the state-preparation circuit and possibly measurement instructions.

**Return type**

[QuantumCircuit](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")

### estimate

<span id="qiskit.algorithms.PhaseEstimation.estimate" />

`estimate(unitary, state_preparation=None)`

Build a phase estimation circuit and run the corresponding algorithm.

**Parameters**

*   **unitary** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – The circuit representing the unitary operator whose eigenvalues (via phase) will be measured.
*   **state\_preparation** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") *| None*) – The circuit that prepares the state whose eigenphase will be measured. If this parameter is omitted, no preparation circuit will be run and input state will be the all-zero state in the computational basis.

**Returns**

An instance of qiskit.algorithms.phase\_estimator\_result.PhaseEstimationResult.

**Return type**

[PhaseEstimationResult](qiskit.algorithms.PhaseEstimationResult "qiskit.algorithms.PhaseEstimationResult")

### estimate\_from\_pe\_circuit

<span id="qiskit.algorithms.PhaseEstimation.estimate_from_pe_circuit" />

`estimate_from_pe_circuit(pe_circuit, num_unitary_qubits)`

Run the phase estimation algorithm on a phase estimation circuit

**Parameters**

*   **pe\_circuit** ([*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")) – The phase estimation circuit.
*   **num\_unitary\_qubits** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Must agree with the number of qubits in the unitary in pe\_circuit.

**Returns**

An instance of qiskit.algorithms.phase\_estimator\_result.PhaseEstimationResult.

**Raises**

[**AlgorithmError**](algorithms#qiskit.algorithms.AlgorithmError "qiskit.algorithms.AlgorithmError") – Primitive job failed.

**Return type**

[*PhaseEstimationResult*](qiskit.algorithms.PhaseEstimationResult "qiskit.algorithms.phase_estimators.phase_estimation_result.PhaseEstimationResult")
