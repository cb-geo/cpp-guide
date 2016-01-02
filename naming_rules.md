# Naming

The most important consistency rules are those that govern naming. The style of a name immediately informs us what sort of thing the named entity is: a type, a variable, a function, a constant, a macro, etc., without requiring us to search for the declaration of that entity.

## General naming rules

Function names, variable names, and filenames should be descriptive; eschew abbreviation.

Give as descriptive a name as possible, within reason. Do not worry about saving horizontal space as it is far more important to make your code immediately understandable by a new reader. Do not use abbreviations that are ambiguous or unfamiliar to readers outside the project, and do not abbreviate by deleting letters within a word. Short names, such as `x` and `i`, are meaningful when used conventionally; that is, `x` should be a local variable or a parameter and `i` should be a loop index.

```cpp
  int solid_particles_;		// No abbreviation.
  int num_errors;          	// "num" is a widespread convention.
  for (unsigned i = 0; ...      // Used conventionally as a loop index.
```
