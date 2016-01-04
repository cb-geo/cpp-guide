## #define guards

> **Note** All header files should have `#define` guards to prevent multiple inclusion. The format of the symbol name should be `<PROJECT>_<PATH>_<FILE>_H_`.

To guarantee uniqueness, they should be based on the full path in a project's source tree. For example, the file `material/bingham.h` in project `mpm` should have the following guard:

```cpp
#ifndef MPM_MATERIAL_BINGHAM_H_
#define MPM_MATERIAL_BINGHAM_H_

...

#endif  // MPM_MATERIAL_BINGHAM_H_
```

