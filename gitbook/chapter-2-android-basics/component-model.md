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

# Component Model

In Android, the component model is one of the main drivers of how apps work. A solid understanding of the component model is crucial to a strong understanding of Android and will allow us to become even better Android reverse engineers.&#x20;

But what is the component model and why is it so important,?

The component model is the underlying model of how parts of an Android app, or components, interact with each other. The component model consists of a few important parts.&#x20;

1. Activities&#x20;
2. Services&#x20;
3. Content Providers&#x20;
4. Broadcast Receiver&#x20;

**Activities** are the parts of the app that take user input. The most important activity is the **Main Activity**. The main activity is often the entry point of an Android application and is often the window displayed to the user. **Services** are background actions that the app can perform. **Content Providers** are interfaces to data, for example, an application might have to use a content provider to access the phone's local storage, a cloud server, or even program memory. **Broadcast Receivers** are components that wait for and react to events. For example, an application can have a broadcast receiver for SMS messages. This means that a broadcast receiver will sit there and wait to respond to an event that has been launched. However, these events can be invoked by either the app itself or an external app, but we will get more into this later.

At this point, you might be thinking to yourself "Why does this guy care so much about Android's internals? I just want to do RE." And to that I say don't worry, the importance of this will reveal itself soon. But for the impatient, let me give you some examples of why we should care about the component model and how this differs from your normal Linux computer.

What if I were to tell you that an Android application could have multiple entry points. Or about the fact that an app could accept requests from other apps, or even send data to other apps at their request. Or even that just because you close an app, it doesn't mean that it's not running. Or even that another app could start an app in the background without even telling you.

This is all thanks to the component model, which hopefully you can now begin to see that understanding the component model will help the rest of the code that we REs later make sense. For the more astute of you out there, you might be wondering "Nic I thought you said that each program runs in its own user and often its own process, how can an app request information?" This comes from the component model and broadcast receivers.

So some of you might be thinking, this sounds very unsafe and why does Android allow this? This is because many of these functionalities are perfectly normal for most apps. Therefore, it is up to us, as security professionals, to understand what is bad and what isn't. To do that, we must first understand Android's component model.

So how do we use this model? For that we have to start with the Android Manifest file. But before we start with tha, let's talk about permissions. Android permissions will be our gateway into this journey. Are you ready?

In the next section, we will dive into Android Permissions. What they are and what they are used for.
