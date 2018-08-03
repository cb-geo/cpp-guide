# C++ Programming Guidelines

* Please adhere to [C++ Core guidelines](https://http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)

* Always use [`clang-format`](./.clang-format) to stylise your code.

```shell
---
# BasedOnStyle:  CB-Geo Computational Geomechanics
AccessModifierOffset: -1
ConstructorInitializerIndentWidth: 4
AlignEscapedNewlinesLeft: true
AlignTrailingComments: true
AllowAllParametersOfDeclarationOnNextLine: true
AllowShortIfStatementsOnASingleLine: true
AllowShortLoopsOnASingleLine: true
AlwaysBreakTemplateDeclarations: true
AlwaysBreakBeforeMultilineStrings: true
BreakBeforeBinaryOperators: false
BreakBeforeTernaryOperators: true
BreakConstructorInitializersBeforeComma: false
BinPackParameters: true
ColumnLimit:     80
ConstructorInitializerAllOnOneLineOrOnePerLine: true
DerivePointerBinding: false
ExperimentalAutoDetectBinPacking: false
IndentCaseLabels: true
MaxEmptyLinesToKeep: 1
NamespaceIndentation: None
ObjCSpaceBeforeProtocolList: false
PenaltyBreakBeforeFirstCallParameter: 1
PenaltyBreakComment: 60
PenaltyBreakString: 1000
PenaltyBreakFirstLessLess: 120
PenaltyExcessCharacter: 1000000
PenaltyReturnTypeOnItsOwnLine: 200
PointerBindsToType: true
SpacesBeforeTrailingComments: 2
Cpp11BracedListStyle: true
Standard:        Auto
IndentWidth:     2
TabWidth:        8
UseTab:          Never
BreakBeforeBraces: Attach
IndentFunctionDeclarationAfterType: true
SpacesInParentheses: false
SpacesInAngles:  false
SpaceInEmptyParentheses: false
SpacesInCStyleCastParentheses: false
SpaceAfterControlStatementKeyword: true
SpaceBeforeAssignmentOperators: true
ContinuationIndentWidth: 4
...

```


## Clang-tidy

Use clang-tidy to modernise the code / lint checker. Generate `compile_commands.json` file before running `clang-tidy`.

```
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_COMPILER=clang++ -DCMAKE_EXPORT_COMPILE_COMMANDS=ON ..

python run-clang-tidy.py -header-filter='.*' -checks='-*,modernize-use-override' -fix
```
