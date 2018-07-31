## .tcc files

> **Note** You may use file extension `.tcc` for shared templatised classes.

A template is not a class or a function. A template is a *pattern* that the compiler uses to generate a family of classes or functions.

In order for the compiler to generate the code, it must see both the template definition (not just declaration) and the specific types/whatever used to *fill in* the template. For example, if you're trying to use a `Foo<int>`, the compiler must see both the Foo template and the fact that you're trying to make a specific `Foo<int>`.

A common solution to this is to write the template declaration in a header file, then implement the class in an implementation file (for example `.tcc`), and include this implementation file at the end of the header.

```cpp
// foo.h
template <typename T>
struct Foo {
    void do_something(T param);
};

#include "foo.tcc"

// foo.tcc
template <typename T>
void Foo<T>::do_something(T param)
{
    //implementation
}
```

This way, implementation is still separated from declaration, but is accessible to the compiler.
