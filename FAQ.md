---
layout: question
title: Frequently Asked Questions
permalink: /FAQ/
category: help
---
{::options auto_ids="true" /}

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

* Will be replaced with the ToC
{:toc}

**See Also**

- [Posts in the Forum tagged #FAQ](https://forum.shotcut.org/search?q=tags%3AFAQ)
- [How To Articles](../howtos/)

## What are the minimum system requirements?

Operating system: 64-bit Windows 10 (build 1809) - 11, Apple macOS 12 - 15, or
64-bit Linux with at least glibc 2.31.

CPU: x86-64 Intel or AMD; at least one 2 GHz core for SD, 4 cores for
HD, and 8 cores for 4K.

GPU: OpenGL 2.0 that works correctly and is compatible on Linux, Direct3D 11 on Windows.

RAM: At least 4 GB for SD, 8 GB for HD, and 16 GB for 4K.

NOTE: If your computer is at the lower end of CPU and RAM requirements, you should use both the
[Preview Scaling](https://forum.shotcut.org/t/preview-scaling/15650) and
[Proxy](https://forum.shotcut.org/t/proxy-editing/18517) features to help reduce preview lag.

Hard drive: yes, get one; the bigger, the better :-)

Network: Shotcut does NOT require access to the network to activate,
check a subscription, or send usage analytics. However, some links in
the Help menu do link out to this web site. If you have files on a fast
(at least 1 Gb/s) network share you can access them from there through
your operating system.

* * *
<script>
    if (location.hostname.endsWith("shotcut.org")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Mobile_300_2"></div>');
    } else if (location.hostname.endsWith("shotcut.com")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Mobile_300_2"></div>');
    } else {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Mobile_300_2"></div>');
    }
</script>

## Why does it crash on Windows upon launch?

Is this a new - for the first time ever - installation of Shotcut?
If NOT, and it used to work, then you may need to delete your Shotcut
registry entries and try again. The registry keys are stored at
HKEY_CURRENT_USER\Software\Meltytech\Shotcut\.

One Windows 8.1 user reported he needed to change the following in
the Compatibility tab of the Properties for the Shotcut icon/exe: Run in
compatibility mode for "Windows XP (Service Pack 2)", and "Run this
program as administrator." However, not every one needs to do that, and
we are not sure why he needed it.

* * *

## I have trimmed my video and/or created my project, now how do I save or share it?

If you just want to save your changes to re-open it later in Shotcut,
you can save your project as a MLT XML file by clicking **Save** on the
toolbar at the top of the window. If you want to upload the video to a
web site or somehow share the result with someone as separate video
file, then choose **File > Export > Video...** from the menu.

By default, if you have made a playlist **Export** uses the **Playlist** unless you
have put something into the **Timeline**, in which case, it uses the
timeline. Otherwise, it will Export the clip or live source (stream,
device, screen, etc.). However, you can control what is used for the source of
the export using the **From** control at the top of the **Export** panel.

* * *

## Which Export preset should I use?

It all depends; that is why there are so many of them! But here are some
suggestions:

-   Upload to a video-sharing web site: `H.264 High Profile` or `YouTube`
-   Extract the audio: `Ogg Vorbis`, `FLAC` (lossless with compression), or good old `MP3`
-   Save to an intermediate file to use with another tool: `DNxHR HQ` or
    `ProRes 422` - really depends on what the other tool accepts
-   Put onto my own web site: `WebM` and/or `Default` (moderate quality H.264)
-   Screen recording (Linux only): `intermediate/MJPEG`
-   Capture from SDI/HDMI: `intermediate/ProRes 422` if your system can handle it,
    otherwise `intermediate/MPEG-2`

* * *

## What can I do if Export is failing or getting stuck?

If a job appears to be stuck or hung (please allow ample time for percentage to
change), right-click the job in the Jobs panel and choose **Stop**. Try export
again with **Export > Video > Parallel processing** disabled (unchecked). If
there is still a problem see what percentage it reaches before failing or
hanging. Then, apply the percentage to your project duration to find the rough
time of where it seems to be having trouble. Is there something complicated or
different there? You can temporarily remove some things in this area and try
again to see if export goes further.

* * *

## How do I add text? Is there a titler?

There are 2 text filters at this time: **Text: Simple** and **Text: Rich**. You can apply the text filters to a video
clip, an image file or a whole track. You can also apply a text filter to a transparent clip to act as its own text clip
by choosing **File > Open Other > Text** from the menu or **Open Other > Text** from the main toolbar. The default
background color in **Open Other > Text** is transparent which as well can be changed to a solid color by clicking on
the **Background color** button.

You can also create text with an external program as an image with an alpha channel and composite it. To composite, you
add a video track to the Timeline to use as a layer. Then, you open an image, set its Properties to adjust duration or
enable an image sequence, add it to the new video track, and further adjust its position and duration as-needed. You
might also want to apply the **Size, Position & Rotate** filter to the image clip. The image file formats that
support an alpha channel are PNG, SVG, and TGA. You can also use Quicktime Animation format. There are many tools that
can create images with alpha channels for this purpose. Some of them include GIMP, Inkscape, Krita, Paint.NET, etc. For
animation, consider Blender and Synfig.

* * *

## Why is seeking so slow?

Some formats and compression methods simply make it take longer. In the
**Settings** menu set **Interpolation** to **Nearest Neighbor**. This
setting not only affects the quality of image scaling but also the
accuracy of seeking. Please be aware that this setting may cause seeking
to become less accurate resulting in some frames repeating when stepping
frame-by-frame backwards or the first several frames in the forward
direction immediately after a seek.

* * *

## Why is stepping frame-by-frame repeating the same frame?

In the **Settings** menu set **Interpolation** to something other than
**Nearest Neighbor** - **Bilinear** is recommended. When the
interpolation level is set to nearest neighbor it relaxes the accuracy
of seeking to make the responsiveness of the video player faster.

* * *

## Are there keyboard shortcuts for editing?

The best way to see the shortcuts is in the Actions and Shortcuts dialog.
This dialog appears by navigating "Help->Actions and Shortcuts..." or by
pressing the "?" key.

There is also a [page with all of the keyboard shortcuts]( {{ "/howtos/keyboard-shortcuts/" | prepend: site.baseurl }} ).

Just like j, k, and l for playback transport control, the bare i, o, x,
v, b are very common shortcuts use by other professional video editing
software from Apple, Avid, Lightworks, and others.

P.S. While it is rather obvious to use cursor left and right keys for
single frame stepping, there is another technique so you do not have to
remove your fingers from the JKL: while holding down K, tap J to step
left or tap L to step right.

* * *
<script>
    if (location.hostname.endsWith("shotcut.org")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Mobile_300_2"></div>');
    } else if (location.hostname.endsWith("shotcut.com")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Mobile_300_2"></div>');
    } else {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Mobile_300_2"></div>');
    }
</script>

## The keyboard shortcuts do not seem to be working.

Sometimes the keyboard "focus" might be captured by something in the GUI
causing the shortcuts to not function. In that case, click the video
preview region to return focus to the player.

* * *

## Shotcut will not start on Linux...

Some file managers do not like the launcher icon provided with the
binary download from this site. The launcher icon was tested
successfully on GNOME Nautilus and KDE Dolphin.

1. open a terminal/console window
2. cd to the location where you have extracted Shotcut
3. enter `Shotcut.app/shotcut`\\
Please do not try to run bin/shotcut; always use the wrapper script in the Shotcut.app
folder! If it still does not start, then it should report that some
libraries could not be loaded.

* * *

## All I see is white or green instead of video, and I know there is video in this file....

First, use **Properties** to see if the **Video** tab is disabled. If it
is disabled, then Shotcut is not compatible with this format or codec.
If the video tab is enabled, more than likely OpenGL (or also Direct3D on
Windows) is not working on your system, or it is too old. First, make
sure **GPU Effect** is disabled in **Settings**. GPU effects
requires OpenGL version 3.2. When it is disabled, you only need OpenGL
version 2.0 on Linux, Direct3D on Windows, or Metal on macOS.

* * *

## Can I have multiple versions installed at the same time?

Yes. Simply rename your existing program folder to put the version
number in it or move it out-of-the-way to another location.

On **Windows**, the installer is mostly just a fancy zip extractor that also
adds a start menu item. So, you can install the new version to a
different location, or rename the existing folder to prevent it from
being overwritten. Then, you can just navigate to whichever program
folder you want in Explorer and run shotcut.exe.

On **macOS**, you do not
need to copy Shotcut to the /Applications folder - that is merely a
suggestion. Simply drag Shotcut out of the .dmg to wherever you like and
rename the app bundle to put the version number into it. Or, rename the
existing version to move it out of the way before copying Shotcut from
the .dmg.

The same concepts apply to **Linux**, where Shotcut is simply
delivered as a compressed tar archive. However, on Linux, it is
important to understand that the launch icon always looks in
Shotcut.app; so, either version the folder containing the launch icon or
have multiple, versioned Shotcut.app folders and run the launch *script*
that is inside of it.

* * *

## How do I cut or trim a clip without encoding or transcoding it?

This is available through **Properties > menu > Extract Sub-clip...**; however,
it is not frame accurate and there are some pitfalls.
We recommend LosslessCut, VirtualDub, or Avidemux as alternatives for this.
However, those usually have the same limitations and problems.
In Shotcut you can try the extract, and instead export if that did not work good enough.

* * *

## Why do I not have the \_\_ filter?

-   Some filters are not compatible with GPU Processing.
-   Some filters cannot be applied to a track or the entire timeline (i.e. Output).
    Please check what is currently selected. The top of the Filters panel shows
    the name of what is selected.
-   By design, we do not make all LADSPA and frei0r filters available
    through the UI. We do not want to present a confusing generic
    interface to all available plugins and overwhelm users with so many,
    often redundant, options. Also, the Shotcut team wants to better
    understand the filters we are providing and ensure each one is
    operating as intended with MLT. If you are manually authoring XML,
    then you can add any filter you want.
-   Sometimes a MLT plugin may fail to load due to a missing or
    incompatible library. Shotcut downloads provide all dependencies for
    Windows and macOS, but it may rely upon some libraries provided by
    distribution packages on Linux.

* * *

## Is Shotcut free for commercial use?

Yes, because the software is made available under the GPLv3 license, it
supports [The Free Software Definition](https://www.gnu.org/philosophy/free-sw.html),
which includes:
> The freedom to run the program as you wish, for any purpose (freedom 0).

* * *

## What is your privacy policy?

The Shotcut software does not collect, store, or share any personal information.
It does not even collect any usage activity to send to our server.
The exception to that is the Microsoft Store, and you can read the
[Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement).
Of course, there might be other app stores and distribution systems, as permitted
by the license, with their own personal information collection that is not
under our control.

The Shotcut forum has a [privacy policy](https://forum.shotcut.org/privacy).

* * *

## Where are the log, presets, cache, and settings stored?

Currently, the cache is used to store thumbnail and waveform data.

**Windows**

The log, cache, and presets are stored in
%LOCALAPPDATA%\\Meltytech\\Shotcut\\. In the Explorer location bar, enter
"%LOCALAPPDATA%" and press Enter. Then look for Meltytech\\Shotcut.

The settings are
stored in the registry at key
HKEY\_CURRENT\_USER\\Software\\Meltytech\\Shotcut\\.

**Linux**

The log, cache, and presets are stored in
\~/.local/share/Meltytech/Shotcut/ where '\~' is your home directory, of
course.

The settings are stored in \~/.config/Meltytech/Shotcut.conf, which is a
text file in INI format.

**macOS**

The log, cache, and presets are stored in \~/Library/Application
Support/Meltytech/Shotcut/, where '\~' is your home directory, of
course.

The settings are stored in
\~/Library/Preferences/com.meltytech.Shotcut.plist, which is a [binary
plist](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)
file.

* * *
<script>
    if (location.hostname.endsWith("shotcut.org")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Mobile_300_2"></div>');
    } else if (location.hostname.endsWith("shotcut.com")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Mobile_300_2"></div>');
    } else {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Desktop_728_2"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Mobile_300_2"></div>');
    }
</script>

## What is the history of Shotcut?

Shotcut was originally
[announced](http://permalink.gmane.org/gmane.comp.lib.fltk.general/2397)
in November, 2004! You can read more about it from a
[backup of its original website](https://web.archive.org/web/20050401015503/http://users.pandora.be/acp/shotcut/).
The current version of Shotcut is a complete rewrite with none of the
original requirements in mind. The original Shotcut was created by
Charlie Yates, a MLT co-founder and original lead developer. Since Dan
Dennedy, another MLT co-founder and its current lead, wanted to create a
new editor based on MLT, he simply chose to [reuse the
name](https://mltframework.org/blog/end_of_2011_update/)
since he liked it so much. The current Shotcut had its origins as the
[MLT BuildOnMe project](https://github.com/mltframework/BuildOnMe).
BuildOnMe was created in January, 2011 as a minimal, example project of
how to use MLT in a cross-platform Qt 4 project. Eventually, Dan sought
to replace the aging Melted GTK+ client, Rugen, with a cross-platform
replacement and needed an app on which to easily test the cross-platform
compatibility of new MLT features such as
[WebVfx](https://github.com/mltframework/webvfx#readme) and
[Movit](https://movit.sesse.net/).
That led him to fork BuildOnMe and start Shotcut.

* * *

## How do I make subtitles?

If you are strictly asking about subtitles or closed captions, Shotcut
does not read, make, edit, or pass-through subtitles. There is planned
the ability to read, show, pass-through, and burn-in subtitles, but
there is no estimated time of arrival. We recommend that you try the
free, open source, cross-platform subtitle editor
[Aegisub](http://www.aegisub.org/).

However, if you are just asking about the ability to put/overlay text in
your video, use the **Text: Simple** or **Text: Rich** filter.
Since it is a filter, that means you need something to which to apply
it. If you just want a solid color, choose **File > Open Other >
Color**. You can also use a picture/photograph just like a video clip by
opening it and adding it to your playlist or timeline. If you just want a
text clip (transparent background) choose **Open Other > Text** and add it
to your playlist or timeline.

* * *

## How do I change the speed of the video?

This is implemented as of version 16.01. With a clip open in the source
player or selected in the timeline, choose **Properties** and look for
the **Speed** field. Shotcut only provides simple frame dropping or
duplicating. However, if the frame rate of your source footage is higher
than the Video Mode (under Settings menu), then you can achieve a fairly
smooth slow motion. If you are looking for more sophisticated results
using more advanced optical flow techniques, we recommend you try the
free, open source, cross-platform tool
[slowMoVideo](http://slowmovideo.granjow.net/).

* * *

## How can I edit the audio at the wave/sample level?

Shotcut does not offer that, but we recommend to try the free, open
source, cross-platform tool [Audacity](http://audacityteam.org/).

* * *

## How does Shotcut use the GPU (or not)?

Shotcut uses the GPU in three ways:

1. For drawing parts of the user interface and showing video: Direct3D on Windows, Metal on macOS, and OpenGL on Linux.
2. hardware encoding (where available and enabled)
3. OpenGL for GPU Effects (filters and transitions) mode

Shotcut does NOT use the GPU or hardware acceleration for the following:

1. decoding and pixel format conversion
2. automatic (as-needed) filters to deinterlace, scale, and pad video and to
   resample or downmix audio
3. filters that you add
4. transitions
5. compositing/blending video tracks
6. mixing audio tracks

Thus, you cannot expect Shotcut to use close to 0% CPU and much % of GPU
when exporting using the hardware encoder because the reading of files and
decoding alone becomes a bottleneck to feed the hardware encoder. Also, if you
have any decent amount of image processing, you should expect a significant
amount of CPU usage especially if parallel processing is enabled (it is by
default). Software from other companies may limit itself to one GPU vendor API
such as CUDA in order to provide almost entirely GPU-based pipeline. Shotcut
has not chosen to go that route because it is a cross-platform solution.

* * *

## Why does Shotcut not use hardware accelerated video decoding?

The video stream always originates in system (CPU) RAM, and CPU-based video
decoding is highly optimized and fast. Meanwhile, transferring full,
uncompressed video from the GPU RAM to system RAM is a relatively slow. Thus, in
the context of a video editor (not simply a player or transcoder),
hardware-accelerated decoding should only be done when all video processing can
also be done on the GPU. That alone is non-trivial. Shotcut does have an
OpenGL-based effects system that is disabled and hidden currently due to
instability. Even when enabled it is a small subset of all effects and does not
include a deinterlacer. Next, assuming you do not need to deinterlace and agree
to limit oneself to the GPU effects, there is a major technical hurdle to
transfer the decoded video in GPU RAM to OpenGL textures due to [multiple
APIs](https://trac.ffmpeg.org/wiki/HWAccelIntro) for multiple operating systems.
Likewise, the complexity to convert OpenGL textures to hardware encoder frames
for the various hardware encoding APIs. Any tool that claims to do all of these
but does not ensure the video stays in GPU RAM is going to have limited
performance gain if any.

Even if made available (integrated) there are major hurdles to handle resource
limitations (number of simultaneous decodes) in a robust fashion and to handle
incompatible video streams with many permutations of encoding
profiles/parameters, APIs, and devices. That would result in a huge source of
unreliability and support issues.

If you want to help with this, please feel free to 
[contribute]( {{ "/howtos/contribute/" | prepend: site.baseurl }} ).
We have not made much progress here due to higher priorities: fixing bugs,
rework on some features, adding basic expected UI features, upgrading
dependencies, providing support, making documentation, and stabilizing GPU Effects.

* * *

## How does Shotcut use multiple CPU cores and threads?

Shotcut's engine (MLT atop FFmpeg and other libraries) uses multiple CPU
cores/threads for:

1. decoding video on _many_ (most?) video codecs
2. image slice-based multi-threaded processing in _some_ processes
3. frame-based multi-threaded image processing in _many_ processes
4. encoding video when not using the hardware encoder on _most_ video codecs

When any of the above is not enabled, a bottleneck is introduced. Some of these
are minor and others major depending on the weight of the operation.

Shotcut's interface - in addition to the main UI thread - uses multiple
background CPU cores/threads for:

1. generating video thumbnails
2. generating audio levels for waveform display in the timeline
3. the engine itself (see above)
4. sending video to OpenGL for display
5. exporting

* * *

## How can I scale the GUI on my high DPI monitor?

Use the QT_SCALE_FACTOR
[command line options](https://shotcut.org/notes/command-line-options/).


On Windows, you can also create a shortcut to shotcut.exe. Then, edit the
shortcut and modify the target field in the shortcut to include the
QT_SCALE_FACTOR. E.g. `C:\Program Files\Shotcut\shotcut.exe --QT_SCALE_FACTOR 2`

* * *

## Does Shotcut support High Dyanmic Range (HDR) video?

Shotcut does not properly display or output HDR video. However, it can convert
HDR video with tone-mapping into a Rec. 709 SDR video. In the UI use either
**Properties > Convert** or **View > Resources...** in the menu.
