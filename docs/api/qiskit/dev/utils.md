---
title: utils
description: API reference for qiskit.utils
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.utils
---

<span id="module-qiskit.utils" />

<span id="qiskit-utils" />

<span id="utilities-qiskit-utils" />

# Utilities

<span id="module-qiskit.utils" />

`qiskit.utils`

### add\_deprecation\_to\_docstring

<span id="qiskit.utils.add_deprecation_to_docstring" />

`qiskit.utils.add_deprecation_to_docstring(func, msg, *, since, pending)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/deprecation.py "view source code")

Dynamically insert the deprecation message into `func`’s docstring.

**Parameters**

*   **func** (*Callable*) – The function to modify.
*   **msg** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The full deprecation message.
*   **since** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – The version the deprecation started at.
*   **pending** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Is the deprecation still pending?

### deprecate\_arg

<span id="qiskit.utils.deprecate_arg" />

`qiskit.utils.deprecate_arg(name, *, since, additional_msg=None, deprecation_description=None, pending=False, package_name='qiskit', new_alias=None, predicate=None, removal_timeline='no earlier than 3 months after the release date')`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/deprecation.py "view source code")

Decorator to indicate an argument has been deprecated in some way.

This decorator may be used multiple times on the same function, once per deprecated argument. It should be placed beneath other decorators like `@staticmethod` and property decorators.

**Parameters**

*   **name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The name of the deprecated argument.
*   **since** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The version the deprecation started at. If the deprecation is pending, set the version to when that started; but later, when switching from pending to deprecated, update since to the new version.
*   **deprecation\_description** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – What is being deprecated? E.g. “Setting my\_func()’s my\_arg argument to None.” If not set, will default to “\{func\_name}’s argument \{name}”.
*   **additional\_msg** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – Put here any additional information, such as what to use instead (if new\_alias is not set). For example, “Instead, use the argument new\_arg, which is similar but does not impact the circuit’s setup.”
*   **pending** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Set to True if the deprecation is still pending.
*   **package\_name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The PyPI package name, e.g. “qiskit-nature”.
*   **new\_alias** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – If the arg has simply been renamed, set this to the new name. The decorator will dynamically update the kwargs so that when the user sets the old arg, it will be passed in as the new\_alias arg.
*   **predicate** (*Callable\[\[Any],* [*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")*] | None*) – Only log the runtime warning if the predicate returns True. This is useful to deprecate certain values or types for an argument, e.g. lambda my\_arg: isinstance(my\_arg, dict). Regardless of if a predicate is set, the runtime warning will only log when the user specifies the argument.
*   **removal\_timeline** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – How soon can this deprecation be removed? Expects a value like “no sooner than 6 months after the latest release” or “in release 9.99”.

**Returns**

The decorated callable.

**Return type**

Callable

### deprecate\_arguments

<span id="qiskit.utils.deprecate_arguments" />

`qiskit.utils.deprecate_arguments(kwarg_map, category=<class 'DeprecationWarning'>, *, since=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/deprecation.py "view source code")

Deprecated. Instead, use @deprecate\_arg.

**Parameters**

*   **kwarg\_map** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*,* [*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None]*) – A dictionary of the old argument name to the new name.
*   **category** ([*Type*](circuit_classical#qiskit.circuit.classical.types.Type "qiskit.circuit.classical.types.Type")*\[*[*Warning*](https://docs.python.org/3/library/exceptions.html#Warning "(in Python v3.12)")*]*) – Usually either DeprecationWarning or PendingDeprecationWarning.
*   **since** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – The version the deprecation started at. Only Optional for backwards compatibility - this should always be set. If the deprecation is pending, set the version to when that started; but later, when switching from pending to deprecated, update since to the new version.

**Returns**

The decorated callable.

**Return type**

Callable

### deprecate\_func

<span id="qiskit.utils.deprecate_func" />

`qiskit.utils.deprecate_func(*, since, additional_msg=None, pending=False, package_name='qiskit', removal_timeline='no earlier than 3 months after the release date', is_property=False)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/deprecation.py "view source code")

Decorator to indicate a function has been deprecated.

It should be placed beneath other decorators like @staticmethod and property decorators.

When deprecating a class, set this decorator on its \_\_init\_\_ function.

**Parameters**

*   **since** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The version the deprecation started at. If the deprecation is pending, set the version to when that started; but later, when switching from pending to deprecated, update `since` to the new version.
*   **additional\_msg** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – Put here any additional information, such as what to use instead. For example, “Instead, use the function `new_func` from the module `<my_module>.<my_submodule>`, which is similar but uses GPU acceleration.”
*   **pending** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – Set to `True` if the deprecation is still pending.
*   **package\_name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – The PyPI package name, e.g. “qiskit-nature”.
*   **removal\_timeline** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – How soon can this deprecation be removed? Expects a value like “no sooner than 6 months after the latest release” or “in release 9.99”.
*   **is\_property** ([*bool*](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")) – If the deprecated function is a @property, set this to True so that the generated message correctly describes it as such. (This isn’t necessary for property setters, as their docstring is ignored by Python.)

**Returns**

The decorated callable.

**Return type**

Callable

### deprecate\_function

<span id="qiskit.utils.deprecate_function" />

`qiskit.utils.deprecate_function(msg, stacklevel=2, category=<class 'DeprecationWarning'>, *, since=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/deprecation.py "view source code")

Deprecated. Instead, use @deprecate\_func.

**Parameters**

*   **msg** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – Warning message to emit.
*   **stacklevel** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – The warning stacklevel to use, defaults to 2.
*   **category** ([*Type*](circuit_classical#qiskit.circuit.classical.types.Type "qiskit.circuit.classical.types.Type")*\[*[*Warning*](https://docs.python.org/3/library/exceptions.html#Warning "(in Python v3.12)")*]*) – Usually either DeprecationWarning or PendingDeprecationWarning.
*   **since** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *| None*) – The version the deprecation started at. Only Optional for backwards compatibility - this should always be set. If the deprecation is pending, set the version to when that started; but later, when switching from pending to deprecated, update since to the new version.

**Returns**

The decorated, deprecated callable.

**Return type**

Callable

### local\_hardware\_info

<span id="qiskit.utils.local_hardware_info" />

`qiskit.utils.local_hardware_info()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/multiprocessing.py "view source code")

Basic hardware information about the local machine.

Gives actual number of CPU’s in the machine, even when hyperthreading is turned on. CPU count defaults to 1 when true count can’t be determined.

**Returns**

The hardware information.

**Return type**

[dict](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")

### is\_main\_process

<span id="qiskit.utils.is_main_process" />

`qiskit.utils.is_main_process()`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/multiprocessing.py "view source code")

Checks whether the current process is the main one

### apply\_prefix

<span id="qiskit.utils.apply_prefix" />

`qiskit.utils.apply_prefix(value, unit)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/units.py "view source code")

Given a SI unit prefix and value, apply the prefix to convert to standard SI unit.

**Parameters**

*   **value** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")  *|*[*ParameterExpression*](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")) – The number to apply prefix to.
*   **unit** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – String prefix.

**Returns**

Converted value.

**Return type**

[float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)") | [ParameterExpression](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")

<Admonition title="Note" type="note">
  This may induce tiny value error due to internal representation of float object. See [https://docs.python.org/3/tutorial/floatingpoint.html](https://docs.python.org/3/tutorial/floatingpoint.html) for details.
</Admonition>

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – If the `units` aren’t recognized.

**Return type**

[float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)") | [ParameterExpression](qiskit.circuit.ParameterExpression "qiskit.circuit.ParameterExpression")

### detach\_prefix

<span id="qiskit.utils.detach_prefix" />

`qiskit.utils.detach_prefix(value, decimal=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/units.py "view source code")

Given a SI unit value, find the most suitable prefix to scale the value.

For example, the `value = 1.3e8` will be converted into a tuple of `(130.0, "M")`, which represents a scaled value and auxiliary unit that may be used to display the value. In above example, that value might be displayed as `130 MHz` (unit is arbitrary here).

**Example**

```python
>>> value, prefix = detach_prefix(1e4)
>>> print(f"{value} {prefix}Hz")
10 kHz
```

**Parameters**

*   **value** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – The number to find prefix.
*   **decimal** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)") *| None*) – Optional. An arbitrary integer number to represent a precision of the value. If specified, it tries to round the mantissa and adjust the prefix to rounded value. For example, 999\_999.91 will become 999.9999 k with `decimal=4`, while 1.0 M with `decimal=3` or less.

**Returns**

A tuple of scaled value and prefix.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")\[[float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)"), [str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")]

<Admonition title="Note" type="note">
  This may induce tiny value error due to internal representation of float object. See [https://docs.python.org/3/tutorial/floatingpoint.html](https://docs.python.org/3/tutorial/floatingpoint.html) for details.
</Admonition>

**Raises**

*   [**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – If the `value` is out of range.
*   [**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – If the `value` is not real number.

**Return type**

[tuple](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")\[[float](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)"), [str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")]

### wrap\_method

<span id="qiskit.utils.wrap_method" />

`qiskit.utils.wrap_method(cls, name, *, before=None, after=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/classtools.py "view source code")

Wrap the functionality the instance- or class method `cls.name` with additional behaviour `before` and `after`.

This mutates `cls`, replacing the attribute `name` with the new functionality. This is useful when creating class decorators. The method is allowed to be defined on any parent class instead.

If either `before` or `after` are given, they should be callables with a compatible signature to the method referred to. They will be called immediately before or after the method as appropriate, and any return value will be ignored.

**Parameters**

*   **cls** ([*Type*](https://docs.python.org/3/library/typing.html#typing.Type "(in Python v3.12)")) – the class to modify.
*   **name** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – the name of the method on the class to wrap.
*   **before** ([*Callable*](https://docs.python.org/3/library/typing.html#typing.Callable "(in Python v3.12)") *| None*) – a callable that should be called before the method that is being wrapped.
*   **after** ([*Callable*](https://docs.python.org/3/library/typing.html#typing.Callable "(in Python v3.12)") *| None*) – a callable that should be called after the method that is being wrapped.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – if the named method is not defined on the class or any parent class.

## Parallel Routines

A helper function for calling a custom function with python [`ProcessPoolExecutor`](https://docs.python.org/3/library/concurrent.futures.html#concurrent.futures.ProcessPoolExecutor "(in Python v3.12)"). Tasks can be executed in parallel using this function.

### parallel\_map

<span id="qiskit.utils.parallel_map" />

`qiskit.utils.parallel_map(task, values, task_args=(), task_kwargs={}, num_processes=1)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/parallel.py "view source code")

Parallel execution of a mapping of values to the function task. This is functionally equivalent to:

```python
result = [task(value, *task_args, **task_kwargs) for value in values]
```

On Windows this function defaults to a serial implementation to avoid the overhead from spawning processes in Windows.

**Parameters**

*   **task** (*func*) – Function that is to be called for each value in `values`.
*   **values** (*array\_like*) – List or array of values for which the `task` function is to be evaluated.
*   **task\_args** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")) – Optional additional arguments to the `task` function.
*   **task\_kwargs** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – Optional additional keyword argument to the `task` function.
*   **num\_processes** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Number of processes to spawn.

**Returns**

**The result list contains the value of**

**`task(value, *task_args, **task_kwargs)` for**

each value in `values`.

**Return type**

result

**Raises**

[**QiskitError**](exceptions#qiskit.exceptions.QiskitError "qiskit.exceptions.QiskitError") – If user interrupts via keyboard.

**Examples**

```python
import time
from qiskit.utils import parallel_map
def func(_):
        time.sleep(0.1)
        return 0
parallel_map(func, list(range(10)));
```

<span id="module-qiskit.utils.optionals" />

<span id="optional-dependency-checkers-qiskit-utils-optionals" />

### Optional Dependency Checkers ([`qiskit.utils.optionals`](#module-qiskit.utils.optionals "qiskit.utils.optionals"))

Qiskit has several features that are enabled only if certain *optional* dependencies are satisfied. This module is a collection of objects that can be used to test if certain functionality is available, and optionally raise [`MissingOptionalLibraryError`](exceptions#qiskit.exceptions.MissingOptionalLibraryError "qiskit.exceptions.MissingOptionalLibraryError") if the functionality is not available.

#### Available Testers

##### Qiskit Components

|                                       |                                                                                                                                                                                     |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **qiskit.utils.optionals.HAS\_AER**   | Qiskit Aer \<[https://qiskit.github.io/qiskit-aer/](https://qiskit.github.io/qiskit-aer/)> provides high-performance simulators for the quantum circuits constructed within Qiskit. |
| **qiskit.utils.optionals.HAS\_IBMQ**  | The `Qiskit IBMQ Provider` is used for accessing IBM Quantum hardware in the IBM cloud.                                                                                             |
| **qiskit.utils.optionals.HAS\_IGNIS** | `Qiskit Ignis` provides tools for quantum hardware verification, noise characterization, and error correction.                                                                      |
| **qiskit.utils.optionals.HAS\_TOQM**  | [Qiskit TOQM](https://github.com/qiskit-toqm/qiskit-toqm) provides transpiler passes for the [Time-optimal Qubit mapping algorithm](https://doi.org/10.1145/3445814.3446706).       |

##### External Python Libraries

|                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **qiskit.utils.optionals.HAS\_CONSTRAINT**    | python-constraint \<[https://github.com/python-constraint/python-constraint>\_\_](https://github.com/python-constraint/python-constraint>__) is a constraint satisfaction problem solver, used in the :class:\`\~.CSPLayout transpiler pass.                                                                                                                                                                                                |
| **qiskit.utils.optionals.HAS\_CPLEX**         | The [IBM CPLEX Optimizer](https://www.ibm.com/analytics/cplex-optimizer) is a high-performance mathematical programming solver for linear, mixed-integer and quadratic programming. This is no longer by Qiskit, but it weas historically and the optional remains for backwards compatibility.                                                                                                                                             |
| **qiskit.utils.optionals.HAS\_CVXPY**         | [CVXPY](https://www.cvxpy.org/) is a Python package for solving convex optimization problems. It is required for calculating diamond norms with [`quantum_info.diamond_norm()`](quantum_info#qiskit.quantum_info.diamond_norm "qiskit.quantum_info.diamond_norm").                                                                                                                                                                          |
| **qiskit.utils.optionals.HAS\_DOCPLEX**       | [IBM Decision Optimization CPLEX Modelling](http://ibmdecisionoptimization.github.io/docplex-doc/) is a library for prescriptive analysis. Like CPLEX, this is no longer by Qiskit, but it weas historically and the optional remains for backwards compatibility.                                                                                                                                                                          |
| **qiskit.utils.optionals.HAS\_FIXTURES**      | The test suite has additional features that are available if the optional [fixtures](https://launchpad.net/python-fixtures) module is installed. This generally also needs [`HAS_TESTTOOLS`](#qiskit.utils.optionals.HAS_TESTTOOLS "qiskit.utils.optionals.HAS_TESTTOOLS") as well. This is generally only needed for Qiskit developers.                                                                                                    |
| **qiskit.utils.optionals.HAS\_IPYTHON**       | If [the IPython kernel](https://ipython.org/) is available, certain additional visualisations and line magics are made available.                                                                                                                                                                                                                                                                                                           |
| **qiskit.utils.optionals.HAS\_IPYWIDGETS**    | Monitoring widgets for jobs running on external backends can be provided if [ipywidgets](https://ipywidgets.readthedocs.io/en/latest/) is available.                                                                                                                                                                                                                                                                                        |
| **qiskit.utils.optionals.HAS\_JAX**           | Some methods of gradient calculation within `opflow.gradients` require [JAX](https://github.com/google/jax) for autodifferentiation.                                                                                                                                                                                                                                                                                                        |
| **qiskit.utils.optionals.HAS\_JUPYTER**       | Some of the tests require a complete [Jupyter](https://jupyter.org/) installation to test interactivity features.                                                                                                                                                                                                                                                                                                                           |
| **qiskit.utils.optionals.HAS\_MATPLOTLIB**    | Qiskit provides several visualisation tools in the [`visualization`](visualization#module-qiskit.visualization "qiskit.visualization") module. Almost all of these are built using [Matplotlib](https://matplotlib.org/), which must be installed in order to use them.                                                                                                                                                                     |
| **qiskit.utils.optionals.HAS\_NETWORKX**      | No longer used by Qiskit. Internally, Qiskit now uses the high-performance [rustworkx](https://github.com/Qiskit/rustworkx) library as a core dependency, and during the change-over period, it was sometimes convenient to convert things into the Python-only [NetworkX](https://networkx.org/) format. Some tests of application modules, such as [Qiskit Nature](https://qiskit-community.github.io/qiskit-nature/) still use NetworkX. |
| **qiskit.utils.optionals.HAS\_NLOPT**         | [NLopt](https://nlopt.readthedocs.io/en/latest/) is a nonlinear optimization library, used by the global optimizers in the `algorithms.optimizers` module.                                                                                                                                                                                                                                                                                  |
| **qiskit.utils.optionals.HAS\_PIL**           | PIL is a Python image-manipulation library. Qiskit actually uses the [pillow](https://pillow.readthedocs.io/en/stable/) fork of PIL if it is available when generating certain visualizations, for example of both [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") and [`DAGCircuit`](qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit") in certain modes.                                      |
| **qiskit.utils.optionals.HAS\_PYDOT**         | For some graph visualisations, Qiskit uses [pydot](https://github.com/pydot/pydot) as an interface to GraphViz (see [`HAS_GRAPHVIZ`](#qiskit.utils.optionals.HAS_GRAPHVIZ "qiskit.utils.optionals.HAS_GRAPHVIZ")).                                                                                                                                                                                                                          |
| **qiskit.utils.optionals.HAS\_PYGMENTS**      | Pygments is a code highlighter and formatter used by many environments that involve rich display of code blocks, including Sphinx and Jupyter. Qiskit uses this when producing rich output for these environments.                                                                                                                                                                                                                          |
| **qiskit.utils.optionals.HAS\_PYLATEX**       | Various LaTeX-based visualizations, especially the circuit drawers, need access to the [pylatexenc](https://github.com/phfaist/pylatexenc) project to work correctly.                                                                                                                                                                                                                                                                       |
| **qiskit.utils.optionals.HAS\_QASM3\_IMPORT** | The functions [`qasm3.load()`](qasm3#qiskit.qasm3.load "qiskit.qasm3.load") and [`qasm3.loads()`](qasm3#qiskit.qasm3.loads "qiskit.qasm3.loads") for importing OpenQASM 3 programs into [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.QuantumCircuit") instances use [an external importer package](https://qiskit.github.io/qiskit-qasm3-import).                                                                       |
| **qiskit.utils.optionals.HAS\_SEABORN**       | Qiskit provides several visualisation tools in the [`visualization`](visualization#module-qiskit.visualization "qiskit.visualization") module. Some of these are built using [Seaborn](https://seaborn.pydata.org/), which must be installed in order to use them.                                                                                                                                                                          |
| **qiskit.utils.optionals.HAS\_SKLEARN**       | Some of the gradient functions in `opflow.gradients` use regularisation methods from [Scikit Learn](https://scikit-learn.org/stable/).                                                                                                                                                                                                                                                                                                      |
| **qiskit.utils.optionals.HAS\_SKQUANT**       | Some of the optimisers in `algorithms.optimizers` are based on those found in [Scikit Quant](https://github.com/scikit-quant/scikit-quant), which must be installed to use them.                                                                                                                                                                                                                                                            |
| **qiskit.utils.optionals.HAS\_SQSNOBFIT**     | [SQSnobFit](https://pypi.org/project/SQSnobFit/) is a library for the “stable noisy optimization by branch and fit” algorithm. It is used by the `SNOBFIT` optimizer.                                                                                                                                                                                                                                                                       |
| **qiskit.utils.optionals.HAS\_SYMENGINE**     | [Symengine](https://github.com/symengine/symengine) is a fast C++ backend for the symbolic-manipulation library [Sympy](https://www.sympy.org/en/index.html). Qiskit uses special methods from Symengine to accelerate its handling of [`Parameter`](qiskit.circuit.Parameter "qiskit.circuit.Parameter")s if available.                                                                                                                    |
| **qiskit.utils.optionals.HAS\_TESTTOOLS**     | Qiskit’s test suite has more advanced functionality available if the optional [testtools](https://pypi.org/project/testtools/) library is installed. This is generally only needed for Qiskit developers.                                                                                                                                                                                                                                   |
| **qiskit.utils.optionals.HAS\_TWEEDLEDUM**    | [Tweedledum](https://github.com/boschmitt/tweedledum) is an extension library for synthesis and optimization of circuits that may involve classical oracles. Qiskit’s [`PhaseOracle`](qiskit.circuit.library.PhaseOracle "qiskit.circuit.library.PhaseOracle") uses this, which is used in turn by amplification algorithms via the `AmplificationProblem`.                                                                                 |
| **qiskit.utils.optionals.HAS\_Z3**            | [Z3](https://github.com/Z3Prover/z3) is a theorem prover, used in the `CrosstalkAdaptiveSchedule` and [`HoareOptimizer`](qiskit.transpiler.passes.HoareOptimizer "qiskit.transpiler.passes.HoareOptimizer") transpiler passes.                                                                                                                                                                                                              |

##### External Command-Line Tools

|                                            |                                                                                                                                                                                                                                              |
| ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **qiskit.utils.optionals.HAS\_GRAPHVIZ**   | For some graph visualisations, Qiskit uses the [GraphViz](https://graphviz.org/) visualisation tool via its `pydot` interface (see [`HAS_PYDOT`](#qiskit.utils.optionals.HAS_PYDOT "qiskit.utils.optionals.HAS_PYDOT")).                     |
| **qiskit.utils.optionals.HAS\_PDFLATEX**   | Visualisation tools that use LaTeX in their output, such as the circuit drawers, require `pdflatex` to be available. You will generally need to ensure that you have a working LaTeX installation available, and the `qcircuit.tex` package. |
| **qiskit.utils.optionals.HAS\_PDFTOCAIRO** | Visualisation tools that convert LaTeX-generated files into rasterised images use the `pdftocairo` tool. This is part of the [Poppler suite of PDF tools](https://poppler.freedesktop.org/).                                                 |

#### Lazy Checker Classes

Each of the lazy checkers is an instance of [`LazyDependencyManager`](#qiskit.utils.LazyDependencyManager "qiskit.utils.LazyDependencyManager") in one of its two subclasses: [`LazyImportTester`](#qiskit.utils.LazyImportTester "qiskit.utils.LazyImportTester") and [`LazySubprocessTester`](#qiskit.utils.LazySubprocessTester "qiskit.utils.LazySubprocessTester"). These should be imported from [`utils`](#module-qiskit.utils "qiskit.utils") directly if required, such as:

```python
from qiskit.utils import LazyImportTester
```

<span id="qiskit.utils.LazyDependencyManager" />

`qiskit.utils.LazyDependencyManager(*, name=None, callback=None, install=None, msg=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/lazy_tester.py "view source code")

A mananger for some optional features that are expensive to import, or to verify the existence of.

These objects can be used as Booleans, such as `if x`, and will evaluate `True` if the dependency they test for is available, and `False` if not. The presence of the dependency will only be tested when the Boolean is evaluated, so it can be used as a runtime test in functions and methods without requiring an import-time test.

These objects also encapsulate the error handling if their dependency is not present, so you can do things such as:

```python
from qiskit.utils import LazyImportManager
HAS_MATPLOTLIB = LazyImportManager("matplotlib")

@HAS_MATPLOTLIB.require_in_call
def my_visualisation():
    ...

def my_other_visualisation():
    # ... some setup ...
    HAS_MATPLOTLIB.require_now("my_other_visualisation")
    ...

def my_third_visualisation():
    if HAS_MATPLOTLIB:
        from matplotlib import pyplot
    else:
        ...
```

In all of these cases, `matplotlib` is not imported until the functions are entered. In the case of the decorator, `matplotlib` is tested for import when the function is called for the first time. In the second and third cases, the loader attempts to import `matplotlib` when the [`require_now()`](#qiskit.utils.LazyDependencyManager.require_now "qiskit.utils.LazyDependencyManager.require_now") method is called, or when the Boolean context is evaluated. For the `require` methods, an error is raised if the library is not available.

This is the base class, which provides the Boolean context checking and error management. The concrete classes [`LazyImportTester`](#qiskit.utils.LazyImportTester "qiskit.utils.LazyImportTester") and [`LazySubprocessTester`](#qiskit.utils.LazySubprocessTester "qiskit.utils.LazySubprocessTester") provide convenient entry points for testing that certain symbols are importable from modules, or certain command-line tools are available, respectively.

**Parameters**

*   **name** – the name of this optional dependency.
*   **callback** – a callback that is called immediately after the availability of the library is tested with the result. This will only be called once.
*   **install** – how to install this optional dependency. Passed to [`MissingOptionalLibraryError`](exceptions#qiskit.exceptions.MissingOptionalLibraryError "qiskit.exceptions.MissingOptionalLibraryError") as the `pip_install` parameter.
*   **msg** – an extra message to include in the error raised if this is required.

### \_is\_available

<span id="qiskit.utils.LazyDependencyManager._is_available" />

`abstract _is_available()`

Subclasses of [`LazyDependencyManager`](#qiskit.utils.LazyDependencyManager "qiskit.utils.LazyDependencyManager") should override this method to implement the actual test of availability. This method should return a Boolean, where `True` indicates that the dependency was available. This method will only ever be called once.

**Return type**

[bool](https://docs.python.org/3/library/functions.html#bool "(in Python v3.12)")

### disable\_locally

<span id="qiskit.utils.LazyDependencyManager.disable_locally" />

`disable_locally()`

Create a context, during which the value of the dependency manager will be `False`. This means that within the context, any calls to this object will behave as if the dependency is not available, including raising errors. It is valid to call this method whether or not the dependency has already been evaluated. This is most useful in tests.

### require\_in\_call

### require\_in\_call

<span id="qiskit.utils.LazyDependencyManager.require_in_call" />

`require_in_call(feature_or_callable: Callable) → Callable`

<span id="qiskit.utils.LazyDependencyManager.require_in_call" />

`require_in_call(feature_or_callable: str) → Callable[[Callable], Callable]`

Create a decorator for callables that requires that the dependency is available when the decorated function or method is called.

**Parameters**

**feature\_or\_callable** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)") *or Callable*) – the name of the feature that requires these dependencies. If this function is called directly as a decorator (for example `@HAS_X.require_in_call` as opposed to `@HAS_X.require_in_call("my feature")`), then the feature name will be taken to be the function name, or class and method name as appropriate.

**Returns**

a decorator that will make its argument require this dependency before it is called.

**Return type**

Callable

### require\_in\_instance

### require\_in\_instance

<span id="qiskit.utils.LazyDependencyManager.require_in_instance" />

`require_in_instance(feature_or_class: Type) → Type`

<span id="qiskit.utils.LazyDependencyManager.require_in_instance" />

`require_in_instance(feature_or_class: str) → Callable[[Type], Type]`

A class decorator that requires the dependency is available when the class is initialised. This decorator can be used even if the class does not define an `__init__` method.

**Parameters**

**feature\_or\_class** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")  *or*[*Type*](circuit_classical#qiskit.circuit.classical.types.Type "qiskit.circuit.classical.types.Type")) – the name of the feature that requires these dependencies. If this function is called directly as a decorator (for example `@HAS_X.require_in_instance` as opposed to `@HAS_X.require_in_instance("my feature")`), then the feature name will be taken as the name of the class.

**Returns**

a class decorator that ensures that the wrapped feature is present if the class is initialised.

**Return type**

Callable

### require\_now

<span id="qiskit.utils.LazyDependencyManager.require_now" />

`require_now(feature)`

Eagerly attempt to import the dependencies in this object, and raise an exception if they cannot be imported.

**Parameters**

**feature** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")) – the name of the feature that is requiring these dependencies.

**Raises**

[**MissingOptionalLibraryError**](exceptions#qiskit.exceptions.MissingOptionalLibraryError "qiskit.exceptions.MissingOptionalLibraryError") – if the dependencies cannot be imported.

<span id="qiskit.utils.LazyImportTester" />

`qiskit.utils.LazyImportTester(name_map_or_modules, *, name=None, callback=None, install=None, msg=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/lazy_tester.py "view source code")

A lazy dependency tester for importable Python modules. Any required objects will only be imported at the point that this object is tested for its Boolean value.

**Parameters**

**name\_map\_or\_modules** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")  *|*[*Dict*](https://docs.python.org/3/library/typing.html#typing.Dict "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*,* [*Iterable*](https://docs.python.org/3/library/typing.html#typing.Iterable "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*]] |* [*Iterable*](https://docs.python.org/3/library/typing.html#typing.Iterable "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*]*) – if a name map, then a dictionary where the keys are modules or packages, and the values are iterables of names to try and import from that module. It should be valid to write `from <module> import <name1>, <name2>, ...`. If simply a string or iterable of strings, then it should be valid to write `import <module>` for each of them.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – if no modules are given.

<span id="qiskit.utils.LazySubprocessTester" />

`qiskit.utils.LazySubprocessTester(command, *, name=None, callback=None, install=None, msg=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/1.0/qiskit/utils/lazy_tester.py "view source code")

A lazy checker that a command-line tool is available. The command will only be run once, at the point that this object is checked for its Boolean value.

**Parameters**

**command** ([*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")  *|*[*Iterable*](https://docs.python.org/3/library/typing.html#typing.Iterable "(in Python v3.12)")*\[*[*str*](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")*]*) – the strings that make up the command to be run. For example, `["pdflatex", "-version"]`.

**Raises**

[**ValueError**](https://docs.python.org/3/library/exceptions.html#ValueError "(in Python v3.12)") – if an empty command is given.
