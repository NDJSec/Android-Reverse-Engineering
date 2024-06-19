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

# Tools: Jadx

As some of you may or may not know a majority of Android code is written in Java or Kotlin, both of which run on top of the Java Virtual Machine (JVM). Don't worry if you do know what the JVM is, we will talk about that later. But to be good Android reverse engineers, we need a tool that can read Java code right? For that, I introduce you to Jadx, a Java decompilation tool that can do it all. Reading Java bytecode or Smali Android bytecode? Jadx has you covered. Need to read the Android manifest? Jadx has you covered. Want to easily create Frida scripts? Jadx can do that for you too.

Some of you might at this point be thinking "What does any of that mean?". And to that I say, don't worry about that right now. I promise by the end of this series you will see why all of that is amazing and why we might want the functionality. For now, just understand that Jadx is a powerful tool that can help us endlessly. Also, did I mention that you can get all this for the low, low price of free?

That's right, you can get all this amazing functionality completely for free. And to make things better, Jadx is completely open-source. So why wait? Let's go install Jadx right now!

First go to the Jadx GitHub, which can be found [here](https://github.com/skylot/jadx), and download the latest version of Jadx. When downloading the file, place it in the **Tools** directory we created earlier. Once that has been done, run the following commands:

{% code lineNumbers="true" %}
```bash
cd ~/Tools 
mkdir Jadx 
unzip jadx-1.4.7.zip -d Jadx 
mkdir bin 
cd bin 
ln -s ~/Tools/Jadx/bin/jadx jadx 
ln -s /Tools/Jadx/bin/jadx-gui jadx-gui 
export PATH=$PATH:/Tools/bin/ 
```
{% endcode %}

Once you run these commands, you will have installed Jadx. However, let's break down what those commands are doing so it doesn't just look like black magic. The first 5 lines unzip the jadx program and place them into a directory for storage. The real magic then happens in the last 3 lines. The first 2 are creating what is called a symbolic link--for the Windows people out there think of this as a shortcut. The last line is placing the directory that has these links in our **PATH** environment variable. This is the place where the OS goes to look when we run commands. By doing this, we can now run the **jadx-gui** or **jadx** commands from anywhere on our system and launch the program.

Congrats, you have officially installed Jadx and learned a bit about symbolic links. You truly are on your way to becoming a true security professional.

Join me next, as we dive into the Android Debug Bridge (ADB), looking at what it is and how to install it.
