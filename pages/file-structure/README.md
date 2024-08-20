# File Structure

## Namespaces

Most datapacks in the wild already have a "main" namespace that conveniently contains the bulk of their content; This same concept applies to what Tinted calls a **primary namespace**.

Each datapack must define exactly one **primary namespace**, and any files that a datapack newly introduces _(files that would not exist if the datapack was not in the world)_ must be contained within this namespace.

A datapack can still include as many other namespaces as it needs--**secondary namespaces--**but a datapack must not define any new files within secondary namespaces, only replace.



```
<datapack>
├── data
│   ├── load
│   │   └── tags
│   │       └── function
│   │           ├── load.mcfunction
│   │           ├── post_load.mcfunction
│   │           └── pre_load.mcfunction
│   ├── <primary namespace>
│   │   ├── function
│   │   │   ├── api
│   │   │   │   └── (public functions)
│   │   │   ├── debug
│   │   │   │   └── (debug/admin functions)
│   │   │   ├── _
│   │   │   │   ├── <load function>
│   │   │   │   └── (private functions)
│   │   │   ├── settings.mcfunction
│   │   │   └── uninstall.mcfunction
│   │   ├── tags
│   │   │   ├── function
│   │   │   │   ├── hook
│   │   │   │   │   └── (hooks)
│   │   │   │   ├── implement
│   │   │   │   │   └── (abstractions)
│   │   │   │   └── _
│   │   │   │       └── (private function tags)
│   │   │   ├── load.json
│   │   │   ├── post_load.json
│   │   │   └── pre_load.json
│   │   ├── <registry...>
│   │   │   ├── (public files)
│   │   │   └── _
│   │   │       └── (private files)
│   │   └── objects.mcfo
│   └── <secondary namespace>
└── pack.mcmeta
```



