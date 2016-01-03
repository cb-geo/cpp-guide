## Type names

Type names start with a capital letter and have a capital letter for each new word, with no underscores: MpmSolidParticle, LinearElastic.

The names of all types — classes, structs, typedefs, and enums — have the same naming convention. 
For example: 

```cpp
  // classes and structs
  class ParticleSoilMpm { ...
  class ParticleMpm { ...
  struct ParticleMpmProperties { ...
  
  // typedefs
  typedef hash_map<ParticleMpm*, std::string> PropertiesMap;
  
  // enums
  enum MpmErrors { ...
```
