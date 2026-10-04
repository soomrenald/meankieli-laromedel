# Dictionary data and bundled components

The owner supplied the APKs and wordlist for this study repository. They are distributed byte-for-byte as supplied. The dictionary data attribution below applies to the identified lexical data; it does not assign a blanket license to the course documents, recordings, or application code.

## Meänkieli–Swedish dictionary data

Source: **Meänkieli-svensk-meänkieli ordbok**, Institutet för språk och folkminnen (ISOF). The dictionary project credits Meän Akateemi–Academia Tornedaliensis and technical assistance from Giellatekno, UiT. The dataset catalogue credits Elina Kangas and Svenska Tornedalingars Riksförbund–Tornionlaaksolaiset.

- [Official dictionary and project credits](https://xn--sprk-soa.isof.se/me%C3%A4nkieli/)
- [Official data directory](https://sprakresurser.isof.se/meankieli/)
- [Official metadata: CC-0](https://sprakresurser.isof.se/meankieli/metadata.xml)
- [Swedish National Data Service catalogue: CC0 1.0](https://researchdata.se/en/catalogue/dataset/2022-241-1)
- [CC0 1.0 terms](https://creativecommons.org/publicdomain/zero/1.0/legalcode)

Both APKs embed the same `assets/fit-swe-lr-trie.xml`: 32,507 entries and 42,526 headword/translation pairs. Every pair matches the official CC0 XML data when translations within one source sense are joined with comma-space, Unicode is normalized to NFC, whitespace is collapsed, and comma spacing is normalized. One literal pair differs only by a space before a comma (`merkilinen`); six raw headword spellings use decomposed diacritics. No dictionary text was changed in the APKs.

The embedded XML also matches the owner's [public source file](https://github.com/soomrenald/meankielii_dictionary_wiki/blob/1f160e4d21650fb6cebc06481330fa174cb72714/fit-swe-lr-trie.xml) exactly after CRLF/LF normalization. The original keyboard ZIP has 14,575 Gboard-format words, all found among the official dictionary's headwords. [dictionary-provenance.json](dictionary-provenance.json) records comparison methods, counts, source-file hashes, and original APK hashes.

## Owner-created vocabulary workbooks

The owner confirmed on 2026-10-04 that they created both [Sanakirja.xlsx](../Me%C3%A4nkieli/Docs/Sanakirja.xlsx) and [meänkieli frequency list.xlsx](../Me%C3%A4nkieli/Docs/me%C3%A4nkieli%20frequency%20list.xlsx). Both are published byte-for-byte as supplied in the original archive. [spreadsheet-provenance.json](spreadsheet-provenance.json) records their hashes and readability checks. No additional license has been assigned to the workbooks; the CC0 attribution above applies to the identified dictionary data.

## Bundled Android libraries

The APK metadata identifies AndroidX (including Jetpack Compose), Google Material Components, and Kotlin coroutines. The official projects publish these components under Apache License 2.0. Copies of their published license texts accompany the APKs here:

| Component | Included license | Official source |
| --- | --- | --- |
| AndroidX / Jetpack Compose | [License](licenses/androidx-LICENSE.txt) | [AndroidX](https://github.com/androidx/androidx/blob/androidx-main/LICENSE.txt) |
| Kotlin runtime | [License](licenses/kotlin-LICENSE.txt) | [JetBrains Kotlin](https://github.com/JetBrains/kotlin/blob/master/license/LICENSE.txt) |
| Kotlin coroutines | [License](licenses/kotlinx-coroutines-LICENSE.txt) | [Kotlin coroutines](https://github.com/Kotlin/kotlinx.coroutines/blob/master/LICENSE.txt) |
| Material Components for Android | [License](licenses/material-components-LICENSE.txt) | [Material Components](https://github.com/material-components/material-components-android/blob/master/LICENSE) |

[apk-components.json](apk-components.json) preserves the versions declared in each supplied APK's `META-INF` entries. This is an observed metadata inventory; it is not a reconstructed build dependency graph. Existing files and metadata inside the APKs are unchanged.
