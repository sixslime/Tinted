# Namespaces

## Organization

<details>

<summary>Abstract Intro</summary>



</details>

```
<datapack>
├── data
│   ├── <primary namespace>
│   ├── (linked namespaces...)
│   └── (...)
└── (...)
```

### The Primary Namespace

A datapack must define[^1] exactly one **primary namespace**.

A datapack's primary namespace is the only place where it can define new content/files.

The name of this namespace is the datapack's identifier; Scoreboard objectives, storage locations, resource locations, etc. are pre-fixed with this identifier.

### Linked Namespaces

A datapack may include[^2] any number of **linked namespaces**.\
All namespace within a datapack that is not it's primary namespace is considered a linked namespace.

Linked namespaces are included in a datapack in order to override files or otherwise interact with files outside of it's primary namespace.

A datapack may only override/interact with the **public** content of any linked namespace.\
A datapack may **not** define any new files within linked namespaces.

{% hint style="info" %}
Most interactions with linked namespaces will be in the form of appending to or replacing tags. This is the recommended way of interacting with linked namespaces; any other form should be performed with caution and consideration.
{% endhint %}

***

## Entry Points and Loading

<details>

<summary>Abstract Intro</summary>

U.N.C. namespaces append their entry-point function(s) (a.k.a. load functions) to the `#minecraft:load` tag and their tick function(s) to the `#minecraft:tick` tag. This has number of issues, namely:

* `#minecraft:tick` is called before `#minecraft:load`
* It puts the responsibility fully on the developer of a dependent datapack to figure out how to ensure their dependency(s) load/tick in the correct order.

</details>

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

### Load Implementation

'load' is a reserved namespace that all Tinted datapacks implicitly depend upon.

A separate datapack is required to contain an implementation of 'load' that adheres to the entry-point system that the Tinted specification defines in this section.

The official implementation of 'load' can be found [here](https://github.com/sixslime/load).\
_Tinted does not strictly require the use of the official implementation._

> <mark style="color:yellow;">It is important to note that a proper implementation of 'load' is effectively zero-cost and can be easily recreated by any developer who wishes to make their own.</mark>



[^1]: Content is <mark style="color:blue;">defined</mark> by a datapack if it does not already exist within the world's filesystem.&#x20;

    _Ex: It is impossible to define the 'minecraft' namespace because it already exists by default._

[^2]: Content is <mark style="color:blue;">included</mark> in a datapack its path already exists in it's world's filesystem.

    _Ex: overriding a default Minecraft recipe would require your datapack to include the 'minecraft' namespace._
