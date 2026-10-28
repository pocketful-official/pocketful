# Third-party software

Pocketful uses the projects below. Each keeps its own licence, which applies to that
project and is not changed by Pocketful's licence. The portable app has the full licence
texts in its `licences` folder.

## Inside the portable app (Pocketful.exe)

| Project | Used for | Licence | Copyright |
|---------|----------|---------|-----------|
| [Python](https://www.python.org) 3.12, with OpenSSL, libffi, SQLite, bzip2, xz, zlib, Expat and mpdecimal | Runs the app | PSF-2.0; OpenSSL Apache-2.0; others MIT/BSD/public domain (see `licences/Python-LICENSE.txt`) | Copyright (c) 2001 Python Software Foundation |
| [FFmpeg](https://ffmpeg.org) n8.1.3, LGPL build from [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) | Converting and decoding audio | LGPL-3.0-or-later (unmodified; built with `--enable-version3`, without `--enable-gpl`). It includes other libraries under their own licences; see BtbN's build scripts | the FFmpeg developers |
| [Deno](https://deno.com) | Used by yt-dlp for YouTube | MIT; includes V8 (BSD-3-Clause) | Copyright 2018-2026 the Deno authors; Copyright 2014 the V8 project authors |
| [yt-dlp](https://github.com/yt-dlp/yt-dlp) | Reading and downloading audio from YouTube Music | Unlicense | – |
| [yt-dlp-ejs](https://github.com/yt-dlp/ejs) | Used by yt-dlp for YouTube | Unlicense; includes meriyah 6.1.4 (ISC) and astring 1.9.0 (MIT) | meriyah: Copyright (c) 2019 and later, KFlash and others; astring: Copyright (c) 2015, David Bonnet |
| [ytmusicapi](https://github.com/sigma67/ytmusicapi) | Searching YouTube Music | MIT | Copyright (c) 2026 sigma67 |
| [requests](https://github.com/psf/requests) | HTTP requests | Apache-2.0 | NOTICE: "Requests. Copyright 2019 Kenneth Reitz" |
| [urllib3](https://github.com/urllib3/urllib3) | HTTP | MIT | Copyright (c) 2008-2020 Andrey Petrov and contributors |
| [charset-normalizer](https://github.com/jawah/charset_normalizer) | HTTP | MIT | Copyright (c) 2025 TAHRI Ahmed R. |
| [idna](https://github.com/kjd/idna) | HTTP | BSD-3-Clause | Copyright (c) 2013-2026, Kim Davies and contributors |
| [certifi](https://github.com/certifi/python-certifi) | HTTPS certificates | MPL-2.0 (unmodified; source at the link) | – |
| [Brotli](https://github.com/google/brotli) | HTTP compression | MIT | Copyright (c) 2009, 2010, 2013-2016 by the Brotli Authors |
| [websockets](https://github.com/python-websockets/websockets) | Used by yt-dlp | BSD-3-Clause | Copyright (c) Aymeric Augustin and contributors |
| [pycryptodomex](https://github.com/Legrandin/pycryptodome) | Used by yt-dlp | BSD-2-Clause and public domain | the respective authors |
| [segno](https://github.com/heuer/segno) | QR codes (Share Pocketful) | BSD-3-Clause | Copyright (c) 2016 - 2024 -- Lars Heuer |
| [pywebview](https://github.com/r0x0r/pywebview) | The app window | BSD-3-Clause | Copyright (c) 2014-2017, Roman Sirokov |
| Microsoft WebView2 SDK (`Microsoft.Web.WebView2.*.dll`, `WebView2Loader.dll`, shipped with pywebview) | The app window | BSD-3-Clause | Copyright (C) Microsoft Corporation |
| [bottle](https://github.com/bottlepy/bottle) | Used by pywebview | MIT | Copyright (c) 2009-2024, Marcel Hellkamp |
| [proxy_tools](https://pypi.org/project/proxy_tools/) | Used by pywebview | MIT | Jonathan Tushman |
| [pythonnet](https://github.com/pythonnet/pythonnet) | Used by pywebview on Windows | MIT | Copyright (c) 2006-2021 the contributors of the Python.NET project |
| [clr-loader](https://github.com/pythonnet/clr-loader) | Used by pythonnet | MIT | Copyright (c) 2019-2026 Benedikt Reinartz |
| [cffi](https://github.com/python-cffi/cffi) / [pycparser](https://github.com/eliben/pycparser) | Used by clr-loader and sounddevice | MIT-0 / BSD-3-Clause | pycparser: Copyright (c) 2008-2027, Eli Bendersky |
| [pywin32-ctypes](https://github.com/enthought/pywin32-ctypes) | Windows calls | BSD-3-Clause | Copyright (c) 2014, Enthought, Inc. |
| [typing_extensions](https://github.com/python/typing_extensions) | Python support | PSF-2.0 | Python Software Foundation |
| [sounddevice](https://github.com/spatialaudio/python-sounddevice) | Playing audio | MIT | Copyright (c) 2015-2026 Matthias Geier |
| [PortAudio](https://www.portaudio.com) (build from spatialaudio/portaudio-binaries) | Playing audio | MIT | Copyright (c) 1999-2011 Ross Bencina and Phil Burk |
| [PyInstaller](https://pyinstaller.org) bootloader and run-time hooks | Starting the app | GPL-2.0-or-later with the Bootloader Exception; run-time hooks Apache-2.0 | Copyright (c) 2010-2023, PyInstaller Development Team |
| Microsoft Visual C++ Runtime (`VCRUNTIME140.dll`) | Python support | Microsoft redistributable | Copyright (C) Microsoft Corporation |

## Inside the Android app

Besides the Python projects above that run the engine (Python, yt-dlp, yt-dlp-ejs, ytmusicapi,
requests and what it uses):

| Project | Used for | Licence | Copyright |
|---------|----------|---------|-----------|
| [Android Jetpack](https://developer.android.com/jetpack) (Compose, Activity, Core) and [Media3](https://github.com/androidx/media) | The app's screens and playback | Apache-2.0 | Copyright The Android Open Source Project |
| [Chaquopy](https://chaquo.com/chaquopy/) runtime | Runs the Python engine on Android | MIT | Copyright (c) Chaquo Ltd |
| [QuickJS-ng](https://github.com/quickjs-ng/quickjs) | Used by yt-dlp for YouTube | MIT | Copyright (c) 2017-2024 Fabrice Bellard, Charlie Gordon and the QuickJS-ng contributors |
| [ZXing](https://github.com/zxing/zxing) and [ZXing Android Embedded](https://github.com/journeyapps/zxing-android-embedded) | Reading the code your PC shows (Your computer) | Apache-2.0 | Copyright ZXing authors; Copyright (C) 2012-2022 ZXing authors, Journey Mobile |

Pocketful reads and writes tags (M4A, MP3, FLAC, Ogg, WAV) with its own code, written
from the public format specifications. It does not use any GPL library.

## Facts and formats

- **libgpod** ([gtkpod project](https://github.com/gtkpod/libgpod), LGPL-2.1-or-later;
  `src/itdb_device.c` Copyright (C) 2002-2007 Jorg Schuler): the iPod model-number and
  serial-number table Pocketful uses to recognise iPods was taken from it. libgpod and
  WikiPodLinux also document the `iTunesSD` and `iTunesDB` formats, which Pocketful's own
  code writes. No libgpod code is copied.

## Online services

Pocketful reads data from these services through their public pages or APIs. Each has its
own terms, which may restrict some uses; Pocketful's authors have not accepted them on
anyone's behalf, and using a service through Pocketful does not change what its terms say
(see [DISCLAIMER.md](DISCLAIMER.md)). Pocketful is not affiliated with any of them: Spotify (public pages and embed), Deezer
(public API), YouTube Music, Tidal, Apple Music and SoundCloud (public pages), Music-Map
(Gnod), Spoqify, MusicBrainz, ListenBrainz and the Cover Art Archive (open data from the
MetaBrainz Foundation).
