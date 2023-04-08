# Amethyst-Releases
## Want to try out Amethyst?
This branch only holds the localization resource strings.  
For how to install & FAQ, please [check out the main branch](https://github.com/KinectToVR/Amethyst-Releases/tree/main).

## Reports: 
- <ins>Record the issue</ins> (or at least describe it as well as you can)
- Send us the log files from ```%AppData%/Amethyst/logs```

## Source:
In the current app's state, I've decided to hide the source until the app comes finished.<br>
If you really want it for some reason though, please write to us on the K2VR discord.

# Localizing Amethyst
## Introduction
This page will help you understand how to localize (translate text resource files for):
- Amethyst (Desktop App)
- Amethyst's Crash Handler
- Official Amethyst Plugins

All resources are combined into a single JSON file with keys and values.  
When editing multiline keys, remember that newline inside the string is a `\n`.  
(The same goes for tabs: `\t`, you'll get used to it... maybe. Or just use a GUI)  

> **Important!** If you see a space at the start/end of a string, please keep it there!

## Preparations
In the folder you have Amethyst installed (where the `Amethyst.exe` is)  
please find a folder named `Assets` and then inside it, a one named `Strings`.  
Inside that folder, you'll find all the current language resources:
- `**.json` - a single translation file (like `en.json`, `de.json`...)
- `locales.json` - enumeration of the currently availble languages

> Note: Each device has the same file tree inside its root path.  
> For devices' strings, look in in `[device]/resources/Strings/`

> As you may have noticed already, the file tree in this repo matches  
> Amethyst's file string tree! It may take a while to get used to, though.

To get started, copy-paste `en.json` and rename it to your language, e.g. `ja.json`.  
Get language code by cropping its [`LCID` tag](https://docs.microsoft.com/en-us/openspecs/office_standards/ms-oe376/6c085406-a698-4e12-9d4d-c3b0ee3dbc4a) before `-`, e.g. Czech `cs-CZ` → `cs`.  
The new language would appear in Amethyst as `ja`, edit the `locales.json` file to fix it:

<table>
<tr>
<th>
Before
</th>
<th>
After
</th>
</tr>

<tr style="vertical-align:top">
<td>

```jsonc
/* English & others */
"en": {
    "en": "English",
    "fr": "French",
    "de": "German",
    "ru": "Russian"
},
...
```
</td>
<td>

```jsonc
/* English & others */
"en": {
    "en": "English",
    "fr": "French",
    "de": "German",
    "ru": "Russian",
    "ja": "Japanese" // Add to each
},
...

/* Your langauge */
"ja": {
    "en": "英語",
    "fr": "フランス語",
    "de": "ドイツ語",
    "ru": "ロシア語",
    "ja": "日本語"
}
```
</td>
</tr>
</table>

## Localization
Now that you've added your language to the global enumeration, you can start localizing.  
Replace the resource string in each key with the translated one. (the one on the right)  

> **Don't translate keys!** (The ones on the left, with many `/` (slash) characters inside them)  
  
Sample localization before/after:
```jsonc
/* ja.json - not translated */
...
"/GeneralPage/Buttons/Save": "Save",
...
```

```jsonc
/* ja.json - translated */
...
"/GeneralPage/Buttons/Save": "保存",
...
```

## Hot reload / Live preview
Each time you make changes (e.g. save) your translation file, Amethyst will automatically  
reload it and apply the pending changes to the user interface. (it may blink or lag a little)  
  
This allows for adding, editing and fixing your resources live - while Amethyst is running.  
Note the same goes for all devices loaded by Amethyst, and the Amethyst Installer itself.

# Localization FAQ

<details><summary><b>Is using machine translation okay?</b></summary>
To the limit that you can be 100% confident what you wrote is proper, <br>
you are allowed to use services like DeepL or Google Translate to HELP you. <br>
Not to write the whole thing. <br>
</details>
<br>

<details><summary><b>I want to see how it will look in the app!</b></summary>
As described <a href="https://github.com/KinectToVR/Amethyst-Releases/tree/strings#hot-reload--live-preview">here</a>, you can add, edit and preview your changes on runtime.
</details>
<br>

<details><summary><b>What about a CLA? How is that gonna work?</b></summary>
I would like to hear everyone's voices on this. <br>
You will be credited in the app's info page for your localization work.<br>
Though, we're not gonna write which language have you Amethyst translated into.<br>
Everything you publish to Amethyst will be licensed under GPLv3,<br>
unless an agreement is made between parties for partial licenses.
</details>
<br>

<details><summary><b>How do I submit work?</b></summary>
You have a few ways available to do that, actually:
<ul>
  <li>Open a pull request on <a href="https://github.com/KinectToVR/Amethyst-Releases/tree/strings">this branch</a>, adding your changes</li>
  <li><a href="https://github.com/KinectToVR/Amethyst-Releases/discussions">Open a discussion</a>, attaching your changed files</li>
  <li>Write to us on <a href="https://discord.gg/YBQCRDG">our Discord server</a> (or to me, directly)</li>
</ul>
</details>
<br>

<details><summary><b>What about future features and additions?</b></summary>
You're welcome to update your translations in the future, <br>
it would be super appreciated, actually! <br>
Either to fix errors or support new features.
</details>
<br>

<details><summary><b>Why not Weblate/Crodwin/...?</b></summary>
Actually, we're on our way to setting up a custom server to handle the API.<br>
When it's finished, there's a high chance that we'll host our Weblate on it.<br>
<br>
Until then, if editing pure JSON is disturbing for you, you can use a <a href="https://codebeautify.org/online-json-editor">web editor</a>.
</details>
