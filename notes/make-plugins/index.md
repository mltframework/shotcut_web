---
layout: page
title: How to Make a Plugin
category: notes
---

Introduction
============

At this time, Shotcut only supports Filter plugins. However, in the mid-term
future we hope to offer transitions and generators. There are two parts to a
plugin: the backend that does the actual audio or video processing and the
front-end that offers a user interface (UI). By design, there is no support to
automatically generate a UI for the parameters of your plugin. Neither is it
possible to launch an external, platform-native UI as many tools do.

Backend
=======
You can make a new backend using a number of technologies including
[MLT](https://www.mltframework.org),
[frei0r](http://frei0r.dyne.org/codedoc/html/),
[LADSPA](https://en.wikipedia.org/w/index.php?title=LADSPA&oldid=696034724), or 
There are also many existing plugins for these
that are already bundled with Shotcut builds that do not yet have a frontend!
Thus, you might want to use an existing
[MLT filter](https://www.mltframework.org/bin/view/MLT/PluginsFilters)
and simply create a frontend for it. Continue reading for more information about
creating a new backend.

Audio
-----
You can make a MLT or LADSPA plugin. Both of these require C or C++ coding.
MLT support the following sample formats:

- signed 16-bit interleaved PCM
- signed 32-bit non-interleaved PCM
- signed 32-bit interleaved PCM
- 32-bit non-interleaved floating point
- 32-bit interleaved floating point
- unsigned 8-bit interleaved PCM

LADSPA supports only 32-bit non-interleaved floating point.

Video
-----
You make a MLT, frei0r, or FFmpeg/libavfilter plugin. These require C or
C++ coding.

MLT supports the following pixel formats:

- YUV 4:2:2, 8-bits per component, packed, in Rec. 601 or 709 colorspaces; along
with an optional, separate 8-bit alpha channel bitmap.
- RGB or RGBA, 8-bits per component, packed, in sRGB colorspace.

frei0r only supports 8-bit RGB(A).

Frontend
========
The frontend is implemented using
[Qt 6 QML/Quick](https://doc.qt.io/qt-6/qtquick-index.html).
You can also use Quick Controls, and Shotcut offers some custom controls as well.

First, you must create a folder to contain your QML. Your folder must be copied
to `share/shotcut/qml/filters` to install it.

Next, you need to create a filter metadata QML file that must begin with `meta`
and end with `.qml`. This QML must include QtQuick and org.shotcut.qml and 
create a Metadata object at the top level. Here is an example:

    import QtQuick 2.0
    import org.shotcut.qml 1.0

    Metadata {
        type: Metadata.Filter
        name: qsTr("Alpha Channel: Adjust")
        mlt_service: 'frei0r.alpha0ps'
        objectName: 'alphaChannelAdjust'
        qml: 'ui.qml'
    }

Finally, you can create the QML files for the panel and the VUI (video user
interface), which is a UI that appears atop the video player region. There is
still much to document to help create frontends, but we suggest you look at the
code in your Shotcut installation to learn for now.

Here are all of the Metadata properties available:

| Name | Type | Description |
|------|------|-------------|
| type | PluginType | Metadata.Filter (required) |
| name | string | The name as it appears to the user. Use qsTr() to make it translatable. (required) |
| mlt_service | string | This is the MLT service (plugin) identifier. (required) |
| objectName | string | This is the name that gets put into XML project file in case there may be more than one Shotcut filter for the same MLT service. It is optional but strongly advised especially if using MLT open source services. |
| needsGPU | bool | Wether this filter requires GPU processing - only available for Shotcut's branch of Movit. (default false) |
| qml | string | The relative file name of the UI QML for the filter panel. |
| vui | string | The relative file name of the UI QML for the video preview. |
| isAudio | bool | True if this is an audio plugin, otherwise video. (default false) |
| isHidden | bool | True to make this hidden from the filter menu. This is useful to keep a legacy frontend for existing projects but make a new implementation for new projects. (default false) |
| isFavorite | bool | True to make it appear in the favorites menu by default. (default false) |
| gpuAlt | string | Prevent a CPU-based filter from appearing when GPU processing is enabled by setting this to the name (mlt_service if not objectName) of the GPU alternative for this filter. |
| allowMultiple | bool | False to prevent the user from adding this filter more than once to a selected clip  or track. (default true) |
| isClipOnly | bool | True to prevent the user from adding the filter to a track or the timeline. (default false) |
{:.withborders}
