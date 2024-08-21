# File Structure

***

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
│   ├── <primary namespace>
│   └── <secondary namespace...>
└── <...>
```

### The Primary Namespace

A datapack must define[^1] exactly one **primary namespace**.

A datapack's primary namespace is the only place where it can define new content/files.

The name of this namespace is the datapack's identifier; Scoreboard objectives, storage locations, resource locations, etc. are pre-fixed with this identifier.

### Linked Namespaces

A datapack may include[^2] any number of **linked namespaces**.

Linked namespaces are included in a datapack in order to override files or otherwise interact with the included namespaces.

Datapacks must only override or interact with the **public** content of any included namespace.

A datapack **must not** define any new files in linked namespaces.

***

{% hint style="info" %}
_<mark style="color:blue;">**Private**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">files outside of a datapack's primary namespace must be treated as non-existent to that datapack.</mark>_
{% endhint %}



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





[^1]: Content is <mark style="color:blue;">defined</mark> by a datapack if it does not already exist within the world's filesystem.&#x20;

    _Ex: It is impossible to define the 'minecraft' namespace because it already exists by default._

[^2]: Content is <mark style="color:blue;">included</mark> in a datapack its path already exists in it's world's filesystem.

    _Ex: overriding a default Minecraft recipe would require your datapack to include the 'minecraft' namespace._
