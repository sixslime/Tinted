---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Introduction

## What is Tinted?

Tinted is a specification for datapacks that aims to make working with **other** datapacks a super smooth and easy experience.

In more exact terms, Tinted is designed to achieve precisely two goals:

1. Eliminate any chance of interference between datapacks/namespaces.
2. Ensure that **ALL** interactions between datapacks are mutually understood by their respective developers.

Importantly, it is designed to be as unobtrusive as possible to any other set of methods, rules, specifications, etc. that fulfill responsibilities outside of these goals.

***

## Who can benefit from Tinted?

<mark style="color:yellow;">**Everyone**</mark> <mark style="color:yellow;"></mark><mark style="color:yellow;">who uses datapacks can benefit from Tinted; any specialization, any level.</mark>

However, some examples of those that can **directly** benefit from Tinted are:

* Authors of datapack libraries/APIs.
* Developers wishing to use any dependencies/libraries in their own datapacks.
* Creators of addon-like datapacks (can possibly be installed in a world with more than one datapack).
* Players that simply want to install more than one datapack in their world.

### What if I Only Use my Own Datapacks / Don't need Dependencies?

Sticking to your own datapacks is a reasonable sentiment, and it's true, if you only ever use your own datapacks, adhering to the Tinted specification may not help you; but consider_, it may help others._

Others may want to extend or build upon your datapack, but it's almost certain that they do not want to dig through files to see what they can and can't touch, what does what, and why scoreboard \<x> keeps being reset.

With Tinted, those developers would already have some understanding on how to interact with your datapack, or, at the very least, know how \*not\* to interfere with it.

***

## What Tinted is Not:

Tinted is **NOT** a "Theory of Everything" framework that handles all responsibilities in cases, nor does it aim to be. As stated, The Tinted specification has exactly two goals, and seeks to achieve **only** these two goals thoroughly and well, leaving the rest to the developer.

To illustrate this point, here are a few things that the Tinted specification does <mark style="color:red;">**NOT**</mark> do:

* Enforce any code-style rules.
* Ensure that the **content** of each datapack "works" with every others'.\
  _<mark style="color:blue;">Tinted only ensures that datapacks will not</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**directly interfere**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">with each other, not necessarily that their content will, in the practical sense, "work correctly" with every others'.</mark>_
* Function as a package manager specification.
* Generate datapacks that are strictly incompatible with non-Tinted datapacks.
* Require any external program to be useful.

{% hint style="danger" %}
<mark style="color:red;">**The CustomModelData Situation**</mark><mark style="color:red;">.</mark>
{% endhint %}
