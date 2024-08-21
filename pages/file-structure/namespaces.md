# Namespaces

```
<datapack>
├── data
│   ├── <primary namespace>
│   ├── (linked namespaces...)
│   └── (...)
└── (...)
```

URC,&#x20;

## The Primary Namespace

A datapack must define[^1] exactly one **primary namespace**.

A datapack's primary namespace is the only place where it can define new content/files.

The name of this namespace is the datapack's identifier; Scoreboard objectives, storage locations, resource locations, etc. are pre-fixed with this identifier.

## Linked Namespaces

A datapack may include[^2] any number of **linked namespaces**.

Linked namespaces are included in a datapack in order to override files or otherwise interact with the included namespaces.

Datapacks must only override or interact with the **public** content of any included namespace.

A datapack **must not** define any new files or interact with **private** files in linked namespaces.

***

## The Entry-point

Often in the wild,&#x20;

```
<datapack>
├── data
│   ├── load
│   │   └── tags
│   │       └── function
│   │           ├── load.json
│   │           ├── post_load.json
│   │           └── pre_load.json
│   ├── <primary namespace>
│   │   └── tags
│   │       └── function
│   │           ├── load.json
│   │           ├── post_load.json
│   │           └── pre_load.json
│   └── <linked namespace...>
└── <...>
```

[^1]: Content is <mark style="color:blue;">defined</mark> by a datapack if it does not already exist within the world's filesystem.&#x20;

    _Ex: It is impossible to define the 'minecraft' namespace because it already exists by default._

[^2]: Content is <mark style="color:blue;">included</mark> in a datapack its path already exists in it's world's filesystem.

    _Ex: overriding a default Minecraft recipe would require your datapack to include the 'minecraft' namespace._
