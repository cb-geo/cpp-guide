### Namespace names
Namespace names are all lower-case, and keep it meaningful. Top-level namespace names are based on the project name `mpm_material`.

### Enumeration names
Preferably, the individual enumerators should be named like constants. The enumeration name, FemShapeFunctions (and FeNumericalError), is a type, and therefore mixed case.

```cpp
enum FemShapeFunctions {
  LINEAR = 0,
  QUADRATIC = 1,
  B_SPLINES = 2,
};
```

### Macro names

You're not really going to define a macro, are you?

In general macros should not be used. However, the only exception being `#define` guards, then they should be named with all capitals and underscores. Macros should not be used for any other purpose.

Use facilities from the C++ language proper, such as inline functions, templates, constructors (for initialization), destructors (for cleanup), exceptions (for exiting contexts), etc instead of using macros.

### Exceptions to Naming Rules
If you are naming something that is analogous to an existing C or C++ entity then you can follow the existing naming convention scheme.

