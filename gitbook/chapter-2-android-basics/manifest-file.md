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

# Manifest File

Like any good scientific process, we need to start with background or early analysis. In the case of Android reverse engineering, this comes from the manifest file. The manifest file is the driver for all of the later code that we will see and learn how to reverse engineer. This is our main driver, the first thing Android will look at to get information about an application. For example, the manifest will define the application's name as seen by the system, the minimum Android SDK version, the targeted SDK version, and so much more. The manifest file can be a treasure trove of information for static and dynamic analysis, and it all starts with understanding how to read it.

So let's go tackle this beast together. Are you ready?

The first question we must answer before we can fully understand the manifest file is what kind of file is the manifest file. The manifest file is a control file for an Android application and is written in the form of an Extensible Markup Language (XML) file. XML is a file format that is used to define data in the form of tags and their corresponding information. For example, an XML file could look like the following:

```xml
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
</note>
```

The main thing to know about XML is that it's only responsible for carrying data and nothing else. This means, that at its core, the manifest file doesn't do anything special other than hold the information about the APK it is referencing so that the phone knows what the app can and cannot do. At this point, some of you might be thinking, "Great, let's just go grab it and get started." I agree with that but hold on a minute. You can't simply grab the manifest file. While it is an XML file, it's not just a file you can download from the Play Store and just read. It is compressed into an Android app's final binary, more commonly known as an Android Package (APK). As discussed in the previous section, the APK is compressed into a binary format, this includes the manifest file, therefore we cannot simply unzip the APK and read the manifest file. However, thanks to the work of many smart people, we can read APKs normally using tools like APKTool or Jadx. For right now, we will use APKTool. Later we will use Jadx, as it is one of the tools you are more likely to see when working on Android reverse engineering in the wild.

To analyze the manifest, we need to unpack the APK using APKTool. We can run the following command in the command line to do this. `apktool d <apk>` This command takes the APK file you want to analyze and creates a directory with all the output information. Give the command a few seconds and when you are finished you should see a new directory in your current directory that new directory has the manifest we are looking for along with a lot of other information we will get into later. If you open this directory in your favorite text editor you can open the **AndroidManifest.xml** file. This file is the manifest that we want to explore.

{% code overflow="wrap" lineNumbers="true" %}
```xml
<?xml version="1.0" encoding="utf-8" standalone="no"?>
    <manifest xmlns:android="http://schemas.android.com/apk/res/android" package="com.example.vulnerableapp">
        <uses-permission android:name="android.permission.INTERNET"/>
        <uses-permission android:name="android.permission.READ_PHONE_STATE"/>
        <application android:allowBackup="true" android:debuggable="true" android:icon="@mipmap/ic_launcher" android:label="@string/app_name" android:roundIcon="@mipmap/ic_launcher_round" android:supportsRtl="true" android:theme="@style/AppTheme">
        <activity android:name="com.example.vulnerableapp.LauncherActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN"/>
                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>android:exported=true</activity>
        <activity android:configChanges="keyboardHidden|orientation|screenSize" android:exported="true" android:label="@string/title_activity_google" android:name="com.example.vulnerableapp.GoogleActivity" android:theme="@style/FullscreenTheme"/>
        <meta-data android:name="android.support.VERSION" android:value="26.1.0"/>
        <meta-data android:name="android.arch.lifecycle.VERSION" android:value="27.0.0-SNAPSHOT"/>
    </application>
</manifest>
```
{% endcode %}

The manifest file should look something like this. From this file, we can learn a lot about the APK before even looking at the code. Before you begin to try and understand what is in this file it is important to know that XML follows a simple pattern. For each piece of data you have the tag (the label), and the data (the information being described). For example, **\<uses-permission>** is the tag, and **android:name="android.permission.INTERNET"** is the data. So from this, there are 2 important pieces of data that you want to look at to begin your analysis. These 2 pieces of information are the permissions and the activity tags. The permissions are important because they give you insight into the kinds of capabilities that an application has or is requesting. This can indicate if an application might be doing something malicious. For example, you have a flashlight app that requests location permissions, does that make any sense? No, it does not. Therefore, that might be one piece of functionality you explore when looking at the code to determine whether or not an app is malicious. The second tag you want to look at is the activity tag. This tag is important because it will indicate the entry point of the application. In other words, it will give you the starting location of the application, and the place where the app will go when it first starts up. This can be extremely helpful especially in large applications as sometimes it is difficult to find the starting point. While lots of other information can be found within the manifest, these are the 2 most critical you must understand to begin reverse engineering Android effectively.

So in the example above, the permissions would be INTERNET and READ\_PHONE\_STATE and the entry point would be com.example.vulnerableapp.LauncherActivity. From this information, we can tell that this application can do 2 things: access the internet and internet-based components, and read the phone state this includes values like the IMEI, get Cell information and the Network Access Identifier. Some of this information is used to allow your phone to make calls while others are unique identification numbers attached to your phone. Therefore, this permission and the methods associated with it can be an important piece of information to track with reverse engineering an APK.

Congratulations, you now have the core knowledge needed to begin looking at code and diving into the heart of Android reverse engineering. Join me in the next section as we take a step away from Android for a bit and begin to learn how Java works beginning to learn to reverse engineer Java code before diving head-first into full Android reverse engineering.
