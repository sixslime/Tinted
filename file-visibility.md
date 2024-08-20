# File Visibility

Files are **public** unless under a '\_' directory within their registry, in which they are **private**.

{% code title="<datapack>/data/" %}
```
<namespace>
├── <registry...>
│   ├── <public file...>
│   └── _
│       └── <private file...>
└── <...>
```
{% endcode %}

**Other namespaces** can access and use public files, while private files _might as well not exist_ to them.

***

## What Should be Public/Private?

* **Public files** have a general use, or could be reasonably utilized by another datapack.
* **Private files** usually have a specific implementation use, or just would not make sense to use from another namespace.

{% hint style="info" %}
If you're having trouble, imagine your datapack was part of the base game, would it make sense for the file(s) to exist?
{% endhint %}

### <mark style="color:yellow;">Some Examples of Public Files:</mark>

* <mark style="color:yellow;">A loot table for a custom mob or block.</mark>
* <mark style="color:yellow;">An enchantment that is visible to the player.</mark>
* <mark style="color:yellow;">A damage type that a public enchantment inflicts.</mark>
* <mark style="color:yellow;">An block tag that specifies blocks that a custom mob takes damage on.</mark>
* <mark style="color:yellow;">A dimension that the player can enter.</mark>
