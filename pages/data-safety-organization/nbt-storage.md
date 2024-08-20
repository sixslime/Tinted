# NBT Storage

Each namespace has exactly seven NBT storage locations designated to it, each with it's own purpose:

> * `<namespace>:data`
> * `<namespace>:var`
> * `<namespace>:in`
> * `<namespace>:out`
> * `<namespace>:settings`
> * `<namespace>:hook`
> * `<namespace>:implement`

***

## Memory Locations

Storing any sort of mutable data in memory falls under the responsibility of `data` or `var`.

## `<namespace>:data`

Storage location for **persistent** data.

All data is **public** unless it is contained within a top-level `_` object (ex: `_.value`), then it's **private**.

Excluding the `_` object, structure must be defined{} and documented by the namespace developer.

## `<namespace>:var`

Storage location for **non-persistent** **private** data and variables.

Structure need not be defined and is to the discretion of the namespace developer.\
(however, data must stay **non-persistent**).

It is encouraged to use this location whenever applicable.

<details>

<summary>Examples</summary>



</details>

***

## Specialized Operations

The other five storage locations are for specialized uses, and are explained more in-depth on their own pages, but in brief summary:

* `in`: For setting API function inputs.
* `out`: For reading API function outputs.
* `settings`: For storing your namespace's global settings (config).
* `hook`: For interfacing with hook function-tags.
* `implement`: For interfacing with abstract implementations.

***

