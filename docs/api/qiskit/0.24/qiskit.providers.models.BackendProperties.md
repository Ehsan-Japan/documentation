<span id="qiskit-providers-models-backendproperties" />

# qiskit.providers.models.BackendProperties

<span id="undefined" />

`BackendProperties(backend_name, backend_version, last_update_date, qubits, gates, general, **kwargs)`

Class representing backend properties

This holds backend properties measured by the provider. All properties which are provided optionally. These properties may describe qubits, gates, or other general propeties of the backend.

Initialize a BackendProperties instance.

**Parameters**

*   **backend\_name** (*str*) – Backend name.
*   **backend\_version** (*str*) – Backend version in the form X.Y.Z.
*   **last\_update\_date** (*datetime or str*) – Last date/time that a property was updated. If specified as a `str`, it must be in ISO format.
*   **qubits** (*list*) – System qubit parameters as a list of lists of `Nduv` objects
*   **gates** (*list*) – System gate parameters as a list of `Gate` objects
*   **general** (*list*) – General parameters as a list of `Nduv` objects
*   **kwargs** – optional additional fields

<span id="undefined" />

`__init__(backend_name, backend_version, last_update_date, qubits, gates, general, **kwargs)`

Initialize a BackendProperties instance.

**Parameters**

*   **backend\_name** (*str*) – Backend name.
*   **backend\_version** (*str*) – Backend version in the form X.Y.Z.
*   **last\_update\_date** (*datetime or str*) – Last date/time that a property was updated. If specified as a `str`, it must be in ISO format.
*   **qubits** (*list*) – System qubit parameters as a list of lists of `Nduv` objects
*   **gates** (*list*) – System gate parameters as a list of `Gate` objects
*   **general** (*list*) – General parameters as a list of `Nduv` objects
*   **kwargs** – optional additional fields

## Methods

|                                                                                                                                                                          |                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| [`__init__`](#qiskit.providers.models.BackendProperties.__init__ "qiskit.providers.models.BackendProperties.__init__")(backend\_name, backend\_version, …)               | Initialize a BackendProperties instance.                            |
| [`faulty_gates`](#qiskit.providers.models.BackendProperties.faulty_gates "qiskit.providers.models.BackendProperties.faulty_gates")()                                     | Return a list of faulty gates.                                      |
| [`faulty_qubits`](#qiskit.providers.models.BackendProperties.faulty_qubits "qiskit.providers.models.BackendProperties.faulty_qubits")()                                  | Return a list of faulty qubits.                                     |
| [`frequency`](#qiskit.providers.models.BackendProperties.frequency "qiskit.providers.models.BackendProperties.frequency")(qubit)                                         | Return the frequency of the given qubit.                            |
| [`from_dict`](#qiskit.providers.models.BackendProperties.from_dict "qiskit.providers.models.BackendProperties.from_dict")(data)                                          | Create a new Gate object from a dictionary.                         |
| [`gate_error`](#qiskit.providers.models.BackendProperties.gate_error "qiskit.providers.models.BackendProperties.gate_error")(gate, qubits)                               | Return gate error estimates from backend properties.                |
| [`gate_length`](#qiskit.providers.models.BackendProperties.gate_length "qiskit.providers.models.BackendProperties.gate_length")(gate, qubits)                            | Return the duration of the gate in units of seconds.                |
| [`gate_property`](#qiskit.providers.models.BackendProperties.gate_property "qiskit.providers.models.BackendProperties.gate_property")(gate\[, qubits, name])             | Return the property of the given gate.                              |
| [`is_gate_operational`](#qiskit.providers.models.BackendProperties.is_gate_operational "qiskit.providers.models.BackendProperties.is_gate_operational")(gate\[, qubits]) | Return the operational status of the given gate.                    |
| [`is_qubit_operational`](#qiskit.providers.models.BackendProperties.is_qubit_operational "qiskit.providers.models.BackendProperties.is_qubit_operational")(qubit)        | Return the operational status of the given qubit.                   |
| [`qubit_property`](#qiskit.providers.models.BackendProperties.qubit_property "qiskit.providers.models.BackendProperties.qubit_property")(qubit\[, name])                 | Return the property of the given qubit.                             |
| [`readout_error`](#qiskit.providers.models.BackendProperties.readout_error "qiskit.providers.models.BackendProperties.readout_error")(qubit)                             | Return the readout error of the given qubit.                        |
| [`t1`](#qiskit.providers.models.BackendProperties.t1 "qiskit.providers.models.BackendProperties.t1")(qubit)                                                              | Return the T1 time of the given qubit.                              |
| [`t2`](#qiskit.providers.models.BackendProperties.t2 "qiskit.providers.models.BackendProperties.t2")(qubit)                                                              | Return the T2 time of the given qubit.                              |
| [`to_dict`](#qiskit.providers.models.BackendProperties.to_dict "qiskit.providers.models.BackendProperties.to_dict")()                                                    | Return a dictionary format representation of the BackendProperties. |

<span id="undefined" />

`faulty_gates()`

Return a list of faulty gates.

<span id="undefined" />

`faulty_qubits()`

Return a list of faulty qubits.

<span id="undefined" />

`frequency(qubit)`

Return the frequency of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return frequency of.

**Return type**

`float`

**Returns**

Frequency of the given qubit.

<span id="undefined" />

`classmethod from_dict(data)`

Create a new Gate object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the Gate to create. It will be in the same format as output by [`to_dict()`](#qiskit.providers.models.BackendProperties.to_dict "qiskit.providers.models.BackendProperties.to_dict").

**Returns**

**The BackendProperties from the input**

dictionary.

**Return type**

[BackendProperties](#qiskit.providers.models.BackendProperties "qiskit.providers.models.BackendProperties")

<span id="undefined" />

`gate_error(gate, qubits)`

Return gate error estimates from backend properties.

**Parameters**

*   **gate** (`str`) – The gate for which to get the error.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The specific qubits for the gate.

**Return type**

`float`

**Returns**

Gate error of the given gate and qubit(s).

<span id="undefined" />

`gate_length(gate, qubits)`

Return the duration of the gate in units of seconds.

**Parameters**

*   **gate** (`str`) – The gate for which to get the duration.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`]]) – The specific qubits for the gate.

**Return type**

`float`

**Returns**

Gate length of the given gate and qubit(s).

<span id="undefined" />

`gate_property(gate, qubits=None, name=None)`

Return the property of the given gate.

**Parameters**

*   **gate** (`str`) – Name of the gate.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`], `None`]) – The qubit to find the property for.
*   **name** (`Optional`\[`str`]) – Optionally used to specify which gate property to return.

**Return type**

`Tuple`\[`Any`, `datetime`]

**Returns**

Gate property as a tuple of the value and the time it was measured.

**Raises**

[**BackendPropertyError**](qiskit.providers.BackendPropertyError#qiskit.providers.BackendPropertyError "qiskit.providers.BackendPropertyError") – If the property is not found or name is specified but qubit is not.

<span id="undefined" />

`is_gate_operational(gate, qubits=None)`

Return the operational status of the given gate.

**Parameters**

*   **gate** (`str`) – Name of the gate.
*   **qubits** (`Union`\[`int`, `Iterable`\[`int`], `None`]) – The qubit to find the operational status for.

**Returns**

Operational status of the given gate. True if the gate is operational, False otherwise.

**Return type**

bool

<span id="undefined" />

`is_qubit_operational(qubit)`

Return the operational status of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return operational status of.

**Return type**

`bool`

**Returns**

Operational status of the given qubit.

<span id="undefined" />

`qubit_property(qubit, name=None)`

Return the property of the given qubit.

**Parameters**

*   **qubit** (`int`) – The property to look for.
*   **name** (`Optional`\[`str`]) – Optionally used to specify within the hierarchy which property to return.

**Return type**

`Tuple`\[`Any`, `datetime`]

**Returns**

Qubit property as a tuple of the value and the time it was measured.

**Raises**

[**BackendPropertyError**](qiskit.providers.BackendPropertyError#qiskit.providers.BackendPropertyError "qiskit.providers.BackendPropertyError") – If the property is not found.

<span id="undefined" />

`readout_error(qubit)`

Return the readout error of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return the readout error of.

**Return type**

`float`

**Returns**

Readout error of the given qubit,

<span id="undefined" />

`t1(qubit)`

Return the T1 time of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return the T1 time of.

**Return type**

`float`

**Returns**

T1 time of the given qubit.

<span id="undefined" />

`t2(qubit)`

Return the T2 time of the given qubit.

**Parameters**

**qubit** (`int`) – Qubit for which to return the T2 time of.

**Return type**

`float`

**Returns**

T2 time of the given qubit.

<span id="undefined" />

`to_dict()`

Return a dictionary format representation of the BackendProperties.

**Returns**

The dictionary form of the BackendProperties.

**Return type**

dict