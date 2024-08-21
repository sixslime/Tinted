---
description: >-
  Words that are used throughout the specification that should be known before
  proceeding.
---

# Important Terms

## Namespace

A namespace is any folder under the `data` folder in a datapack.

```
<datapack>
├── data
│   └── <namespace...>
└── <...>
```

The word "namespace" may be used to refer to a namespace itself, but also may be used to refer all files within a namespace; it should remain obvious which definition is intended.

## Public/Private

**Public:** Accessible and usable by all namespaces.

**Private:** Accessible only by the same namespace.\
_Treated as non-existent to other namespaces._

## Persistent/Non-persistent

Forms of data will be categorized as either **persistent** or **non-persistent**.

**Persistent:** Data is allowed to exist beyond the tick that it is created.

**Non-persistent:** Data must only exist within a single sub-tick within a defined scope; it should be destroyed/cleared in the same tick/scope it was created.\
_In other words, non-persistent data does not exist outside of the function(s) that use it._

{% hint style="info" %}
<mark style="color:blue;">It is OK for</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**non-persistent**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">data to exist in a</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**persistent**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">context.</mark>
{% endhint %}

## "U.N.C."

Roughly, "Under Normal/Non-Tinted Circumstances".

U.N.C. is used to refer to situations where Tinted is **NOT** present.

_Example: "U.N.C. a datapack would not have a '\_' folder"._

