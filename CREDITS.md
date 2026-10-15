# Credits and provenance

## Original work

[pstack](https://github.com/cursor/plugins/tree/main/pstack) was created by **Lauren Tan ([poteto](https://github.com/poteto))** and is distributed under the [MIT license](https://github.com/cursor/plugins/blob/e5136d82418d2db3165ea1050d17577cd618cc05/pstack/LICENSE).

This collection is an unofficial, independent adaptation. It is not endorsed by or affiliated with the original author or the upstream repository's owner. The original copyright and license notices are retained in the adapted skill directories and the root license.

The public comparison baseline is upstream version **0.15.25**, commit [`e5136d82418d2db3165ea1050d17577cd618cc05`](https://github.com/cursor/plugins/tree/e5136d82418d2db3165ea1050d17577cd618cc05/pstack). Individual skills preserve their own `metadata.upstream` and `metadata.upstream-commit`, which identify the source used for that adaptation. A later reviewed-through commit is recorded separately from the adaptation source.

## Portable adaptation

Maintained by [MatiasFrangolini](https://github.com/MatiasFrangolini).

The adaptations remove mandatory editor APIs and fixed model/effort defaults, add capability discovery and honest fallbacks, make arena/swarm explicit-only, and retain authorization and evidence boundaries. `pstack-update` is locally authored for selective maintenance; it has no assumed upstream counterpart.

The source-to-adaptation table and excluded capabilities are documented in [README.md](README.md). The public release baseline contains only source catalog data and fingerprints of the distributed files. Per-installation review history, personal policy, transcripts, machine paths, and private project data are not part of the release.

## Optional installer

NPX installation uses the separate, open-source [skills CLI](https://github.com/vercel-labs/skills). The library's core instructions do not depend on that installer or its vendor. It is not copied or vendored here.
