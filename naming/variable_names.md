## Variable names

The names of variables and data members are all lowercase, with underscores between words. Data members of classes (but not structs) additionally have trailing underscores. For instance: `a_local_variable`, `a_struct_data_member`, `a_class_data_member_`. 

### Common variable names

```cpp
  double mean_area;  // OK - uses underscore.
  double meanarea;   // OK - all lowercase.

  double meanArea;   // Bad - mixed case.
```

### Class/Struct private data members

Private data members of classes or structs, both static and non-static, are named like ordinary non-member variables, but with a trailing underscore.

```cpp
class ElementBase {
    ...
    private:
    double mean_area_;   // OK - underscore at end.
    double mean_area_;   // OK.
    std::vector<std::shared_ptr<Nodes>> vec_nodes_;  // OK.
};
```

### Global variables

There are no special requirements for global variables, which should be rare in any case. If your code requires a global variable, consider prefixing it with g_ and define it as a `const` inside a namespace.

### Constant names

Constants should be named with all capitals and underscores.

```cpp
const double pi = 3.1415926535897;
```
