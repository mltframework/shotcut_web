---
layout: nosidebar
title: MLT XML Annotations
category: notes
---

Shotcut adds several XML elements and attributes to the [MLT XML](https://mltframework.org/docs/mltxml/) it generates.
Also, currently it needs many of these to properly map MLT objects into the Shotcut UI. Eveyhw

| **MLT Object** | **MLT Property** | **XPath** | **Description** |
|--------------|----------------|---------|---------------|
| tractor | shotcut | /mlt/tractor/property[@name = 'shotcut'] | Set to 1 on a to indicate that Shotcut can edit this MLT XML. |
| tractor | shotcut:virtual | /mlt/tractor/property[@name = 'shotcut:virtual'] | Set to 1 to force Shotcut to load this XML as a virtual clip. |
| tractor | shotcut:trackHeight | /mlt/tractor/property[@name = 'shotcut:trackHeight'] | Stores the track height in pixel units. |
| tractor | shotcut:scaleFactor | /mlt/tractor/property[@name = 'shotcut:scaleFactor'] | Stores the timeline zoom level as a real number. |
| tractor | shotcut:markers | /mlt/tractor/property[@name = 'shotcut:markers'] | Stores the timeline markers using a child `properties` element. |
| playlist | shotcut:name | //playlist/property[@name = 'shotcut:name'] | The name of the track in the multitrack timeline. |
| playlist | shotcut:audio | //playlist/property[@name = 'shotcut:audio'] | Set to 1 to indicate this is an audio-only track. |
| playlist | shotcut:video | //playlist/property[@name = 'shotcut:video'] | Set to 1 to indicate this is an audio/video track. |
| filter | shotcut:filter | //filter/property[@name = 'shotcut:filter'] | This is the Shotcut identifier for a filter. There can be more than one Shotcut filter UI for a single MLT filter. This provides disambiguation. The identifier comes from the filter's QML Metadata. |
| filter | shotcut:hidden | //filter/property[@name = 'shotcut:hidden'] | Set 1 to hide this filter instance in the Shotcut UI. |
| transition | shotcut:transition | //transition/property[@name = 'shotcut:transition'] | This is the Shotcut identifier for a transition. There can be more than one Shotcut transition UI for a single MLT transition. This provides disambiguation. A lot of times in the code, this is just checked to see if the MLT transition represents a transition that the user added instead of one that Shotcut adds automatically to provide audio mixing and video compositing. |
| producer | shotcut:comment | //producer/property[@name = 'shotcut:comment'] | Stores the user's comments about a clip or shot. |
| producer | shotcut:producer | //producer/property[@name = 'shotcut:producer'] | This is the Shotcut identifier for a producer. There can be more than one Shotcut producer UI for a single MLT producer. Or, there can be more than one MLT producer for a single Shotcut UI. This property can be used to specify the proper Shotcut UI in case it can not be inferred from the producer service name. |
| producer | shotcut_aspect_num | //producer[property/@name ='mlt_service' and (property/text() = 'avformat' or property/text() = 'qimage' or property/text() = 'pixbuf')]/property[@name = 'shotcut_aspect_num'] | The numerator of the display aspect ratio. |
| producer | shotcut_aspect_den | //producer[property/@name = 'mlt_service' and (property/text() = 'avformat' or property/text() = 'qimage' or property/text() = 'pixbuf')]/property[@name = 'shotcut_aspect_den'] | The denominator of the display aspect ratio. |
| producer | shotcut_sequence | //producer[property/@name = 'mlt_service' and (property/text() = 'qimage' or property/text() = 'pixbuf')]/property[@name='shotcut_sequence'] | Set to 1 to indicate this is an image sequence. |
| producer | shotcut_resource | //producer[property/@name = 'mlt_service' and (property/text() = 'qimage' or property/text() = 'pixbuf')]/property[@name='shotcut_resource'] | When working with image sequences, this stores the image file that the user selected since Shotcut will set the MLT resource property to something suitable for image sequences. |
| producer | shotcut:caption | //producer/property[@name = 'shotcut:caption'] | Used to provide a friendly name for a producer to be used for display to the user |
| producer | shotcut:detail | //producer/property[@name = 'shotcut:detail'] | Used to provide a more detailed description for the producer than the caption. For example if the caption is the file name, the detail could be the full file path |
| producer | shotcut:hash | //producer/property[@name = 'shotcut:hash'] | A MD5 hash of a media file (whole file if less than 2 MB, or first MB followed by last MB for files larger than 2 MB) |
| producer | shotcut:group | //producer/property[@name = 'shotcut:group'] | A numeric value for a unique group of clips, start and skipped values are unimportant
| producer | shotcut:skipConvert | //producer/property[@name = 'shotcut:skipConvert'] | If set 1, then Shotcut will not prompt to convert the file if it believes it to be variable frame rate or unseekable. |
| producer | shotcut:resource | //producer/property[@name = 'shotcut:resource'] | A copy of the resource property used by the proxy manager. |
| producer | shotcut:disableProxy | //producer/property[@name = 'shotcut:disableProxy'] | Set to 1 to indicate that proxy should not be generated for this producer. |
| producer | shotcut:originalResource | //producer[property/@name ='mlt_service' and property/text() = 'avformat']/property[@name = 'shotcut:originalResource'] | A copy of the `resource` property used by the Reverse action to restore original when reversing a reversed. |
| producer | shotcut:originalIn | //producer[property/@name ='mlt_service' and property/text() = 'avformat']/property[@name = 'shotcut:originalResource'] | A copy of the `in` property used by the Reverse action to restore original when reversing a reversed. |
| producer | shotcut:originalOut | //producer[property/@name ='mlt_service' and property/text() = 'avformat']/property[@name = 'shotcut:originalOut'] | A copy of the `out` property used by the Reverse action to restore original when reversing a reversed. |
| producer | shotcut:defaultAudioIndex | //producer[property/@name ='mlt_service' and property/text() = 'avformat']/property[@name = 'shotcut:originalOut'] | A copy of the `audio_index` property used by the audio levels/waveform generator. |
| producer | shotcut:proxy.meta | //producer[property/@name ='mlt_service' and property/text() = 'avformat']/property[@name = 'shotcut:proxy.meta'] | Indicates whether the MLT properties beginning with "meta." reflect the proxy (`1`) or source media. |
| various | shotcut:projectAudioChannels | //property[@name = 'shotcut:skipConvert'] | Sets the number of audio channels to use for this project. 2 is used if not specified. |
| various | shotcut:projectFolder | //property[@name = 'shotcut:projectFolder'] | Set to 1 to indicate this project uses a project folder. |
| various | shotcut:projectNote | //property[@name = 'shotcut:projectNotes'] | The text contents of the **Notes** panel. |
| filter | shotcut:animIn | //filter/property[@name = 'shotcut:animIn'] | The duration in frames for the simple keyframes' starting animation. |
| filter | shotcut:animOut | //filter/property[@name = 'shotcut:animOut'] | The duration in frames for the simple keyframes' ending animation. |
| filter | shotcut:backup | //filter/property[@name = 'shotcut:backup'] | Motion tracking uses this to save the property value of whatever parameter is affected before applying tracking results. It uses it to restore the state when re-apply tracking (different operation or tracker) or choosing to reset. |
{:.withborders}

**Warning**: All of these are subject to change as Shotcut is still in development.

In addition to these, Shotcut expects the following things in regular MLT XML:

* There should be a playlist element with the id "main bin" before the last tractor (if it exists) to load in the Playlist panel.
* There should be a playlist with the id "background" that contains a black color producer and it should be the first child track element of the last tractor.

**Note**: As of version 21.05.01 there is now a `chain` element instead of `producer` when the `mlt_service` is avformat.
So, all of the things pertaining to `producer` in the table above also apply to `chain`.
