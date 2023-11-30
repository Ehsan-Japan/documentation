<span id="qiskit-qobj-pulseqobj" />

# qiskit.qobj.PulseQobj

<span id="undefined" />

`PulseQobj(qobj_id, config, experiments, header=None)`

A Pulse Qobj.

Instatiate a new Pulse Qobj Object.

Each Pulse Qobj object is used to represent a single payload that will be passed to a Qiskit provider. It mirrors the Qobj the published [Qobj specification](https://arxiv.org/abs/1809.03452) for Pulse experiments.

**Parameters**

*   **qobj\_id** (*str*) – An identifier for the qobj
*   **config** ([*PulseQobjConfig*](qiskit.qobj.PulseQobjConfig#qiskit.qobj.PulseQobjConfig "qiskit.qobj.PulseQobjConfig")) – A config for the entire run
*   **header** ([*QobjHeader*](qiskit.qobj.QobjHeader#qiskit.qobj.QobjHeader "qiskit.qobj.QobjHeader")) – A header for the entire run
*   **experiments** (*list*) – A list of lists of [`PulseQobjExperiment`](qiskit.qobj.PulseQobjExperiment#qiskit.qobj.PulseQobjExperiment "qiskit.qobj.PulseQobjExperiment") objects representing an experiment

<span id="undefined" />

`__init__(qobj_id, config, experiments, header=None)`

Instatiate a new Pulse Qobj Object.

Each Pulse Qobj object is used to represent a single payload that will be passed to a Qiskit provider. It mirrors the Qobj the published [Qobj specification](https://arxiv.org/abs/1809.03452) for Pulse experiments.

**Parameters**

*   **qobj\_id** (*str*) – An identifier for the qobj
*   **config** ([*PulseQobjConfig*](qiskit.qobj.PulseQobjConfig#qiskit.qobj.PulseQobjConfig "qiskit.qobj.PulseQobjConfig")) – A config for the entire run
*   **header** ([*QobjHeader*](qiskit.qobj.QobjHeader#qiskit.qobj.QobjHeader "qiskit.qobj.QobjHeader")) – A header for the entire run
*   **experiments** (*list*) – A list of lists of [`PulseQobjExperiment`](qiskit.qobj.PulseQobjExperiment#qiskit.qobj.PulseQobjExperiment "qiskit.qobj.PulseQobjExperiment") objects representing an experiment

## Methods

|                                                                                                                          |                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| [`__init__`](#qiskit.qobj.PulseQobj.__init__ "qiskit.qobj.PulseQobj.__init__")(qobj\_id, config, experiments\[, header]) | Instatiate a new Pulse Qobj Object.                          |
| [`from_dict`](#qiskit.qobj.PulseQobj.from_dict "qiskit.qobj.PulseQobj.from_dict")(data)                                  | Create a new PulseQobj object from a dictionary.             |
| [`to_dict`](#qiskit.qobj.PulseQobj.to_dict "qiskit.qobj.PulseQobj.to_dict")(\[validate])                                 | Return a dictionary format representation of the Pulse Qobj. |

<span id="undefined" />

`classmethod from_dict(data)`

Create a new PulseQobj object from a dictionary.

**Parameters**

**data** (*dict*) – A dictionary representing the PulseQobj to create. It will be in the same format as output by [`to_dict()`](#qiskit.qobj.PulseQobj.to_dict "qiskit.qobj.PulseQobj.to_dict").

**Returns**

The PulseQobj from the input dictionary.

**Return type**

[PulseQobj](#qiskit.qobj.PulseQobj "qiskit.qobj.PulseQobj")

<span id="undefined" />

`to_dict(validate=False)`

Return a dictionary format representation of the Pulse Qobj.

Note this dict is not in the json wire format expected by IBMQ and qobj specification because complex numbers are still of type complex. Also this may contain native numpy arrays. When serializing this output for use with IBMQ you can leverage a json encoder that converts these as expected. For example:

```python
import json
import numpy

class QobjEncoder(json.JSONEncoder):
    def default(self, obj):
        if isinstance(obj, numpy.ndarray):
            return obj.tolist()
        if isinstance(obj, complex):
            return (obj.real, obj.imag)
        return json.JSONEncoder.default(self, obj)

json.dumps(qobj.to_dict(), cls=QobjEncoder)
```

**Parameters**

**validate** (*bool*) – When set to true validate the output dictionary against the jsonschema for qobj spec.

**Returns**

A dictionary representation of the PulseQobj object

**Return type**

dict