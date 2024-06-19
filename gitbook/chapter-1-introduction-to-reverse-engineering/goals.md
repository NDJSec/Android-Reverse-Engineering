# Goals

Before we can begin to discuss the intriguing and interesting world that is Reverse Engineering, we must first outline what is Reverse Engineering, also known as RE.

Reverse Engineering, as defined by the Merriam-Webster dictionary is:

{% hint style="info" %}
"To disassemble and examine or analyze in detail (a product or device) to discover the concepts involved in manufacture usually to produce something similar"
{% endhint %}

But what does this mean to us? In short, reverse engineering is applying the scientific process to a piece of code, in such a way that we can take an application and begin to try and understand what it does and how it does it. For us, that means beginning to understand Android and its inner workings. From there, we will begin to look into Java and its underlying Java Virtual Machine (JVM). Then we will explore how Android changes this through their use of the Dalvik Virtual Machine, Dalvik bytecode, and the more recent Android Runtime (ART). Lastly, we will begin our descent into the deep world of Native code (C, C++, Assembly) through the use of the Java Native Interface (JNI). This is where the worlds of Native code reverse engineering and Java reverse engineering begin to collide.

At this point, you might be asking yourself one of two questions, "Cool! Where do we start?", or "Why should I care and why should I learn RE?". To the first question I say don't fret, we will begin in due time. To those of you who are still skeptical and might think "why should I care", let's talk about all the great things that reverse engineering has been used for and all the great things that it can still do. Hopefully, by the end of this section I will have convinced you to join the tip of the spear that is security research and reverse engineering.

The first famous example of reverse engineering comes from Phoenix Technologies. In the Mid-1980s, Phoenix implored reverse engineering to create a compatible BIOS (Basic Input Output System) with the IBM BIOS that existed at the time. In their efforts, they were able to create a system that allowed more users to interact with the software of the tech giants of the time IBM. Because of this, you are now able to enjoy various choices when building your systems without having to worry about not being able to use software. If that's not enough, does anyone remember WannaCry or other large malware attacks? These were stopped by reverse engineers.

The truth is that many of you are performing reverse engineering already and don't even know it. Every time you enter a new code base and start poking around to understand the code so you can build your next great invention, you too are performing reverse engineering.

Are you sold yet? I hope so. Join me in learning about the amazing world of reverse engineering and learn to reverse engineer on a system owned and used by millions around the world. Let's become the world's next generation of Cyber Professionals. The choice is yours, so let's embark on this journey together, are you ready?
