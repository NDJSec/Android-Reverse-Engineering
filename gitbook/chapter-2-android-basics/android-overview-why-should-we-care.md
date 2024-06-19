# Android Overview: Why should we care?

Before we begin, you might be thinking to yourself "Why Android?" And you would be right, why would we want to learn about Android reverse engineering? What if I were to tell you that Android has 73% of the global market share. Not convinced yet? How about the fact that all you need is $25 and a phone to start developing on Android. This means that the barrier to entry is very low. Furthermore, with 73% of the market share, it proves to be a lucrative place for malware authors to create their malware or for shady businesses to steal your data.

However, you might be asking yourself "Doesn't the app store prevent this?". While they can, they are also human and like you or I, they can miss things. Furthermore, in Android you can side-load apps. This means that a user can self-install apps, without the use of an app store. This makes it that much more important for us to be educated and vigilant security professionals.

Hopefully, you are now beginning to see why the Android platform is important to understand, especially as security researchers.

With that being said, how does Android differ from your computer? While Android runs Linux, its approach to security makes the Android's external surface vastly different from your computer. But how is this done?

One way in which Android differs from Linux is through the use of its middleware. This middleware consists of the Java API Framework, Native C/C++ libraries, the Android runtime, and the Hardware Abstraction Layer (HAL). This middleware layer combined with Android's choice to not focus on UNIX processes makes the Android landscape rather different.

<figure><img src="https://developer.android.com/static/guide/platform/images/android-stack_2x.png" alt=""><figcaption></figcaption></figure>

Furthermore, Android uses its API for common resources and inter-app communication. Android also has a strong use of components.

But what does this mean for us? Why should we care?

Understanding Android and its security model is crucial for us to later understand the code that we will be looking at. It's great if we can understand how to read Java code and learn to reverse engineer the Java bytecode, but what does that matter if we can't understand what it means in the bigger picture?

It might not make sense now, but hopefully throughout this chapter we will begin to see the importance of not only understanding Java, but also understanding Android itself.

In the next section, we will look at a brief overview of the Component Model in Android.
