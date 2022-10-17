# HaLocalDeps.Stack

Test for a Stack package to depend on the other Stack package.

AppPackage depend on LibA package

When AppPackage need a updated version of LibA
- In LibA -
1. along with the change to the libarary itself, bump version number of LibA in libA/package.hyaml
2. stack build
3. stack sdist (to update the project tar file)
- In AppPackage -
1. in package.yaml, update the version nubmer of LibA to match with the new veresion
2. in stack.yaml, update the name of the tar file as it has version number encoded
3. stack build

Libraries are considered immutable. so without version nubmer Stack assumes that there's no change