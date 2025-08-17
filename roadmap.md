---
layout: page
title: Road Map
permalink: /roadmap/
category: other
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

In no particular order or estimated delivery time:

- duck audio
- quick effects VUI
- make it easy to add 0.5 or 1 second transition on timeline
- integration for external editor (e.g. Audacity, GIMP, etc. via configurable launcher and file watcher)
- open HEIC images (already works on macOS, work-in-progress in FFmpeg)
- SMPTE 2084 PQ HDR
- fullscreen playback on current/single screen with on-screen controls
- audio noise reduction
- project media management (automatically copy or move to project folder, automatically convert)
- set metadata (artist, title, etc.) in export
- archive project
- additional editing modes/operations (slip, slide)
- raw video processing - e.g. CinemaDNG
- multi-camera editing features
- convert generator UIs to QML
- add keyframes for generators
- add partik0l generator
- circle VUI control for Vignette and Crop: Circle
- generic filter UI (MLT service name and table of parameters)
- OpenFX and VST2 plugins using generic filter UI
- multi-track transition
- generic transition (MLT service name and table of parameters)
- add CMX EDL import
- add Kdenlive XML export
- add OpenTimelineIO import/export
- add presets to Filters search
- add option to view timeline waveform per channel
- add transitions to Playlist
- add speed param to Export > Codec
- add option to reduce number of encode threads for Convert, Reverse, and Proxy jobs
- improve the appearance of video-with-alpha clips by showing with checkered background in source player
- hardware accelerated decoding for GPU Effects
- background removal
- universal search
- read Kyno XML for name, comments, tags
- simple screen capture through libobs or ffmpeg
- add a base VUI that adds indicators for in and out points and a toolbar to invoke filters:
  Text, Size/Position/Rotate, Crop, Color, Chroma Key: Simple, White Balance
- improved UI for nested projects (MLT XML clips)
- multi-select support for Properties
- multi-select support for Filters
- option to include intermediate thumbnails in timeline
- ability to set the poster frame for a clip
- add Recent and Most Used tabs to Filters chooser
- typewriter effect for Text: Simple and Text: Rich
- more columns and sorting in Playlist
- clip markers or flags
- turn off all effects switch
- aspect ratio lock for VUI rectangle control - e.g. when used with Crop: Rectangle
- motion blur for motion-animated things like Text and Size/Position/Rotate
- 2.7K and 8K Video Modes
- reorganize Video Modes UI
- outline for Text: Rich
- face detection
- curves UI for color
- convert icons to SVG
- context-sensitive online help
- automatic silence detection/removal

See also the [Suggestion category in the Forum](https://forum.shotcut.org/c/suggestion/7).
