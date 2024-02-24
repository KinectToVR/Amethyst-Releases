# Amethyst-Releases

### How do I install or update Amethyst?
[<img width="290px" src="https://get.microsoft.com/images/en-us%20light.svg">](https://www.microsoft.com/store/apps/9P7R8FGDDGDH)

**Scroll further down for manual instructions.**  

Amethyst is a Windows application for using various devices for body tracking in virtual reality. It can be [extended with user-made plugins](https://docs.k2vr.tech/en/dev/overview) to support any device you wish.

This is a rewrite from the ground up, it is *not* based on KinectToVR/K2EX. It is a whole new app that doesn't carry the legacy baggage of K2EX. We were able to fix numerous bugs and streamline the experience. We hope you will enjoy it. If you like what you see and you wish to support future development, you can throw money at us with the [<img style="display:inline; height:26px;" src="https://user-images.githubusercontent.com/8508676/189487326-eff20178-77a2-4ea4-9798-d389e53501e4.png">](https://opencollective.com/k2vr) button.
  (We won't force you, though every expense is currently out of pocket.)



<img alt="Amethyst General Tab" src="https://user-images.githubusercontent.com/50022719/230727989-84673a2e-ee90-45e8-9282-cbe9bd1f8697.png">
<details>
<summary><span style="font-weight:600;">More Screenshots</span></summary>
<img alt="Amethyst Settings Tab" src="https://user-images.githubusercontent.com/50022719/230728008-42181c96-67cf-4c54-b632-b0b8aafc478c.png"> 
<img alt="Amethyst Devices Tab" src="https://user-images.githubusercontent.com/50022719/230728027-3c758683-5df3-4cb5-b485-e93f3245e188.png">
<img alt="Amethyst Info Tab" src="https://user-images.githubusercontent.com/50022719/230728043-e3fda800-d4ac-46c8-aca7-e5ef02507d58.png"> 
<img alt="Amethyst Plugins Tab" src="https://user-images.githubusercontent.com/50022719/230728064-98f0f510-bc83-470a-a3af-e0f8ed5b67c1.png"> 
</details>

<details>
<summary><span style="font-weight:600;">Related Components</span></summary>
<img alt="Amethyst ExtFlip" src="https://user-images.githubusercontent.com/50022719/230728107-d65de3d3-5545-43bf-86b9-5d223af615f1.png">
<img alt="Amethyst Extra Trackers" src="https://user-images.githubusercontent.com/50022719/230728127-809e14a8-3077-4433-9726-509abd4f8900.png">
<img alt="Amethyst Tracking Output" src="https://user-images.githubusercontent.com/50022719/230728139-793302e3-c66f-4c2d-a333-dfe86cc6e591.png">
<img alt="Amethyst Store Sample" src="https://user-images.githubusercontent.com/50022719/230728147-a3e08d07-99ae-40e2-8994-67de31ebc1de.png">
</details>

<details>
<summary><span style="font-weight:600;">Extra/Fun Stuff</span></summary>
<img alt="Amethyst Help" src="https://user-images.githubusercontent.com/50022719/230728159-54110668-51b9-419f-9825-6e5296212267.png">
<img alt="Amethyst Freeze" src="https://user-images.githubusercontent.com/50022719/230728169-3e7b30d4-30cd-4595-a8a8-68c512edcf23.png">
</details>
</br>

## Manual setup

If the Microsoft Store isn't available for you, for some reason:
 - **Download 11835K2VRTeam.Amethyst_[...]_.Msix** from the [latest release](https://github.com/KinectToVR/Amethyst-Releases/releases/latest).
 - **You're good to go!** Just go through the setup and start playing!

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
- Run `amethyst-app:report` to collect all relevant files, just copy or drag-and-drop to share
- In case of SteamVR errors, log files from ```%AppData%/Amethyst/logs``` might be needed too
