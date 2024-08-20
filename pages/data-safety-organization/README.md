# Data Safety/Organization

Resource files in a namespace are organized and contained within that namespace inherently.\
For example, a loot table from the namespace 'foo' already has the prefix `foo:` because the loot table file is in the 'foo' directory.

This, however, cannot be said about NBT data, scoreboards, entity tags, etc. that a namespace declares or changes. The following specifications aim to organize and contain such elements, such that each individual namespace **cannot** interfere with any another, but can still communicate with others in an organized fashion.
