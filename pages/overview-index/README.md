---
description: A summary of what Tinted is, as a brief but complete index.
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# Overview / Index

### [File Visibility:](broken-reference)

Files are deemed **public** unless under a '\_' directory within their registry, in which they are **private**.

{% code fullWidth="false" %}
```
<namespace>
├── <registry>
│   ├── <public file...>
│   └── _
│       └── <private file...>
└── <...>
```
{% endcode %}

### Robust Loading:

An alternative to '#minecraft:load'/'#minecraft:tick' allows for finer control of loading order.

```
data
├── load
│   └── tags
│       └── function
│           └── load.json
└── my_namespace
    ├── function
    │   └── _
    │       ├── <load function>
    │       └── <tick function>
    └── tags
        └── function
            └── load.json
```

{% code title="load/tags/function/load.json" %}
```json
{
    "values": [
    "#<dependency>:load",
    "#my_namespace:load",
}
```
{% endcode %}

{% code title="my_namespace/tags/load.json" %}
```json
{
    "values": [
    "#my_namespace:_/<load function>"
}
```
{% endcode %}

{% code title="my_namespace:_/<load function>" %}
```
#> my_namespace:_/<load function>
#--------------------
# @LOAD
#--------------------
scoreboard players set *my_namespace load-status 1
<...>
schedule clear my_namespace:_/<tick function>
function my_namespace:_/<tick function>
```
{% endcode %}

{% code title="my_namespace:_/<tick function>" %}
```
#> my_namespace:_/<tick function>
#--------------------
# @LOAD
#--------------------

schedule function my_namespace:_/<tick function> 1t
<...>
```
{% endcode %}

### Function Organization:

The 'function' registry has additional file structure compared to other registries:

```
function
├── api
│   └── <public function...>
├── debug
│   └── <debug function...>
├── _
│   └── <private function...>
├── settings.mcfunction
└── uninstall.mcfunction
```

### Public Function Standards:

All **public** functions must contain a documentation **header**.

{% code title="my_namespace/function/api/subpath/do_something.mcfunction" fullWidth="false" %}
```
#> my_namespace:api > examples/add_mult
#----------------------
# -> a: int
# -> b: int
# => multiply: int = 1
#----------------------
# <- result: int
#----------------------
#> adds <a> and <b>, then multiplies the value by <multiply>.
#----------------------
#- fails if <a> or <b> is bigger than 100.
#----------------------
# 1 - success
# 0 - failure, <a> or <b> was greater than 100.
#----------------------

<IMPLEMENTATION...>
```
{% endcode %}

By design, the only things a developer needs to remember are **names** of parameters and outputs.

<pre data-full-width="false"><code>&#x3C;...>
data modify storage my_namespace:in add_mult.a set value 5
data modify storage my_namespace:in add_mult.b set value 10
function my_namespace:api/examples/add_mult
<strong># (returns 1)
</strong>data get storage my_namespace:out add_mult.result
<strong># (returns 50)
</strong>&#x3C;...>
</code></pre>

### NBT Type Specification:

### Naming Requirements:

### Consistent NBT Data:

### NBT Object Classes:

### Macro Classes:

### Concise Text References:
