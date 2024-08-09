---
layout: post
title:  "MachO Binary Obfuscation"
# date:   2024-06-30 16:00 +0800
categories: Binary Obfuscation
pin: true
---

Binary Obfuscation in MachO
===========================

### Purpose
There are many reasons why we would want to obfuscate code! A common purpose of obfuscation is to hinder Reverse Engineering, allowing software developers to prevent malicious attacks on their product or protect intellectual property.

In my case, the main goal is to prevent the evasion of Jailbreak Detection through the use of hooks, or at least make it harder for attackers to find the correct functions to hook.

To do this we will utilize the [LIEF framework](https://lief.re/), a powerful Library for manipulating PE, ELF and `MachO` Binaries.

As we are working directly on the compiled Binary, this is considered file format modification, which is powerful in preventing reverse engineering tools from working correctly.

As stated by Romain Thomas, Author of [The Poor Man's Obfuscator](https://www.romainthomas.fr/publication/22-pst-the-poor-mans-obfuscator/) which was heavily referenced for this project.

> "File format modifications are less resilient than classical obfuscation since the original assembly code remains unchanged.\
On the other hand, this is a topic that is less explored than regular obfuscation and for which, it exists less tooling, automation, and literature." - Romain Thomas

### What is Code Obfuscation?
Code obfuscation is the 

### What is MachO?
Mach-O, short for Mach object file format, is a file format for executables, object code, shared libraries, dynamically loaded code, and core dumps. It was developed to replace the a. out format. It is used on on all of Apple's devices, including MacOS and `iOS`.

For a more detailed layout, we can refer to the [MachO file format reference](https://github.com/aidansteele/osx-abi-macho-file-format-reference). Note that this is an outdated version of Apple's documentation, and there have been changes to the file format.

### Things to note when working with MachO
- Binaries are required to be signed before execution, if not they will encounter a `killed: 9` error.




