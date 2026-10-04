# App documentation evidence

The [app guide](../Me%C3%A4nkieli/Apps/README.md) combines five owner-supplied actual Android captures with inspected code packaged in the repository’s APKs. The images were visually inspected before captioning. They retain their original filenames, PNG bytes, 768 × 1713 resolution, and proportions. Width attributes change README display size only. [app-screenshots.json](app-screenshots.json) records original hashes and coverage.

## Screen coverage

| Original image | Visible state |
| --- | --- |
| [4664.png](images/apps/4664.png) | Dictionary query “aina,” one exact result, 45 partial results, word classes, translations, and inline examples. |
| [4665.png](images/apps/4665.png) | Essiv.m4a playback, region 4 of 22, red playback-position line, region controls, speed, and recording buttons. |
| [4666.png](images/apps/4666.png) | Open File(s), silence time/sensitivity, before/after padding, and Exit app menu. |
| [4667.png](images/apps/4667.png) | Blue snippet interval with adjustable edges and enabled Play Snippet; the still image shows a selection ready to play. |
| [4668.png](images/apps/4668.png) | Active speech recording, Stop recording, recording status, and disabled main playback/region controls. |

The owner identified the first image as the dictionary and the other four as the audio app. No device model or exact APK build was supplied. The dictionary screenshot’s Swedish labels correspond to labels in the small APK’s code, but the capture is not treated as binary-version verification or evidence of both editions. No browser or browser-harness images are used.

## Controls checked against packaged code

The current trainer’s `assets/meankieli_audio_file_player_android_ver.html` was read directly from [dialogue-trainer-v0.3.apk](../Me%C3%A4nkieli/Apps/dialogue-trainer-v0.3.apk). Its native `classes3.dex` was inspected for file, recording, permission, exit, and Back behavior. No app code was changed.

| Guide function | Code reference and confirmed behavior |
| --- | --- |
| File selection and file arrows | HTML file-input listener, `onAndroidFileListChanged`, `updateFileNav`; native `openFilePicker`, `openDocumentLauncher`, `loadAudioFileByIndex`, `loadNextFile`, `loadPreviousFile`: audio picker supports multiple files; navigation has end bounds. |
| Region selection/navigation | `renderRegions`, `setCurrentRegion`, Prev/Next listeners: list taps and navigation start playback; region selection clears the snippet. |
| Play, stop, red position line | `playCurrentRegion`, `stopAllPlayback`, Play listener, `drawWaveform`: restart from the region start, one-shot bounded playback, red line while source audio is playing. No loop control. |
| Speed/reset | `speedSlider` and `speedResetButton` listeners: 0.1×–1×, 1× reset, source/snippet playback uses `state.playbackSpeed`. Recorded-buffer playback uses the normal default rate. |
| Detection and padding | `computeRegions`, `reanalyzeIfLoaded`, `analyzeAudio`: relative RMS sensitivity with a minimum floor; silence duration and before/after padding; overlapping padded regions merge; slider changes rebuild regions and select region 1. |
| Add next | `addNextRegion`, `trimGapAndShiftRegions`: keeps the current index, removes the next list entry, shortens the unpadded gap to at most `CONCATENATED_SILENCE_SECONDS = 0.1`, shifts later times, clears the snippet, and allows repeated merging. Only the in-memory working audio changes. Reanalysis uses that working audio; reloading the source restores it. |
| Snippet selection/playback | `handlePointerStart/Move/End`, `getEdgeAtX`, `playSnippet`, `updateControls`: mouse/touch interval selection and edge adjustment; bounded playback at source speed; Play returns to the full region. |
| Speech recording/replay | Record/Play-recorded listeners, `loadRecordedAudioFromAndroid`, `playRecordedBuffer`, native `startNativeRecording`/`stopNativeRecording`: temporary cache recording is passed to the player and deleted; the completed take is available for in-app replay, with no persistent export UI. |
| Permissions and exit | Android manifest declares RECORD_AUDIO and audio/storage access. Native `requestPermissions` requests them; `exitApp` releases recording resources, deletes the temporary file, clears WebView cache/history, and removes the task. HTML `resetLoadedAudio` clears source/take state. |
| Android Back | Native `onBackPressed` uses WebView history if present, otherwise delegates to normal Android Back behavior. |

For the small dictionary, `classes.dex` contains the Swedish search placeholder, Clear Search icon, exact/partial headers, inline examples, query-change search callback, and XML-backed lookup. For the large dictionary, `classes6.dex` contains `DictionaryScreenKt` and `AddEntryDialogKt`; `classes3.dex` contains `DictionaryRepository.searchWord`, `addEntry`, and `saveToXml`. The large UI uses Search and Add Entry. All four add-entry fields are checked for nonblank values; additions are written to the app’s local XML copy. Card details are inline. A dedicated entry-copy function was not verified.

The [web player HTML](../Me%C3%A4nkieli/Apps/Audio_player_web_version.html) was inspected separately. It has one-file selection, region/list navigation, one-shot Play and snippet playback, a 0.25×–2× speed slider, silence-duration reanalysis, waveform selection/edges, and a frequency-spectrum panel. It does not expose the current trainer’s Add next, recording, adjustable sensitivity/padding, multi-file controls, or Exit app menu.

## Verification limits

Screenshots show visible app states; code inspection establishes the implemented control paths. They do not independently verify Android installation, permission dialogs, audio output quality, completed microphone playback, every Android version, or persistence of large-dictionary additions. [Local emulator diagnostics](ANDROID_TESTING.md) remain historical evidence of failure before Android boot. No new emulator trials were started.

Source dialogue/audio completeness limits, including Set 3 page-to-recording boundaries, remain in [import notes](IMPORT.md).
