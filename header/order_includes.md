## Order of includes

Use standard order for readability and to avoid hidden dependencies: 

* C library, 
* C++ library,
* other libraries' `.h`,
* your project's `.h`.

> **Note** Within each section the includes should be ordered alphabetically.

All of a project's header files should be listed as descendants of the project's source directory without use of UNIX directory shortcuts . (the current directory) or .. (the parent directory). For example, `mpm/include/material/bingham.h` should be included as

```cpp
#include "material/bingham.h"
```

In `dir/foo.cc` or `dir/foo_test.cc`, whose main purpose is to implement or test the stuff in `dir2/foo2.h`, order your includes as follows:

* `dir2/foo2.h` (preferred location — see details below).
* C system files.
* C++ system files.
* Other libraries' .h files.
* Your project's .h files.

With the preferred ordering, if `dir2/foo2.h` omits any necessary includes, the build of `dir/foo.cc` or `dir/foo_test.cc` will break. Thus, this rule ensures that build breaks show up first for the people working on these files, not for innocent people in other packages.

`dir/foo.cc` and `dir2/foo2.h` are often in the same directory (e.g. `base/basictypes_test.cc` and `base/basictypes.h`), but can be in different directories too.

> **Caution** You should include all the headers that define the symbols you rely upon, except in the unusual case of forward declaration. If you rely on symbols from `bar.h`, don't count on the fact that you included `foo.h` which (currently) includes `bar.h`: include `bar.h` yourself, unless `foo.h` explicitly demonstrates its intent to provide you the symbols of `bar.h`. However, any includes present in the related header do not need to be included again in the related `cc` (i.e., `foo.cc` can rely on foo.h's includes).

For example, the includes in `material/base/material_base.cc` might look like this:

```cpp
#include "base/material_base.h"  // Preferred location.

#include <sys/types.h>
#include <unistd.h>

#include <algorithm>
#include <vector>

#include "base/material_container.h"
```

### Exception
Sometimes, system-specific code needs conditional includes. Such code can put conditional includes after other includes. Of course, keep your system-specific code small and localized.

