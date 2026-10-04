# Native Android verification status

Five actual Android screenshots supplied by the owner are now documented in the [app guide](../Me%C3%A4nkieli/Apps/README.md). [Screen coverage and code references](APP_VERIFICATION.md) record their original bytes and the source of the instructions. The screenshot device model and exact APK builds were not recorded.

The earlier local emulator attempt remains blocked: the process exited with a segmentation fault before Android finished booting or offered a usable ADB connection. No APK was installed or run and no native screenshot was captured by this execution environment. The owner-provided images are separate evidence; browser-player and browser-harness images remain removed from the current files.

## Prepared setup and attempts

The official SDK's **Pixel 9 Pro** profile defines a 1280 × 2856 display with an `xxhdpi` density bucket. The test AVD uses that geometry and 480 logical dpi, with 2 GiB RAM and two virtual CPU cores. This simulates the requested screen layout; it does not reproduce every physical Pixel 9 Pro hardware capability. [Google's specifications](https://support.google.com/pixelphone/answer/7158570?hl=en) also list the 1280 × 2856 display.

Google's Android 14 / API 34 Google APIs x86_64 system image, revision 14, passed its published SHA-1 check. Emulator 37.2.12 passed its published SHA-1 check. The official archived stable 35.6.11 fallback passed Google's SHA-256 check. [android-verification.json](android-verification.json) records versions, package URLs, checksums, and test modes. [Google's emulator archive instructions](https://developer.android.com/studio/emulator_archive) describe installing a selected version manually.

The current host reports existing KVM access as usable. Startup was attempted with KVM and software CPU modes, SwiftShader and GPU-off modes, Vulkan disabled, explicit local temporary/runtime paths, and a hidden Qt display. Both emulator versions failed before Android boot. The display initialization logs confirm 1280 × 2856 and 480 dpi. These observations do not establish the crash's cause.

The prepared AVD and local launch helper remain in the ignored `.local-runtime/android/` directory. Raw logs, virtual-device data, SDK downloads, and runtime authentication files are kept out of Git. No physical phone, account sign-in, microphone capture, host group membership, kernel settings, or security settings were used or changed. Existing SDK license terms were reused; no new material license agreement was accepted.

## APK requirements from their manifests

| Supplied APK | Package ID | Declared version | Minimum Android |
| --- | --- | --- | --- |
| dialogue-trainer-v0.3.apk | com.meankieli.audioplayer | 1.0 / code 1 | Android 8.0 / API 26 |
| Meankieli_dict_large.apk | com.meankieli.dictionary | 1.0 / code 1 | Android 7.0 / API 24 |
| meankieli_dict_small.apk | com.meankieli.dictionary | 1.15 / code 5 | Android 7.0 / API 24 |

The dictionaries share a package ID. Choose one variant on a device; they are not two independently named installations. These are manifest observations, not successful installation tests.

## Remaining independent runtime checks

The owner’s screenshots cover dictionary results and the trainer’s loaded-region/playback, menu, snippet-selection, and active-recording states. The guide now documents the controls from these pixels and the packaged code. Local emulator execution remains unverified, including APK installation, permission dialogs, file selection across Android versions, completed recording playback, and persistence of large-dictionary additions. No further emulator setup or compatibility trials were started for screenshot documentation.
