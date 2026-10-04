# Meänkieli self-study materials

Läromedel i meänkieli för självstudier.

This collection brings together dialogue recordings, grammar examples, source documents, and local study apps. Start by reading a folder's dialogue text, then practice its recording in the browser audio player.

The recordings, Word documents, folder READMEs, and apps are organized below. The [app guide](Me%C3%A4nkieli/Apps/README.md) includes five actual Android screenshots supplied by the owner, with instructions checked against the packaged app code. The dictionary APKs and keyboard wordlist are available with documented CC0 data attribution. Native Android features have not been independently tested in this execution environment.

## Start studying

1. [Choose a dialogue or grammar folder](Me%C3%A4nkieli/Audio%20files%20for%20android%20app/README.md). Each folder displays its source text and links to the original document.
2. Download a recording, then [download the web audio player](Me%C3%A4nkieli/Apps/Audio_player_web_version.html) and open the HTML file locally.
3. Follow the [screen-by-screen app guide](Me%C3%A4nkieli/Apps/README.md): load audio, choose a detected region, slow it down, and replay a waveform snippet.

The [app guide](Me%C3%A4nkieli/Apps/README.md) explains the controls, study workflow, and current test coverage.

## App screenshots

<p>
<a href="Me%C3%A4nkieli/Apps/README.md#android-dictionaries"><img src="docs/images/apps/4664.png" width="240" alt="Android dictionary results for aina"></a>
<a href="Me%C3%A4nkieli/Apps/README.md#playback-and-navigation"><img src="docs/images/apps/4665.png" width="240" alt="Android audio playback with a red position line"></a>
</p>

*Dictionary search and audio playback, supplied by the owner. [See all five screens and their controls](Me%C3%A4nkieli/Apps/README.md), including settings, snippet playback, recording, and how to repair a split utterance with **Add next**.*

## Repository structure

```text
README.md
docs/
  MEDIA.md
  IMPORT.md
  archive-manifest.json
  transcript-alignment.json
  DATA_SOURCES.md
  APP_VERIFICATION.md
  images/apps/              five original Android screenshots
Meänkieli/
  Apps/
    Audio_player_web_version.html
    dialogue-trainer-v0.3.apk
    Meankieli_dict_large.apk
    meankieli_dict_small.apk
    README.md
  Audio files for android app/
    set 1/                  20 everyday-dialogue recordings
    set 2/                  15 numbered conversations
    set 3/                  10 page-named recordings and replacement source
    grammatik/
      böjning/              12 case recordings
      prepositioner/        11 preposition recordings
      dåtid/                15 past-tense recordings, including an alternate take
  Completed audio files/
    Del 1/                  20 MP3/WAV recordings
    Del 2/                  15 processed WAV recordings
    Del 3/                   5 processed case WAV recordings
  Docs/                     Word originals, Markdown, and vocabulary XLSX files
  dictionary for chrome.zip  Gboard wordlist in its original archive
  Archive/                  earlier trainer APKs and replaced Set 3 document
```

[Browse all materials](Me%C3%A4nkieli/README.md) · [Documents](Me%C3%A4nkieli/Docs/README.md) · [Original recordings](Me%C3%A4nkieli/Completed%20audio%20files/README.md)

## Dialogue sources

The folder READMEs contain the original dialogue and grammar text rather than Drive shortcut placeholders. Each Meänkieli utterance appears beside its source Swedish translation in a table. Meänkieli, Swedish, English headings, spelling, diacritics, variants, and notes are retained. This is a presentation and organization pass, not a language correction pass.

Set 1, Set 2, and Böjning use matching sections of the course material. Prepositioner uses its included document, and Dåtid uses the seven verb-type perfect/imperfect tables. Set 3 uses the replacement supplied by the owner; the earlier three-dialogue file is archived. Page-to-paragraph boundaries and every audio line have not been independently verified. See [import and verification notes](docs/IMPORT.md).

## App coverage and remaining work

The owner supplied actual Android captures of dictionary search, audio playback, the loading/settings menu, snippet selection, and speech recording. The app guide explains all exposed controls, including repeatable **Add next** repairs and their reset behavior, using the code packaged in the supplied APKs. The screenshots’ device model and exact APK builds were not recorded. Independent Android installation, permission, and runtime checks remain unverified; [local emulator diagnostics](docs/ANDROID_TESTING.md) record the earlier failure before boot. The browser player ran with an original recording in desktop Chromium. Both dictionary APKs and the keyboard wordlist are available from the app guide, with [source attribution and license evidence](docs/DATA_SOURCES.md). Both [owner-created vocabulary spreadsheets](Me%C3%A4nkieli/Docs/README.md#owner-created-vocabulary-workbooks) are available unchanged, with their original sheet names and cell contents.

The original 436.6 MiB Drive ZIP stays outside Git. Large recording originals are preserved without transcoding; see [media storage notes](docs/MEDIA.md). No Git LFS or account billing settings were enabled.
