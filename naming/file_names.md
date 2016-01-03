## File names

Filenames should be all lowercase and can include underscores (_). Follow the conventions of your project.

> **Note** C++ files should end in `.cc` and header files should end in `.h`.

Examples of acceptable file names:

```cpp
    element.h
    particle_soil_mpm.cc
    particlesoilmpm_test.cc  // unit test files
```

> **Caution** Do not use filenames that already exist in /usr/include, such as error.h.

In general, make your filenames very specific. For example, use `particle_soil_mpm.h` rather than `particle.h`. A very common case is to have a pair of files called, e.g., `foo_bar.h` and `foo_bar.cc`, defining a class called `FooBar`.

Inline functions must be in a .h file. If your inline functions are very short, they should go directly into your `.tcc` file. See [`.tcc` files]() for more information on how to defined shared templatised classes. 

```cpp
  particle_soil_mpm.h    // The class declaration.
  particle_soil_mpm.cc   // The class definition.
  particle_soil_mpm.tcc  // Templatised class definitions.
```

> **Warning**  Don't forget that header files require `#define` guards.


