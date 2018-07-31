## Inline functions


> **Note** Inlining a function can generate more efficient object code, as long as the inlined function is small. Feel free to inline accessors and mutators, procedural integration, and other short, performance-critical functions.

When the compiler inline-expands a function call, the function’s code gets inserted into the caller’s code stream. No matter how you designate a function as inline, it is a request that the compiler is allowed to ignore: the compiler might inline-expand some, all, or none of the places where you call a function designated as inline. Procedural integration[^isocpp] might remove a bunch of unnecessary instructions, which might make things run faster.


### Caution
* Beware of destructors, which are often longer than they appear because of implicit member- and base-destructor calls! Virtual and recursive functions are not normally inlined.

* It's typically not cost effective to inline functions with loops or switch statements (unless, in the common case, the loop or switch statement is never executed). 

* If the executable size is too big, the system might spend most of its time going out to disk to fetch the next chunk of code.

## Inline member functions

> **Note** When your class is intended to be highly reused, you should define your inline member function, which are longer than 2 lines, outside the class body.

Your reusers will read your header file to determine what the class does - external behaviour and implementation. From a practical standpoint, this separation of the public-part of the class from the non-public part makes life easier and safer for your class’s reusers.

```cpp
class Foo {
public:
  void method();  // Best practice: Don't put the inline keyword here
  // ...
};

inline void Foo::method() { // Best practice: Put the inline keyword here
  // ...
}
```


# Reference
[^isocpp]: https://isocpp.org/wiki/faq/inline-functions#procedural-integration
