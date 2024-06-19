# Android Permissions

In this section, we will look at Android Permissions, one of the critical backbones of Android, and its security model.

So some of you might be wondering "What are Android permissions?". I'm so glad you asked. Android permissions are exactly what they sound like, they are the permissions users grant to an application. So why are they important and why should we care? Well, understanding Android permissions will not only allow you to understand what an app is doing, but also how to identify points of interest that will help make our later analysis easier.

So how do you use and interact with these permissions? You do this through the use of the Android Manifest; there will be more on that in the next section. For the time being, know that a developer simply declares the permissions that they want in their manifest file and the operating system (OS) does the rest.

We can declare permissions, so what? But what can they do and are they good or are they bad?

At their core permissions are not all bad and they allow developers to bring us many of the great features that we've come to know and love. However, Android themselves gives us some guidance here on how to discern these permissions. Android defines 3 permission types for us:

1. Normal: Very little risk, default value&#x20;
2. Dangerous: For high-risk protected operations&#x20;
3. Signature: When the requesting and declaring apps are signed with the same signature&#x20;

**Normal permissions** are just that, they are normal. They involve very little risk and therefore are granted automatically when requested. Such permissions include Internet, Bluetooth, Receive boot complete, and Access WiFi state. While some of these might be worth looking at during static analysis, Android defines them as "permissions that allow access to data and actions that extend beyond your app's sandbox but present very little risk to the user's privacy and the operation of other apps."

In comparison, **Dangerous permissions,** are permissions that are defined to perform high-risk protected operations that could pose a risk to a user's privacy. At this point, some of you might be asking "If they pose a risk to user's privacy why do they exist?". You might be right, but first consider some of the functionalities defined as dangerous permissions. These include Camera, Read contacts, Write contacts, Send SMS, Read SMS, Call phone, Access external storage, and more.

Lastly, we have **Signature permissions**, which are permissions that are automatically granted across applications that have been signed by the same key. In other words, apps that have been created by the same developer. The idea here is that apps from the same developer might want to be able to inter-op and so when a permission is granted to one application, if it is a signature permission, it is then automatically granted to all other permissions from the same developer assuming they request it.

However, some of you might be wondering how does one grant permissions to an app. This is through the use of 2 mechanisms. The first is the manifest--more on that later. The second mechanism that we are going to focus on a bit is Android's runtime permission scheme. The runtime permission scheme is the current way that Android grants permissions to the phone. As the name suggests, this is done by prompting the user at runtime when this permission is wanting to be used.

With that being said, why does this matter? Okay, so we just spent the better part of a page discussing Android permissions, but what does this have to do with Android Reverse Engineering? Why does this crazy guy care so much about the underlying Android system?

Well, don't worry we will get to the fun stuff very soon. One of the biggest questions I have been asked when teaching reverse engineering is "What are we looking for?". Unlike a gamified challenge where we are looking for a well-defined flag in the real world, we often have to come up with the thing we are looking for while we are looking for it. Therefore, in order to do this we must start with Android permissions. A strong understanding of Android's permissions will allow us to put what we look at into perspective and to become even better security professionals. At the end of the day it's great if we can read the code, but if we can't put that into the bigger picture and think critically about what we are looking at, we will have a hard time placing our analysis.

In the next, section we will begin to get our hands dirty with some real reverse engineering. To do this, we will look at the Android Packages and learn how to pull them apart.
