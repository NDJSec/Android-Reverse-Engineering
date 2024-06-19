# Tools: Overview

In this section, and the subsequent sections, we will look at and install a few of the tools that we will be using throughout the course of this series. The first tool we will look at is APKTool. APKTool is an Android reverse engineering tool designed for pulling apart Android apps, also known as Android Packages (APKs). Don't worry too much about APKs, as we will talk about them in greater detail later in this course. The second tool that we will look at is Jadx. Jadx is a Java decompilation tool that is mainly focused on Android APKs. While many Java decompilation tools exist out there, I mainly choose Jadx for it's built-in support of Smali, Android's bytecode that we will discuss more later, extraction and decoding of the Android manifest file, as well as support for easily creating Frida scripts. Don't worry if you aren't sure what a lot of this means, as we will describe all of it in much greater detail later on in this course. I simply wanted to outline some of the reasons I chose Jadx, and why you might want to as well.

After Jadx, we will look at the Android Debug Bridge (ADB). This tool directly from Android, will allow us to easily interact with our Android phone, whether it be an emulator or a real phone. Lastly, we will discuss Ghidra, the open-source native code reverse engineering tool released by the National Security Agency (NSA). This tool will be great for when we get into our native code analysis towards the end of this course. But, don't worry about that now, that is a long way away and by then you will be well on your way to becoming a strong security professional.

However, before we begin to install any of these tools let's look at Linux. We will look at how to install it and talk about some of the reasons we might want to consider Linux as our operating system of choice when performing our analysis.

In the next section, we are going to go through how to install Linux in a virtual machine using VirtualBox and some of the reasons why you might want to consider using Linux for your analysis.