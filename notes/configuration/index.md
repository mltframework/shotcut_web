---
layout: page
title: Configuration Keys
category: notes
---

<script>
    if (location.hostname.endsWith("shotcut.org")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Desktop_728_1"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Mobile_300_1"></div>');
    } else if (location.hostname.endsWith("shotcut.com")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Desktop_728_1"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Mobile_300_1"></div>');
    } else {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Desktop_728_1"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Mobile_300_1"></div>');
    }
</script>

### Location

If an `appdatadir` folder is supplied (see below), the configuration file is
named shotcut.ini in the folder. Otherwise, where the configuration lives
depends on the operating system:

**Windows**

The settings are
stored in the registry at key
HKEY\_CURRENT\_USER\\Software\\Meltytech\\Shotcut\\.

**Linux**

The settings are stored in \~/.config/Meltytech/Shotcut.conf, which is a
text file in INI format.

**macOS**

The settings are stored in
\~/Library/Preferences/com.meltytech.Shotcut.plist, which is a [binary
plist](https://developer.apple.com/library/mac/documentation/Darwin/Reference/Manpages/man5/plist.5.html)
file.

### Keys

How the category appears depends on the config file format. Linux conf and Windows INI file uses sections (square brackets), Windows registry uses a sub-key, and macOS plist
prefixes the key name followed by a period and the key. In 
Windows registry, a bool is stored as a string: true or false.

| Key              | Type        | Description
|------------------|-------------|------------
| appdatadir       | string      | the file system path where to load configuration. If this is set, then all the remaining configuration keys are read from shotcut.ini instead of the registry (Windows), plist (macOS), or ~/.config (Linux).
| askUpgradeAutomatic | bool     | whether to ask if you want to check for an update automatically (default true)
| audioInput       | string      | the most recently chosen audio device in Open Other > Audio/Video Device (default first input)
| backupPeriod     | integer     | how frequently to backup the project file in minutes (default 1440 daily)
| checkUpgradeAutomatic |  bool  | whether to check for an update automatically at startup (default false)
| clearRecent      | bool        | Setting > Clear Recent on Exit
| chromiumPath     | string      | the file system path to the chromium executable (default depends on OS)
| convertAdvanced  | bool        | whether to keep the Advanced section of the Convert dialog open (default false)
| dockerPath       | string      | the file system path to the docker executable for Text to Speech (default depends on OS)
| exportFrameSuffix | string     | the last used format for File > Export Frame (default `.png`)
| exportRangeMarkers | bool      | File > Export > Markers as Chapters > Include ranges
| flatpakWrappers  | bool        | whether to ask to choose a Flatpak for Open With > Add on Linux (default true)
| geometry         | binary      | before version 23.05.07, the size and position of the windows
| geometry2        | binary      | as of version 23.05.07, the size and position of the windows
| geometryDefault  | binary      | used to save View > Layout > Restore Default Layout
| glaxnimatePath   | string      | the path to the glaxnimate executable if glaxnimate (default "glaxnimate" in same dir as shotcut executable)
| imageDuration    | real number | the default duration of a newly opened image file
| jobPriority      | string      | the priority of background melt and ffmpeg jobs such as export and proxy: `low` (default) or `normal`
| language         | string      | lowercase, two-letter ISO 639 language code, or &lt;language&gt;_&lt;country&gt; where &lt;country&gt; is an uppercase, two- or three-letter ISO 3166 country code (Settings > Language)
| noupgrade        | bool        | whether to show the prompt to check for upgrade upon app launch
| openPath         | string      | the file system path for the file-open dialog
| opengl           | integer     | Settings > Display Method, in decimal: 0 (Automatic), 15 (OpenGL), 16 (DirectX, Windows only), or 17 (Software)
|                  |             | This is no longer used on Windows and macOS as of version 23.05.07.
| processingMode   | integer     | Settings > Processing Mode, one of: 0 (native 8-bit CPU, default), 2 (native 10-bit CPU), 3 (linear 10-bit CPU), 4 (linear 10-bit GPU/CPU)
| projects         | string list | list of XML project files with full path: comma-separated `recent.ini` text file
| projectsFolder   | string      | the file system path in which project folders are created
| recent           | string list | list of recent media and XML files with full path: comma-separated in Linux or Windows INI, multi-string in Windows registry, and array of strings in macOS plist (View > Recent)
|                  |             | This is no longer saved here as of version 23.05.07 and moved to a separate `recent.ini` text file.
| savePath         | string      | the file system path for the file-save dialog
| screenRecorderPath|string      | the file system path to a user-definable screen recorder on Linux with Wayland but not GNOME or KDE (default "obs")
| showConvertClipDialog | bool   | whether to continue to show the Convert to Edit-friendly dialog for variable frame rate or non-seekable files
| theme            | string      | UI theme, one of: dark, light, or system (Settings > Theme)
| timeFormat       | integer     | Settings > Time Format, one of: 0 (Frames), 1 (Clock), 2 (Timecode Drop-Frame, default), 3 (Timecode Non-Drop Frame)
| titleBars        | bool        | whether to show the title bar for UI panels (View > Show Title Bars)
| toolBar          | bool        | whether to show the main tool bar at the top of the main window (View > Show Toolbar)
| undoLimit        | integer     | the maximum number of undo commands in View > History (default 1000)
| videoInput       | string      | the most recently chosen video device in Open Other > Audio/Video Device (default first input)
| warnLowMemory      | bool      | whether to check for low CPU RAM memory and show a warning dialog (default true)
| windowState      | binary      | before version 23.05.07, the current layout of the UI panels
| windowState2     | binary      | as of 23.05.07, the current layout of the UI panels
| windowStateDefault | binary    | used to save View > Layout > Restore Default Layout
| ***encode***
| advanced         | bool        | whether to always show the Advanced mode for Export (default false)
| freeSpaceCheck   | bool        | whether to continue checking if a storage volume has sufficient space for storing Video
| hardware         | string list | list of hardware encoders available on this system: comma-separated in Linux or Windows INI, multi-string in Windows registry, and array of strings in macOS plist (View > Recent)
| hardwareDecoder  | bool        | whether to use the hardware video decoder (default false)
| path             | string      | the file system path for Export > Export File
| useHardware      | bool        | whether to use hardware encoding if available (default false)
| ***files***
| currentDir       | string      | the current folder in Files (default Home)
| foldersOpen      | bool        | whether the folders tree is visible in Files (default true)
| location/&lt;custom location name&gt; | string | the full path to the saved Location
| locations        | string list | the names of the saved custom Locations
| openOther/&lt;type&gt; | string list | full paths to saved executables for Open With per media types: audio, image, other, video
| viewMode         | string      | one of: detailed, icons, or tiled
| ***filter***
| askOutput        | bool        | whether to show warning dialog about adding filters to Timeline Output
| audioInCurve     | integer     | the default Fade Audio In > Type, one of: 1 (Natural, default), 16 (S-Curve), 15 (Fast-Slow), 14 (Slow-Fast)
| audioInDuration  | real number | the default Fade Audio In duration in seconds
| audioOutCurve    | integer     | the default Fade Audio Out > Type, one of: 1 (Natural, default), 16 (S-Curve), 15 (Fast-Slow), 14 (Slow-Fast)
| audioOutDuration | real number | the default Fade Audio Out duration in seconds
| favorite/&lt;filterId&gt; | string | whether a filter is chosen as favorite, one of: yes or no. See all the meta.qml files in share/shotcut/qml/filters for the filter IDs.
| videoInDuration  | real number | the default Fade Video In duration in seconds
| videoOutDuration | real number | the default Fade Video Out duration in seconds
| ***keyframes***
| dragScrub        | bool        | Keyframes > Scrub while dragging (default false)
| ***layout***
| &lt;custom layout name&gt;_geometry | binary | the size and position of the windows
| &lt;custom layout name&gt;_state | binary | the layout of the UI panels
| layouts          | string list| the names of all of the custom saved layouts
| mode             | integer    | which of the layout modes is selected: 0 = custom, 1 = Logging, 2 = Editing, 3 = FX, 4 = Color, 5 = Audio, 6 = Player 
| ***markers***
| color            | string      | the color to use for a new marker (default green)
| columns/color    | bool        | whether to show the Color column (default true)
| columns/duration | bool        | whether to show the Duration column (default true)
| columns/end      | bool        | whether to show the End column (default true)
| columns/start    | bool        | whether to show the Start column (default true)
| columns/text     | bool        | whether to show the Text column (default true)
| sortColumn       | integer     | the column on which to sort (default -1, unsorted or natural order)
| sortOrder        | integer     | whether to sort ascending (0, default) or descending (1)
| ***player***
| audioChannels    | integer     | the number of audio channels to use (Settings > Audio Channels)
| audioDriver      | string      | Settings > Player > Audio API (only on Linux or Windows)
| deinterlacer     | string      | one of: onefield, linearblend, yadif-nospatial, or yadif (Settings > Deinterlacer)
| external         | string      | for Settings > External Monitor, one of: sdi (Linsys card), decklink:&lt;N&gt; (Blackmagic Design peripheral), or &lt;N&gt; (screen)
| gpu              | bool        | before version 23.05.07, whether Settings > GPU Effects is on (default false)
| gpu2             | bool        | as of v23.05.07, whether Settings > GPU Effects is on (default false)
| interpolation    | string      | for Settings > Interpolation, one of: nearest, bilinear, bicubic, or hyper (Lanczos)
| jack             | bool        | whether Settings > Use JACK Audio is on
| keyer            | integer     | for Settings > External Monitor > Decklink Keyer, one of: 0 (Off), 1 (Internal), 2 (External)
| muted            | bool        | whether the player volume is muted
| pauseAfterSeek   | bool        | Settings > Player > Pause After Seek (default true)
| previewHardwareDecoder | bool  | Settings > Preview Scaling > Use Hardware Decoder (default true except NVIDIA onj Linux) |
| profile          | string      | for Settings > View Mode, see file names in share/mlt/profiles for a list of values or blank for Automatic
| progressive      | bool        | whether Settings > Progressive is on
| realtime         | bool        | whether Settings > Realtime is on
| scrubAudio       | bool        | whether Settings > Scrub Audio is on
| videoDelayMs     | real number | for Settings > Synchronization... (default 0)
| volume           | integer     | the player volume level as a percentage
| warnGPU          | bool        | before version 23.05.07, whether to show warning dialog when GPU Effects is on (default true)
| zoom             | real number | the player's current zoom level as a factor from 0 to 2 where 0 means "Fit"
| ***playlist***
| autoplay         | bool        | whether to automatically start playing after opening a clip from the playlist
| columns/clip     | bool        | whether to show the Clip name column in the details view (default true)
| columns/date     | bool        | whether to show the Date column in the details view (default true)
| columns/in       | bool        | whether to show the In point column in the details view (default true)
| columns/start    | bool        | whether to show the Start time column in the details view (default true)
| columns/thumbnails| bool       | whether to show the Thumbnails column in the details view (default true)
| colunms/duration | bool        | whether to show the Duration column in the details view (default true)
| previewScale     | integer     | the vertical resolution to use for preview scaling, default 0 means none/inactive
| thumbnails       | string      | how to show the thumbnails in the Playlist panel, one of: hidden, wide, tall, small, large
| viewMode         | string      | one of: detailed, icons, or tiled
| ***proxy***
| enabled          | bool        | for Settings > Proxy > Use Proxy (default false)
| folder           | string      | for Settings > Proxy > Storage > Set.... (default a sub-folder "proxies" of the App Data Directory)
| projectFolder    | bool        | for Settings > Proxy > Storage > Use Project Folder (default true)
| useHardware      | bool        | for Settings > Proxy > Use Hardware Encoder (default false)
| ***scope***
| loudness/integrated | bool     | View > Scopes > Audio Loudness > menu > Integrated Loudness
| loudness/momentary | bool     | View > Scopes > Audio Loudness > menu > Momentary Loudness
| loudness/peak | bool     | View > Scopes > Audio Loudness > menu > Peak
| loudness/range | bool     | View > Scopes > Audio Loudness > menu > Loudness Range
| loudness/shortterm | bool     | View > Scopes > Audio Loudness > menu > Short Term Loudness
| loudness/truepeak | bool     | View > Scopes > Audio Loudness > menu > True Peak
| ***shortcuts***
| * | string | These store the custom keyboard shortcuts. There can be many of these keyed roughly on their English name. The value is one or two "\|\|"-separated key sequences.
| ***slideshow***
| aspectConversion | integer     | Aspect ratio conversion: 0 for pad black, 1 for center crop (default), 2 for crop and pan, 3 for blur pad
| clipDuration     | real number | Clip duration in seconds, default 10
| transitionDuration| real number| Transition duration in seconds, default 2
| transitionSoftness| real number| Transition softness in %, default 20 
| transitionStyle  | integer     | Transition type, default 2 (dissolve)
| zoomPercent      | integer     | Zoom effect in %, default 10
| ***speech***
| language    | string        | the code of the last used language, one of: a, b, e, f, h, p, j, z (default "a")
| speed       | real number   | the last used speed value (default 1.0)
| voice       | string        | the last used kokorodoki voice argument, see its docs (default "af_alloy")
| ***subtitles***
| columns/duration | bool        | whether to show the Duration column (default true)
| columns/end      | bool        | whether to show the End column (default true)
| columns/start    | bool        | whether to show the Start column (default true)
| showPrevNext     | bool        | Subtitles > menu > Show Previous/Next (default true)
| trackTimeline    | bool        | Subtitles > menu > Track Timeline Cursor (default true)
| whisperExe       | string      | override full path to whisper-cli executable
| whisperModel     | string      | override full path the whisper model in ggml format
| **notes**
| zoom             | real number | Notes > context menu > Decrease/Increase Text Size
| ***timeline***
| audioReferenceSpeedRange|real number|Timeline > menu > Align To Reference Track > Speed adjustment range (default 0)
| audioReferenceTrack | integer  | Timeline > menu > Align To Reference Track > Reference audio track (last used)
| autoAddTracks    | bool        | Settings > Timeline > Automatically Add Tracks (default false)
| dragScrub        | bool        | Timeline > Scrub while dragging (default false)
| previewTransition| bool        | transition Properties > Preview (default true)
| rectangleSelect  | bool        | Settings > Timeline > Rectangle Select (default true)
| ripple           | bool        | Timeline > Ripple trim and drop
| rippleAllTracks  | bool        | Timeline > menu > Ripple All Tracks
| rippleMarkers    | bool        | Timeline > toolbar > Ripple timeline markers with edits (default false)
| scrollZoom       | bool        | Timeline > menu > Scroll to Playhead on Zoom
| scrolling        | integer     | Settings > Timeline > Scrolling, one of: 0 (No), 1 (Center), 2 (Page, default), 3 (Smooth)
| snap             | bool        | Timeline > Toggle snapping
| thumbnails       | bool        | Timeline > menu > Show Video Thumbnails
| trackHeight      | integer     | Timeline > menu > Make Tracks Shorter/Taller
{:.withborders}
