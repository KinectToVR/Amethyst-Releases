# Amethyst-Releases
### **[<img src="https://user-images.githubusercontent.com/8508676/181382203-946594a8-64d4-4861-bad8-f1f2c02262b2.png">](#setup)**
This repository holds the published releases of Amethyst

<img alt="Amethyst General Tab" src="https://imgur.com/kR9JfPx.png">
<details>
<summary><span style="font-weight:600;">More Screenshots</span></summary>
<img alt="Amethyst Settings Tab" src="https://imgur.com/ZwbH9Td.png"> 
<img alt="Amethyst Devices Tab" src="https://imgur.com/EARzPls.png">
<img alt="Amethyst Info Tab" src="https://imgur.com/mUyJ8Id.png"> 
</details>

<details>
<summary><span style="font-weight:600;">Extra/Fun Stuff</span></summary>
<img alt="Amethyst ExtFlip" src="https://imgur.com/MSCx6IU.png">
<img alt="Amethyst Help" src="https://imgur.com/vFgDmMt.png">
</details>
</br>

## Setup
### Pre-requisites (You need these to run the app):
- Windows 20H2 or newer (+any win11 is fine)
- Install [VCRedist 2022](https://aka.ms/vs/17/release/vc_redist.x64.exe)

Releases older than `1.0.2.4` require a manual install of  
[.NET 6 Desktop Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-6.0.4-windows-x64-installer) and [Windows App SDK Runtime](https://docs.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads)

### Actually doing the thing:

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
