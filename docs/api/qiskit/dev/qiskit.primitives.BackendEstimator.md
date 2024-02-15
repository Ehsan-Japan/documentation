---
title: BackendEstimator
description: API reference for qiskit.primitives.BackendEstimator
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.primitives.BackendEstimator
---

# BackendEstimator

<span id="qiskit.primitives.BackendEstimator" />

`qiskit.primitives.BackendEstimator(backend, options=None, abelian_grouping=True, bound_pass_manager=None, skip_transpilation=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/primitives/backend_estimator.py "view source code")

Bases: `BaseEstimatorV1`\[`PrimitiveJob`\[[`EstimatorResult`](qiskit.primitives.EstimatorResult "qiskit.primitives.base.estimator_result.EstimatorResult")]]

Evaluates expectation value using Pauli rotation gates.

The [`BackendEstimator`](#qiskit.primitives.BackendEstimator "qiskit.primitives.BackendEstimator") class is a generic implementation of the `BaseEstimator` interface that is used to wrap a [`BackendV2`](qiskit.providers.BackendV2 "qiskit.providers.BackendV2") (or [`BackendV1`](qiskit.providers.BackendV1 "qiskit.providers.BackendV1")) object in the `BaseEstimator` API. It facilitates using backends that do not provide a native `BaseEstimator` implementation in places that work with `BaseEstimator`. However, if you’re using a provider that has a native implementation of `BaseEstimator`, it is a better choice to leverage that native implementation as it will likely include additional optimizations and be a more efficient implementation. The generic nature of this class precludes doing any provider- or backend-specific optimizations.

Initialize a new BackendEstimator instance

**Parameters**

*   **backend** – Required: the backend to run the primitive on
*   **options** – Default options.
*   **abelian\_grouping** – Whether the observable should be grouped into commuting
*   **bound\_pass\_manager** – An optional pass manager to run after parameter binding.
*   **skip\_transpilation** – If this is set to True the internal compilation of the input circuits is skipped and the circuit objects will be directly executed when this object is called.

## Attributes

<span id="qiskit.primitives.BackendEstimator.backend" />

### backend

Returns: The backend which this estimator object based on

<span id="qiskit.primitives.BackendEstimator.options" />

### options

Return options values for the estimator.

**Returns**

options

<span id="qiskit.primitives.BackendEstimator.preprocessed_circuits" />

### preprocessed\_circuits

Transpiled quantum circuits produced by preprocessing :returns: List of the transpiled quantum circuit

<span id="qiskit.primitives.BackendEstimator.transpile_options" />

### transpile\_options

Return the transpiler options for transpiling the circuits.

<span id="qiskit.primitives.BackendEstimator.transpiled_circuits" />

### transpiled\_circuits

Transpiled quantum circuits. :returns: List of the transpiled quantum circuit

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – if the instance has been closed.

## Methods

### run

<span id="qiskit.primitives.BackendEstimator.run" />

`run(circuits, observables, parameter_values=None, **run_options)`

Run the job of the estimation of expectation value(s).

`circuits`, `observables`, and `parameter_values` should have the same length. The i-th element of the result is the expectation of observable

```python
obs = observables[i]
```

for the state prepared by

```python
circ = circuits[i]
```

with bound parameters

```python
values = parameter_values[i].
```

**Parameters**

*   **circuits** (*Sequence\[*[*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")*] |* [*QuantumCircuit*](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit")) – one or more circuit objects.
*   **observables** (*Sequence\[BaseOperator |* [*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*] | BaseOperator |* [*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – one or more observable objects. Several formats are allowed; importantly, `str` should follow the string representation format for [`Pauli`](qiskit.quantum_info.Pauli "qiskit.quantum_info.Pauli") objects.
*   **parameter\_values** (*Sequence\[Sequence\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]] | Sequence\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*] |* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)") *| None*) – concrete parameters to be bound.
*   **run\_options** – runtime options used for circuit execution.

**Returns**

The job object of EstimatorResult.

**Raises**

*   [**TypeError**](https://docs.python.org/3/library/exceptions.html#TypeError "(in Python v3.12)") – Invalid argument type given.
*   [**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – Invalid argument values given.

**Return type**

T

### set\_options

<span id="qiskit.primitives.BackendEstimator.set_options" />

`set_options(**fields)`

Set options values for the estimator.

**Parameters**

**\*\*fields** – The fields to update the options

### set\_transpile\_options

<span id="qiskit.primitives.BackendEstimator.set_transpile_options" />

`set_transpile_options(**fields)`

Set the transpiler options for transpiler. :param \*\*fields: The fields to update the options
