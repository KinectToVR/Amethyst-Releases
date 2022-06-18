# Amethyst-Releases
This repository holds the published releases of Amethyst

## Setup
### Pre-requisites (You need these to run the app):
- Install [VCRedist 2022](https://aka.ms/vs/17/release/vc_redist.x64.exe)
- Install [.NET 6 Desktop](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-6.0.4-windows-x64-installer)
- Install the latest [Windows App SDK Runtime](https://docs.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads)

### Actually doing the thing:
- **Turn off the K2EX/KinectToVR driver** in SteamVR add-ons  
  *If you don't do this, when setting up Amethyst's driver, SteamVR will crash on launch, blocking your access to the add-ons list, and you would need to edit `%localappdata%\openvr\openvrpaths.vrpath` by hand to remove the KinectToVR driver.*  
    
  ```
  This happens because glog (the logging library used in the K2EX driver and in the Amethyst driver alike)
  gets loaded into the OpenVR assembly, but it can only be loaded once. So when the K2EX driver tries to
  load after Amethyst's. Everything explodes.
  
  Considering this, if you rename the name entry in the vrdrivermanifest for the K2EX driver so it's
  alphabetically before Amethyst, like `0kinecttovr` then Amethyst will load second and take over the
  existing glog instance.
  ```
 - Download the ZIP from the [latest release](https://github.com/KinectToVR/Amethyst-Releases/releases/latest).
 - Create a new folder, e.g. `C:\Amethyst`
 - Extract the contents of the release ZIP into that new folder.  
   In the case of the example folder, you would end up with `C:\Amethyst\Amethyst.exe`
 - Once Amethyst is launched, Click re-register SteamVR driver and follow the prompts.
 
### It's unsupported but please help me anyway!!!
Before asking for help with unsupported beta release software, try these:  
#### The app doesn't start after updating it.
**Update the Windows App SDK Runtime** the app is built against the latest version (except in cases of build failure) You can always refer to the release "changelog" to know which version is used.

#### My SteamVR gives me Error 203 and won't start no matter what I do.
You have the Amethyst and K2EX drivers **enabled at the same time**. They use the same logging library and conflict with each other on startup, causing the entirety of the SteamVR backend to crash.  
Close SteamVR, then **either delete or edit** `%localappdata%\openvr\openvrpaths.vrpath` if your file says null in it after you edited it, go learn JSON, and WTF are you doing on GitHub????

#### I have some other unrelated issue.
Unless you're actually braindead, you may possibly have run into a bug, reporting those is important to building a stable application for release. See just below on how to report bugs.

### Reports: 
- __This is still very WIP__, things will be broken and fixed on daily basis.
- Go to discord and post log files from ```%AppData%/KinectToVR/logs```

### Source:
In the current app's state, I've decided to hide the source until the app comes finished.<br>
If you really want it for some reason though, please write to us on the KinectToVR discord.
