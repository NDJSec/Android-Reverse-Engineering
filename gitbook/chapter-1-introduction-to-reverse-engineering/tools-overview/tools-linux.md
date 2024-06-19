# Tools: Linux

In this section, we will be looking at Linux and walking through a simple guide on how to install Linux on your computer using a virtual machine (VM). For this, we are going to use VirtualBox, a free virtualization software for Window, Mac, and Linux.

Some of you might be wondering why we would want to use Linux, over say Windows or Mac. The short answer is because of some of the tools and scripts we will use later on in this series are written for UNIX-based operating systems and work best on Linux. However, it is worth noting that for a lot of what we will be doing MacOS works perfectly fine and you can choose to skip this section if you'd like. However, for Windows, I suggest you continue with this section using a VM. You may also use the Windows Subsystem for Linux (WSL). While I will not be going over how to install WSL, it should be able to handle many of the analysis tools we will use. With that being said, let us begin.

First, download the VirtualBox software. To do that you can go to the following link below and install your appropriate version.

&#x20;[VirtualBox Download](https://www.virtualbox.org/wiki/Downloads)

{% hint style="info" %}
At the time of writing this, if you are on an M1 or M2 Mac, VirtualBox does not work entirely correctly. If you are on one of these platforms, feel free to skip this section as many of the tools here will work without issue on Mac.
{% endhint %}

You will also need to install a Linux ISO file. An ISO file is the file type used on operating systems installers. We will use this ISO file in order to install our Linux distribution of choice, in this case, Ubuntu.

[Ubuntu Install Linux](https://ubuntu.com/download/desktop)

In this next part, we will be following Ubuntu's guide for installing an Ubuntu VM in VirtualBox. The link to their guide can be found [here](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview).

Once, you have the installer downloaded, run the installer and follow the install instructions provided by the VirtualBox installer. All the defaults are fine for what we will be doing. Once you have VirtualBox installed, you should see a screen that looks like the following:

<figure><img src="https://lh5.googleusercontent.com/9qjVTUIYb156EpeJ_ttAPgg_lZgpmR_6CD8G25O7G0PAp1-uxI4LMhR2bEiQxSVEszjnZVqzGby3ycr6Btv1esQIs7JIItyOE1Do09hAG8HbErivtu1UCgiPm_USC8bUfPxM3e1zWTyewkFAVbkLPPR2Y1n24aOQB21yjqUdYItkneNeMQ-pnY-utcjZFQ" alt=""><figcaption></figcaption></figure>

Next, we will create a new VM. To do this, we want to click \textbf{New} and fill in the appropriate details. For the name, you can choose whatever you like. For the machine folder, the default choice is fine. Then for the ISO image, select the Ubuntu ISO we downloaded earlier. Lastly, hit next.

<figure><img src="https://lh4.googleusercontent.com/QzuEtSrV0NEZyNkXQAraETw1wpM0lpCCmm0OZYKe347N4gsGIMSVaDLByWWw6rb7_2IjxgR3r_Ydodj1vYwdgWT9VvWG0eS5FAteZWupWFmNIJsXABJ_09BqYRuTop1wFPWm1OaH0c0c9cysl55o8V4qEDwXSbAPsrrBqMsy5herGsFskCq4T5lQxvi8UA" alt=""><figcaption></figcaption></figure>

Next, we will create a user profile that we can use when using this machine. For this, enter in any values for your username and password. The default credentials are username: **vboxuser** and password: **changeme.** However, be sure to change these defaults as they will create a user without sudo access, which we will need over the course of this series. Lastly, enter a hostname of anything, ensuring no spaces proceed it and you can leave the domain name blank. Also, select Install Guest Additions as this will allow us to copy and paste to and from the VM, along with other very useful functionality. Once done, click **Next** to continue.

<figure><img src="https://lh5.googleusercontent.com/Tv2j7d4NIjTG60q7F1CSAMV2tiAECqO0Nho28u9CZuWlPVzh0JeaZKvFFLfJV-FHnQR77yfn6dAIUmeyUy8Y2dQJZ32qu5DrDwLFeO_H6SajvW0Es-WgwMFDgsDohZbJC7yTEIeZKbwkPY9Xby7VaSeXeMJfJM2p5C4t_lPg116HA79eNifCZkZXrIs_UQ" alt=""><figcaption></figcaption></figure>

Next, we must define the VM's resources such as memory and processors. For this, around 8GB of RAM is recommended by Ubuntu, and 4 CPUs are also recommended, however, this will depend on your system. A good note is to keep the sliders in the green as this will help prevent issues. Once done, click **Next** to continue.

<figure><img src="https://lh4.googleusercontent.com/wSFUfjtt2e_Vjxqx7Ohx6-cUSs6uZGIl8dH3kM3F__e_SCFSImh72YwQ2j4u64tvjZTXM2oNtynizQNXkudnrJKa0i0VwSVEqIzPlDcrB5xBI-RyNLTw8Xo3pZ3BhmMH4c9o8onYS0aTHp9bJA2epthLT3JOMCp1iNtT-YU0q_zDM1TQyo5y8x4cF43GIg" alt=""><figcaption></figcaption></figure>

Lastly, we have to specify the amount of disk space, or storage that this VM will have. For this, I would not go under 25GB, but know that more is better. If you plan to have other tools, such as Ghidra and Frida in your VM, I would make this number larger. Remember, whatever number you use now, you can not easily resize later, so erring on the side of larger is better. Once done, click **Next** to continue.

<figure><img src="https://lh4.googleusercontent.com/v2xn45QF8XUjfep2ZaELCMP4CVgvRup8pUu7M8VRF9N27xyym8ZbExPrk74x6TRrLr3NBLmP0k5t62cWoktrp8qHHkEvTAxa9izQG5rFcyIvBUDp1Dd8JHdCuGfAx8aEy9g8X7UwI9TXtEZhjpCY3XzouObZoa2WItEO_UP1jOVe2851jrbb0yblCRzgWQ" alt=""><figcaption></figcaption></figure>

Finally, click **Finish** on the summary page to finish initializing your VM.

Congrats! You have just created your first Linux VM and are one step closer to becoming the next generation of security professionals.

Now, let's boot up the system and let the unattended installation do its thing. To do this click your newly created VM and click start. This will prompt you with a message saying "Powering VM up...". Don't touch the machine and just let it do its thing. When it is done, you will be greeted with a login screen where you can enter your username and password, which you set earlier in the installation. If everything went correctly, you will have officially set up your first Ubuntu Linux VM and are ready to start your RE journey.

<figure><img src="https://lh5.googleusercontent.com/yMQCsjA_n3ldbxGQ10zvqehVr3t-gt6Do9Wb42LH6C--9s1-YLYNLqZEUETaBeGYmNDDIEBpFal34Pot87CmkRp-I-JKg8Cv3A5KNpK-c7D-FOoHS0LHvih3mqMzudDZLk-gHa9qGPlx_8y0zPJFTNasgTKvU328wpsCkNiaVKJLUFoPmIMM263RpYhCUQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/8Bv7SVl_70yAr-eWtIJAlZ7Z5ca4bIou3VLccqtzr0MSP8b6bT1__nexfSFxY6QFVNb2QUpUnS-yo7orX_L3WbKUNDfvtnLjbyWwNTfXwD-wGkF6mlavfn7MvQDEgXEcGeW6vjs-ovzdjy2hqVj6bprpMgkwyxkzNvcMoapOvD2H7o7ykdl-Y42eJgUE-Q" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/nA19wYmycgKl-Yppd_22k1_FJ2lWnpcmsxW7o9ct_VhhHnl1Zx4n9BpFryBzTyVdYbghPuLK2whcsSVGI_sF12lrBrJyyZrbqXuDfOrxWW7HwgCYG8IjrrVDgolfJIfANT5WACQUnaidOdbUMf7IQVGPNaBizaEE8wadq4P3rt45rYQnffUq0pb6icHgaA" alt=""><figcaption></figcaption></figure>

In the next section, we will talk about installing VIM, a basic command line text editor in Linux.
