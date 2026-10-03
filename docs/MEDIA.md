# Media storage

The owner selected regular Git for this initial import to preserve recording filenames and folder navigation. Original recordings are kept unchanged. The supplied ZIP is retained outside the Git checkout and is not committed.

The archive contains 1,460,361,090 expanded bytes. Its largest file is `Meänkieli/Completed audio files/Del 2/Konv2-processed.wav`: 83,346,774 bytes (79.49 MiB). Twelve originals exceed 50 MiB, and none exceed 100 MiB.

[GitHub's file-size guidance](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github) warns above 50 MiB and blocks files above 100 MiB. It recommends small repositories, ideally below 1 GB. [Repository limits](https://docs.github.com/en/repositories/creating-and-managing-repositories/repository-limits) enforce a 2 GB push limit. The compressed Git pack must be checked before uploading.

Keep these binary originals stable. Avoid repeated replacements in Git history. If frequent revisions make the repository too large, release assets can preserve originals with download links from the same study folders. GitHub's large-file guide recommends releases for distributing large binaries and does not limit total release storage or bandwidth, though individual assets have limits.

Git LFS is an alternative that preserves file paths but requires client support and owner storage/download allowances. [Current LFS billing guidance](https://docs.github.com/en/billing/concepts/product-billing/git-lfs) lists 10 GiB each for Free/Pro storage and bandwidth; existing account usage was not inspected. Downloads count toward the owner's allowance, and overages may block access or incur charges depending on account settings. No LFS setup, paid storage, or billing changes were made.
