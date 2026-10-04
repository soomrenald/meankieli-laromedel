# Apps and how to use them

[Repository guide](../../README.md) · [Study recordings and text](../Audio%20files%20for%20android%20app/README.md)

## Web audio player

[Download the HTML file](Audio_player_web_version.html), then open the downloaded file in a current browser. GitHub's file view displays source rather than running the app. No build step is needed. The supplied HTML has no external script dependencies or remote upload endpoint; it reads selected audio locally using the browser audio APIs.

1. Choose **Audio file** and select a downloaded recording.
2. Wait for decoding and the **Detected sound regions** list. Select a region, or use **Previous** and **Next**.
3. Press **Play** to listen to the selected region. Adjust **Playback speed** from 0.25× to 2× for practice.
4. Adjust **Silence length threshold** (50–2,000 ms) if the divisions are unsuitable. Shorter silence thresholds tend to split more phrases; longer thresholds tend to group them.
5. Drag across the waveform to select part of the current region, adjust the selection edges, and press **Play Snippet**. The lower panel displays a spectrum.

The web player decoded `3. Middag.m4a` as 1:17.833 and detected 18 regions at the default 740 ms silence threshold. Region navigation, speed changes, region playback, waveform selection, and snippet playback were exercised in desktop Chromium. Other browsers and mobile platforms have not been tested here.

## Android dialogue trainer v0.3

[Download dialogue-trainer-v0.3.apk](dialogue-trainer-v0.3.apk) (5.56 MiB). Installation, Android file permissions, microphone recording, and native lifecycle behavior remain untested. On an Android device, use your normal approved APK installation process, then launch the app. A disposable emulator was prepared, but it crashed before Android boot; native APK installation remains unverified. The manifest requires Android 8.0 or later.

The intended APK workflow, based on the bundled interface and bridge calls, is to open **☰ → Open File(s)**, choose recordings, and practice selected regions. File arrows move between selected recordings; **Prev region**, **Play/Stop playing**, and **Next region** control the current phrase. **Add next** joins the next region into the current practice buffer. **Playback speed** runs from 0.1× to 1×, and **1x** restores normal speed. Drag the waveform to select a snippet. **Record** and **Play recorded** support pronunciation practice; their native microphone behavior has not been exercised.

The menu exposes file selection, silence time (50–2,000 ms), sensitivity (1–25%), padding before/after regions (0–2,000 ms), and **Exit app**. Packaged defaults are 740 ms, 4%, and 500 ms padding on either side. Use these settings to tune phrase boundaries, starting with a short recording.

**Actual Android screenshots pending:** the owner will supply native app captures. Both tested official emulator versions failed before Android boot. The prepared Pixel 9 Pro display profile is 1280 × 2856 at 480 logical dpi. See [setup evidence and remaining tests](../../docs/ANDROID_TESTING.md). Browser and browser-harness screenshots were removed at the owner's request. Preliminary bundled-interface tests are recorded in [verification notes](../../docs/IMPORT.md).

## Android dictionaries

[Download the large dictionary APK](https://raw.githubusercontent.com/soomrenald/meankieli-laromedel/main/Me%C3%A4nkieli/Apps/Meankieli_dict_large.apk) (22.18 MiB) and [download the small dictionary APK](https://raw.githubusercontent.com/soomrenald/meankieli-laromedel/main/Me%C3%A4nkieli/Apps/meankieli_dict_small.apk) (13.02 MiB) are native Android dictionary packages. Both bundle a Meänkieli–Swedish XML dictionary; the smaller package also includes SQLite/SQL assets. Its packaged strings include “Sök svenska eller meänkieli...”, indicating a bilingual search field. UI screens, installation steps specific to Android versions, and device behavior have not been verified, and no screenshots have been fabricated.

The APKs are unchanged originals. Their lexical data matches the official ISOF CC0 dictionary; see [source attribution, licenses, and hash evidence](../../docs/DATA_SOURCES.md). Both manifests require Android 7.0 or later and use the same package ID, so choose one dictionary variant rather than expecting separate installations. Actual Android screenshots are awaiting the owner’s captures. Screen-specific behavior remains unverified; see [Android verification status](../../docs/ANDROID_TESTING.md).

## Keyboard wordlist archive

[Download the original keyboard wordlist ZIP](../dictionary%20for%20chrome.zip). It contains only `dictionary.txt`, not a Chrome extension. Its header identifies the **Gboard Dictionary version 1** format, with shortcut/word/language-tag columns and 14,575 data rows. It should be treated as a keyboard dictionary import file, despite its original filename. A Gboard import was not attempted, and no Chrome installation workflow is claimed. All 14,575 words match the official ISOF CC0 dictionary headwords; see [data attribution](../../docs/DATA_SOURCES.md).
