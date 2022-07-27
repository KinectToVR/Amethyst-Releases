# Amethyst-Releases
### **[<img src="https://user-images.githubusercontent.com/8508676/181382203-946594a8-64d4-4861-bad8-f1f2c02262b2.png">](#setup)**
This repository holds the published releases of Amethyst
<img alt="Amethyst General Tab" src="https://imgur.com/rsotr0K.png">
<details>
<summary><span style="font-weight:600;">More Screenshots</span></summary>
<img alt="Amethyst Settings Tab" src="https://imgur.com/iyyLi5L.png"> 
<img alt="Amethyst Devices Tab" src="https://imgur.com/GntYVBe.png">
<img alt="Amethyst Settings Tab" src="https://imgur.com/OGyK2ln.png"> 
</details>

<details>
<summary><span style="font-weight:600;">Extra/Fun Stuff</span></summary>
<img alt="Amethyst ExtFlip" src="https://imgur.com/qsnB2hO.png">
<img alt="Amethyst Okashi Tab" src="https://imgur.com/Mi7Ahw3.png">
</details>
</br>

## Setup
### Pre-requisites (You need these to run the app):
- Install [VCRedist 2022](https://aka.ms/vs/17/release/vc_redist.x64.exe)

Releases older than `1.0.2.4` require a manual install of  
[.NET 6 Desktop Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-6.0.4-windows-x64-installer) and [Windows App SDK Runtime](https://docs.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads)

### Actually doing the thing:

 - **Turn off the K2EX/KinectToVR driver** in SteamVR add-ons  
 - ![ezgif com-gif-maker (4)](https://user-images.githubusercontent.com/8508676/181381168-62bf00e4-5a2e-46c7-8970-cf841793fa56.gif)  
  If you don't do this, SteamVR will crash on launch, blocking your access to the add-ons list, and you would need to edit `%localappdata%\openvr\openvrpaths.vrpath` by hand to remove the KinectToVR driver.  
  <details>
  <summary><span style="font-weight:600;">If you care to know why</span></summary>
  This happens because glog (the logging library used in the K2EX driver and in the Amethyst driver alike)
  gets loaded into the OpenVR assembly, but it can only be loaded once. So when the K2EX driver tries to
  load after Amethyst's. Everything explodes.
  
  Considering this, if you rename the name entry in the vrdrivermanifest for the K2EX driver so it's
  alphabetically before Amethyst, like `0kinecttovr` then Amethyst will load second and take over the
  existing glog instance.
 </details>
 
 - **Download Amethyst-Release-XXXXXX.zip** from the [latest release](https://github.com/KinectToVR/Amethyst-Releases/releases/latest).
 - **Create a new folder**, e.g. `C:\Amethyst`
 - **Extract the ZIP** into that new folder.  
   *In the case of the example folder, you would end up with `C:\Amethyst\Amethyst.exe`*
 - Once Amethyst is launched, Click re-register SteamVR driver and follow the prompts.
 -  ![ezgif com-gif-maker(7)](https://user-images.githubusercontent.com/8508676/181381958-98f913be-e7f7-461a-9c52-d642c9090a65.gif)

### It's unsupported but please help me anyway!!!

#### My SteamVR gives me Error 203 and won't start no matter what I do.
You have the Amethyst and K2EX drivers **enabled at the same time**.  
They use the same logging library and conflict with each other on startup, causing the entirety of the SteamVR backend to crash.  
Close SteamVR, then **either delete or edit** `%localappdata%\openvr\openvrpaths.vrpath`  
if your file says null in it after you edited it, go learn JSON, and WTF are you doing on GitHub????

#### I have some other unrelated issue.
Unless you're actually braindead, you may possibly have run into a bug,  
reporting those is important to building a stable application for release. 
See just below on how to report bugs.

### Reports: 
- <ins>Record the issue</ins> (or at least describe it as well as you can)
- Send us the log files from ```%AppData%/Amethyst/logs```

### Source:
In the current app's state, I've decided to hide the source until the app comes finished.<br>
If you really want it for some reason though, please write to us on the K2VR discord.
