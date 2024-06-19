# Android Package: APK

Welcome Ladies and Gentlemen, if you have made it this far you are about to get our first taste of Android reverse engineering.

In order to continue this magical journey of understanding, we must first begin to understand how Android apps or APKs are built. By understanding the components of an APK, it will teach us where to look and help guide us in our early analysis. With that being said, what are the parts of an APK? What even is an APK?

{% hint style="info" %}
An Android APK is an archive file format for Android applications. Similar to zip files, APKs compress all of the app's content into a single file that can be read by the OS.
{% endhint %}

For this reason, we could use a tool like unzip to extract the contents of an APK. However, this wouldn't be a great idea since some files are compressed in additional ways that unzip can't handle. Such files include the manifest file. So with that being said, what are the parts of an APK?

An APK consists of 4 sometimes 5 parts:

1. &#x20;**AndroidManifest.xml**
2. **META-INF** Directory&#x20;
3. **res** Directory&#x20;
4. **smali** Directory

The first component is the AndroidManifest.xml file. We will dive into this much more in our next section, but in short the manifest file is the sort of control file used for the entirety of the application. It defines the entry points, permissions, activities, receivers, and everything else the app wants or needs. From this file you can learn everything an app needs to function and where it will go to get those functions.

The next component is the META-INF directory. The META-INF directory contains all the information needed by the app to ensure that none of its internals have been tampered with. Given much of this directory just contains hashes of the assets included in the app. We won't spend time looking at this in detail. Many times we will never even look into this directory how it is good to understand that it exists and what the purpose of this directory is.

The next component is the res directory. The res directory many of the XML files for various assets within an app. For example, it contains a file named **strings.xml** containing all of the hard-coded strings used by an application. The data in this directory can be useful given that sometimes we can find things such as encryption keys used by apps should their developer hard-code and leave them in the app.

The last and arguably most important directory is the smali directory. This directory contains all the smali code used to make the application. In other words, the smali directory contains all the used by the application that we wish to analyze. From the smali directory, we can get every class, method, and underlying implementation. We will dive heavily into this directory and how to read and analyze its contents. However, for now, it is important to understand that this directory exists and is the location we will get all of our information from.

In short, these are all of the parts that an APK consists of. While some of these parts can change, these are the core ones to understand. From these parts, we can derive all the information we wish to know and reverse engineer any Android application.

In the next section, we will take a deep dive into the Android Manifest file and understand what it is and some key things to look out for when first looking at it. We will explore how to unpack an APK, find the manifest, and lastly how to find the entry point of the APK.
