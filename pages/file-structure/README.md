# File Structure

## Namespaces

```
<datapack>
├── data
│   ├── <primary namespace>
│   └── <secondary namespace...>
└── <...>
```

### The Primary Namespace

A datapack must define exactly one **primary namespace**.

The datapack must only define new files/content within it's primary namespace.

The name of this namespace is the datapack's identifier; resource locations, scoreboard objectives, storage locations, etc. that the datapack defines are pre-fixed by this identifier.

### Linked Namespaces

A datapack may include any number of **linked namespaces**.

The datapack may interact with linked namespaces by including **public** files that are defined within those namespaces.

The datapack **must not** define any new files/contents or interact with any **private** files within its linked namespaces.

***

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



