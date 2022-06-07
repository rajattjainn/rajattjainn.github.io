---
layout: post
title: "Python Code Documentation Guide"
description: ""
date: 22-05-29

---
### Docstring
- A string literal that occurs as the first statement in a module, function, class, or method definition.
- Becomes the `__doc__` special attribute of that object
- Always use `"""triple double quotes"""` around docstrings.

### One-line Docstrings
- Closing quotes are on the same line as the opening quotes.
- No blank line either before or after the docstring.
- Preferred form of such a docstring:

```
def function(a, b):
	"""Do X and return a list."""
```

### Multi-line Docstrings
- A summary line just like a one-line docstring, followed by a blank line, followed by a more elaborate description.
- It is important that the summary line fits on one line and is separated from the rest of the docstring by a blank line.
- The docstring for a **module** should generally list the classes, exceptions and functions (and any other objects) that are exported by the module, with a one-line summary of each.
- The docstring for a **package** (i.e., the docstring of the package’s `__init__.py` module) should also list the modules and subpackages exported by the package.
- The docstring for a **function** or method should summarize its behavior and document its arguments, return value(s), side effects, exceptions raised, and restrictions on when it can be called (all if applicable). Optional arguments should be indicated.

```
def complex(real=0.0, imag=0.0):
	"""Form a complex number.
	Keyword arguments:
	real -- the real part (default 0.0)
	imag -- the imaginary part (default 0.0)
	Returns:
	cplx - Complex number
	"""
	if imag == 0.0 and real == 0.0:
	
		return complex_zero
	...
```

### General Guideliens
- Insert a blank line after **all** docstrings that document a class.
- The docstring of a script should be usable as its “usage” message, printed when the script is invoked with incorrect or missing arguments (or perhaps with a “-h” option, for “help”).
- 
---
**References:**
1. [PEP 257](https://peps.python.org/pep-0257/#what-is-a-docstring)