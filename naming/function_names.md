### Function names

#### Regular Functions

Functions should be lower case. Use underscores to seperate words.

If your function crashes upon an error, you should append _or_die to the function name. This only applies to functions which could be used by production code and to errors that are reasonably likely to occur during normal operation.

```cpp
add_new_material()
delete_material_point()
open_file_or_die()
```

#### Accessors and Mutators

Accessors and mutators should match the name of the variable. It is preferrable to overload the accessors and mutator functions. This shows an excerpt of a class whose instance variable is `mean_area_`.

```cpp
class ElementBase {
public:
...
// Return mean area
double mean_area() const {
  return mean_area_;
}

// Assign mean area
void mean_area(const double& area) {
  mean_area_ = area;
}

private:
// mean area
double mean_area;
};
```

You may also use lowercase letters for other very short inlined functions. For example if a function were so cheap you would not cache the value if you were calling it in a loop, then lowercase naming would be acceptable.


