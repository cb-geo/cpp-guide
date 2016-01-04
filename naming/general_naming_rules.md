## General naming rules

> **Note** Function names, variable names, and filenames should be descriptive; eschew abbreviation.

* Give as descriptive a name as possible, within reason. Do not worry about saving horizontal space as it is far more important to make your code immediately understandable by a new reader. 

* Short names, such as `x` and `i`, are meaningful when used conventionally; that is, `x` should be a local variable or a parameter and `i` should be a loop index.

```cpp
  int solid_particles_;		// No abbreviation.
  int num_errors;          	// "num" is a widespread convention.
  for (unsigned i = 0; ...      // Used conventionally as a loop index.
```

> **Danger**
* Do not use abbreviations that are ambiguous or unfamiliar to readers outside the project.
* Do not abbreviate by deleting letters within a word. 


```cpp
  int n;                   // Meaningless.
  int nerr;                // Ambiguous abbreviation.
  int n_comp_conns;        // Ambiguous abbreviation.
  int lem_connections;     // Only your group knows what this stands for.
  int pc_reader;           // Lots of things can be abbreviated "pc".
  int prtcl_id;            // Deletes internal letters.
  int the_number_of_material_points_in_a_cell
                           // A bit too long.
```
