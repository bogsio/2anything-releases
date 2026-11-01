# 2anything-releases
Public download hosting for 2anything (source is private). Binaries only.

## GPL sources

The app bundles two programs licensed under the GNU General Public License, which
it runs as separate executables: **FFmpeg** (`ffmpeg`, `ffprobe`, a static build
that links about thirty open-source libraries) and **Pandoc**. The GPL requires
whoever distributes those binaries to make their corresponding source available,
so this repository also hosts it.

Each set of component versions the app has shipped has a **pre-release** tagged
`ffmpeg-<version>-pandoc-<version>` (pre-release, so that `releases/latest` keeps
pointing at the app itself). It carries:

- the FFmpeg source tarball exactly as published by ffmpeg.org, with the
  project's detached signature
- a source tarball for every library statically linked into the FFmpeg build, at
  the version the build reports
- the Pandoc source tarball exactly as published on GitHub
- `SHA256SUMS` over every file, and `MANIFEST.tsv` listing each component, its
  version, file name, upstream URL and SHA-256 (also committed under `manifests/`)

The versions and the FFmpeg configure line are printed by the app itself with
`2anything --licenses`; match them against the pre-release tag.

**What is and is not here.** The FFmpeg binary is the macOS arm64 static build
published by [ffmpeg.martin-riedl.de](https://ffmpeg.martin-riedl.de/). That site
does not publish its build scripts, so the configure line printed by the app is
the build description we have; the sources here are the upstream releases of every
component it names. The x264 tarball is a snapshot of its `stable` branch (the
build reports `0.165.x`) taken when the pre-release was prepared. Pandoc's
statically linked Haskell libraries are listed in `COPYRIGHT` inside its tarball
and are available from [Hackage](https://hackage.haskell.org/); they are not
mirrored here.

**Written offer.** For three years from the date you received a copy of
2anything, we will provide the corresponding source for its GPL components to
anyone who asks, at no charge beyond the cost of the medium. Email
[support@2anything.app](mailto:support@2anything.app).
