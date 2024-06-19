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

# Techniques

In the world of reverse engineering, there are two main techniques for analysis. These include Static Analysis and Dynamic Analysis. As the name implies, static analysis is the concept of statically looking at the code to perform analysis. In other words, you are analyzing the code without running it. You are simply reading through the code in order to identify important details and gain an understanding of the code. In comparison, dynamic analysis is the concept of looking at the code dynamically. In other words, you are performing your analysis through the act of running the code and analyzing the program's behavior at run-time.

In order to perform this analysis, we as reverse engineers use a variety of tools. In the case of dynamic analysis, we often a disassembler and/or a decompiler to convert our program into some kind of code that we can understand. For this series, we will use 3 main tools for static analysis but know that there are many out there and it ultimately comes down to personal preference and comfort. The three static analysis tools that we will be using throughout the series, are \textit{Apktool}, \textit{Jadx}, and \textit{Ghidra}. However, I will be sure to link to many other tools at the end of this series for those interested.

We will also use a multitude of different dynamic analysis tools throughout this series. Some of these tools include Frida, which is a dynamic instrumentation framework. Unicorn, which is a great emulation framework. ADB, also known as the Android Debug Bridge, is Android's developer interface for interacting with their phones directly for debugging purposes.

We will spend the early parts of this series focusing static analysis through the use of disassemblers and decompilers. Later on in the course, we will look into dynamic analysis.

A disassembler is a program that will allow a reverse engineer to extract the assembler instructions from the machine instructions or the bytecode of the program. This will allow us, as reverse engineers, to more easily understand what is going on. Disassemblers are often paired with decompilers, programs that can convert this assembler into a pseudo-representation of what the original code might have looked like. In our case, this will be Java code, and later this will be C/C++.

In the next section, we will look at some of the tools that we will be using throughout this series, and walk through how to download some of these tools.
