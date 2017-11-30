---
layout: default
title: Supported formats
weight: 3
---

When defining the formats that ExoPlayer supports, it's important to note that
"media formats" are in fact defined at multiple levels. From the lowest level to
the highest, these are:

* The format of the individual media samples (e.g., a frame of video or a frame
  of audio). We call these *sample formats*. Note that a typical video file will
  contain media in at least two sample formats; one for video (e.g., H.264) and
  one for audio (e.g., AAC).
* The format of the container that houses the media samples and associated
  metadata. We call these *container formats*. A media file has a single
  container format (e.g., MP4), which is commonly indicated by the file
  extension. Note that for some audio only formats (e.g., MP3), the sample and
  container formats may be the same.
* Adaptive streaming technologies such as DASH, SmoothStreaming and HLS. These
  are not media formats as such, however it's still necessary to define what
  level of support ExoPlayer provides.

The following sections define ExoPlayer's support at each level, from highest to
lowest. Support for standalone subtitle formats is also described at the bottom
of this page.

## Adaptive streaming ##

### DASH ###

ExoPlayer supports DASH with the FMP4, WebM and Matroska container formats.
Media streams must be demuxed, meaning that video, audio and text must be
defined in distinct AdaptationSet elements in the DASH manifest. The contained
audio and video sample formats must also be supported (see the
[sample formats](#sample-formats) section for details).

| Feature | Supported    | Comment              |
|---------|:------------:|:---------------------|
| **Containers** |||
| FMP4 | YES| Demuxed streams only |
| WebM | YES | Demuxed streams only |
| Matroska | YES | Demuxed streams only |
| MPEG-TS | NO | No support planned |
| **Closed&nbsp;captions/subtitles** |||
| TTML | YES | Raw, or embedded in FMP4 according to ISO/IEC 14496-30 |
| WebVTT | YES | Raw, or embedded in FMP4 according to ISO/IEC 14496-30 |
| CEA-608 | YES | Carried in SEI messages embedded in FMP4 video tracks |
| **Metadata** |||
| EMSG metadata | YES | Embedded in FMP4 |
| **Content protection** |||
| Widevine CENC | YES | API 19 and higher; "cenc" scheme only |
| PlayReady SL2000 | YES | Android TV only |

### SmoothStreaming ###

ExoPlayer supports SmoothStreaming with the FMP4 container format. Media streams
must be demuxed, meaning that video, audio and text must be defined in distinct
StreamIndex elements in the SmoothStreaming manifest. The contained audio and
video sample formats must also be supported (see the
[sample formats](#sample-formats) section for details).

| Feature | Supported    | Comment              |
|---------|:------------:|:---------------------|
| **Containers** |||
| FMP4 | YES | Demuxed streams only |
| **Closed&nbsp;captions/subtitles** |||
| TTML | YES | Embedded in FMP4 |
| **Content protection** |||
| PlayReady SL2000 | YES | Android TV only |

### HLS ###

ExoPlayer supports HLS with the MPEG-TS, ADTS and MP3 container formats. The
contained audio and video sample formats must also be supported (see the
[sample formats](#sample-formats) section for details). Note that we recommend
using DASH (or SmoothStreaming) rather than HLS where possible. You can read
about some of the benefits of DASH
[here](https://medium.com/google-exoplayer/test-8b62d50362ef#.dlz6npay4).

| Feature | Supported    | Comment              |
|---------|:------------:|:---------------------|
| **Containers** |||
| MPEG-TS | YES ||
| FMP4 | YES ||
| ADTS (AAC) | YES ||
| MP3 | YES ||
| **Closed&nbsp;captions/subtitles** |||
| CEA-608 | YES ||
| WebVTT | YES ||
| **Metadata** |||
| ID3 metadata | YES ||
| **Content protection** |||
| AES-128 | YES ||
| Sample AES-128 | NO ||
| Widevine | NO | Future support planned for API 24 and higher |

## Standalone container formats ##

Media files in the following container formats can be played directly by
ExoPlayer. The contained audio and video sample formats must also be supported
(see the [sample formats](#sample-formats) section for details).

| Container format | Supported    | Comment              |
|------------------|:------------:|:---------------------|
| MP4 | YES ||
| M4A | YES ||
| FMP4 | YES ||
| WebM| YES ||
| Matroska| YES ||
| MP3 | YES ||
| Ogg | YES | Containing Vorbis, Opus and Flac |
| WAV | YES ||
| MPEG-TS | YES | Not seekable* |
| MPEG-PS | YES | Not seekable* |
| FLV | YES | Not seekable* |
| ADTS (AAC) | YES | Not seekable* |
| Flac | YES | Using the [Flac extension][] only |

\* Seeking is unsupported because the container does not provide metadata (e.g.,
a sample index) to allow a media player to perform a seek in an efficient way.
If seeking is required, we suggest using a more appropriate container format.

## Sample formats ##

By default ExoPlayer uses Android's platform decoders. Hence the supported
sample formats depend on the underlying platform rather than on ExoPlayer.
Sample formats supported by Android devices are documented
[here](https://developer.android.com/guide/appendix/media-formats.html#core).
Note that individual devices may support additional formats beyond those listed.

In addition to using Android's platform decoders, ExoPlayer can also make use of
software decoder extensions. These must be manually built and included in
projects that wish to make use of them. We currently provide software decoder
extensions for
[VP9](https://github.com/google/ExoPlayer/tree/release-v2/extensions/vp9),
[Flac](https://github.com/google/ExoPlayer/tree/release-v2/extensions/flac),
[Opus](https://github.com/google/ExoPlayer/tree/release-v2/extensions/opus) and
[FFmpeg](https://github.com/google/ExoPlayer/tree/release-v2/extensions/ffmpeg).

### FFmpeg extension ###

The [FFmpeg extension][] supports decoding a variety of different audio sample
formats. You can choose which decoders to include by passing command line
arguments to FFmpeg's `configure` script:

| Sample format  | Argument(s) to `configure` |
|---------------:|----------------------------|
| Vorbis         | --enable-decoder=vorbis |
| Opus           | --enable-decoder=opus |
| FLAC           | --enable-decoder=flac |
| ALAC           | --enable-decoder=alac |
| MP1, MP2, MP3  | --enable-decoder=mp3 |
| AMR-NB         | --enable-decoder=amrnb |
| AMR-WB         | --enable-decoder=amrwb |
| AAC            | --enable-decoder=aac |
| AC-3           | --enable-decoder=ac3 |
| E-AC-3         | --enable-decoder=eac3 |
| DTS, DTS-HD    | --enable-decoder=dca |
| TrueHD         | --enable-decoder=mlp --enable-decoder=truehd |

See the extension's
[README.md](https://github.com/google/ExoPlayer/tree/release-v2/extensions/ffmpeg/README.md)
for an example command line to `configure`.

[Flac extension]: https://github.com/google/ExoPlayer/tree/release-v2/extensions/flac
[FFmpeg extension]: https://github.com/google/ExoPlayer/tree/release-v2/extensions/ffmpeg

## Standalone subtitle formats ##

ExoPlayer supports standalone subtitle files in a variety of formats. Subtitle
files can be side-loaded as described in the [Developer guide][].

| Container format | Supported    | Comment              |
|------------------|:------------:|:---------------------|
| WebVTT | YES ||
| TTML | YES ||
| SMPTE-TT | YES | Use `MimeType.APPLICATION_TTML`|
| SubRip | YES ||
| SubStationAlpha (SSA) | YES ||
| ASS | YES | Use `MimeType.TEXT_SSA` |

[Developer guide]: https://google.github.io/ExoPlayer/guide.html#side-loading-a-subtitle-file
