---
layout: page
title: Command Line Options
category: notes
---

<div data-aaad='true' data-aa-adunit='/22247219933/shotcutorg_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutorg_Mobile_300_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutcom_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutcom_Mobile_300_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutapp_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutapp_Mobile_300_1'></div>

```
Usage: shotcut [options] [FILE]...

Options:
  -h, --help                        Displays this help.
  -v, --version                     Displays version information.
  --fullscreen                      Fill the screen with the Shotcut window.
  --noupgrade                       Hide upgrade prompt and menu item.
  --glaxnimate                      Run Glaxnimate instead of Shotcut.
  --gpu                             Use GPU processing.
  --clear-recent                    Clear Recent on Exit
  --appdata <directory>             The directory for app configuration and data.
  --QT_SCALE_FACTOR <number>        The scale factor for a high-DPI screen
  --QT_SCREEN_SCALE_FACTORS <list>  A semicolon-separated list of scale factors for each screen
  --QT_SCALE_FACTOR_ROUNDING_POLICY <string> How to handle a fractional display scale:
                                    Round, Ceil, Floor, RoundPreferFloor, PassThrough
  --SDL_AUDIODRIVER <string>        Which operating system audio API
                                    to use: directsound, wasapi, winmm (Windows)
                                    alsa, arts, dsp, esd, jack, pipewire, pulseaudio (Linux)

Arguments:
  [FILE]...                         Zero or more files or folders to open
```

When `--appdata` is supplied the configuration key `appdatadir`
is not written to the normal [configuration file/registry]({{ "/notes/configuration/" | prepend: site.baseurl }}).

`resource` can be anything that Shotcut can open such as a media file, MLT XML
project file, generic MLT XML file, or even a MLT producer specification (e.g. `noise:`).
