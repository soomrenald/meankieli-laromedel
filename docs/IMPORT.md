# Import and verification notes

The initial Git checkout contained only the existing root README at commit `7c8febd`. Work was prepared on `docs/self-study-materials`; the original archive remains unchanged outside the checkout.

The ZIP contains 138 files, no duplicate member paths, no symlinks, and no absolute or traversal paths. Extraction refused collisions and checked resolved destinations before writing. Every member was read through ZIP CRC verification and recorded with its byte count and SHA-256 in [archive-manifest.json](archive-manifest.json).

The original Set 3 `Meankieli_ExtendedDialogues.docx` is now retained as `Meänkieli/Archive/Meankieli_ExtendedDialogues-original.docx`. Its former location contains the owner-supplied replacement. The replacement was materialized through Library, verified as a readable DOCX (24,560 bytes), and retained unchanged. It reports 13 pages in saved metadata; no actual document pagination render was completed. The folder README reproduces its entire text without inferred page boundaries.

Source mappings use archive filenames, source headings, and the owner's replacement instruction. All source Word files have readable Markdown companions. Set 1, Set 2, and Böjning display their corresponding course sections including Swedish translation blocks. Prepositioner, Dåtid, and Set 3 display their complete individual source documents. No dialogue text was invented or rewritten. Individual audio-to-text lines have not all been checked by listening.

The two differently named Vanheta imperfect recordings have different bytes and both remain. There are no independently named Abessiv or Ackusativ II recordings, although those topics occur in the source course material. The set 1 greeting uses `.mp4`; that particular recording format has not been tested in the apps.

Four real interface screenshots were visually checked. The unmodified web player decoded `3. Middag.m4a` as 1:17.833 and detected 18 regions at 740 ms. Region navigation, speed 0.75×, region playback, waveform selection, and snippet playback were exercised. The original trainer v0.3 HTML was run through a local browser file-selection harness: it detected 15 regions with default 740 ms, 4% sensitivity, and 500 ms padding, then 14 after Add next. Region navigation and speed reset were exercised. A browser instrumentation MutationObserver error occurred during harness inspection; the app HTML contains no MutationObserver reference and visible controls continued to work. Native Android file/recording/exit behavior, installation, archived app versions, and native dictionaries remain untested.

This checkpoint retains unresolved dictionary/vocabulary assets locally and omits their downloads. It does not infer licenses from similar filenames or apply a blanket license to unrelated source materials.
