---
layout: page
title: Release Notes
permalink: /download/releasenotes/
category: other
---

<div data-aaad='true' data-aa-adunit='/22815767462/shotcutorg_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22815767462/shotcutorg_Mobile_300_1'></div>
<div data-aaad='true' data-aa-adunit='/22815767462/shotcutcom_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22815767462/shotcutcom_Mobile_300_1'></div>
<div data-aaad='true' data-aa-adunit='/22815767462/shotcutapp_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22815767462/shotcutapp_Mobile_300_1'></div>

These are brief notes about known problems and feature additions. See
[News]({{ "/blog" | prepend:site.baseurl }}) or the [git
log](https://github.com/mltframework/shotcut/commits/master) for more
information.

##### Release 24.04.28

- Fixed crash if the **Keyframes** panel is in a tab group along with **Filters**.
- Fixed **Elastic Scale** video filter can distort with preview scaling.
- Fixed dropping incompatible video file may not prompt conversion.
- Fixed color in **Properties > Convert > Best** if input video is BT.709 without signaling.
- Some fixes for **Settings > Audio Channels > 4 (quad)**.
- Fixed changes in **Filters** cannot after moving the clip on the **Timeline**.
- Fixed **Zoom Timeline to Fit** sometimes incorrect.
- Fixed batch analysis for **Stabilize** video filter on export with project folder.
- Upgraded MLT to version 7.24.0.
- Added **Ambisonic Encoder** audio filter.
- Added **View > Scopes > Audio Vector**.
- Added **View > Scopes > Audio Surround**.
- Added **Settings > Time Format** to affect everywhere that timecode is displayed or editable.
- Added a indication to the on-video control for the **Ambisonic Decoder** audio filter.
- Added **Edit > Undo** and **Redo** support for adding, removing, and changing **Keyframes** (work in progress) for the following filters:
  - Fade In Audio
  - Fade Out Audio
  - Gain / Volume
  - Brightness
  - Color Grading
  - Contrast
  - Fade In Video
  - Fade Out Video
  - Text: Rich
  - Size, Position & Rotate
  - White Balance
- Added **Apply Copied Filters** to **Timeline > menu > Edit** and context menu that works with multiple selected clips.

##### Release 24.02.29

- Fixed distortion caused by **Mixdown** audio filter.
- Fixed **Normalize: One Pass** audio filter maximizing levels at start of playback.
- Fixed old custom presets in text and timer video filters load with 0% opacity.
- Stop automatically grouping audio/video clips when **Detach Audio**.
- Fixed **Loop Selection** on the last clip of **Timeline** not looping.
- Fixed **Enter Full Screen** and **Preferences** shortcuts on macOS.
- Fixed **Properties > Convert** HLG HDR to to Rec. 709 SDR is not tone-mapping.
- Fixed problematic filename characters in **Settings > Video Mode > Custom Add**.
- Fixed disabling the last audio or video filter when there is a time filter in **Filters**.
- Fixed **File > Exit** is slow or hangs if a job in **Jobs** is paused.
- Fixed **Filters > + > Sets** adds audio filters in reverse order.
- Fixed **Wave** video filter distorts if **Settings > Preview Scaling** is on.
- Fixed incorrect gamma in preview player and **File > Export > Frame** when **GPU Effects** is on.
- Improved selection in **Timeline** after various operations.
- Improved behavior changing **Properties > Speed** with **Timeline > Ripple** on.
- Improved the speed of opening a timeline project.
- Upgraded macOS and Windows to Qt version 6.5.3, which changes the mininum macOS version to 11.
- Added support for AMD AV1 hardware encoder on Windows (`av1_amf`) and Linux (`av1_vaapi`).
- Added automatic vertical scrolling to **Timeline** when moving a track.
- Added **Settings > Audio Channels > 4 (quad/Ambisonics)**.
- Added **Ambisonic Decoder** audio filter that converts to binaural, stereo, quad, Ambisonic, or 5.1 surround. When Ambisonic mode is chosen, it is an Ambisonic panner.
- Added Ambisonic metadata to **Set Equirectangular** if there is a track with 4 audio channels.
- Added **Copy Parameters** to 360 video filters to use with **Ambisonic Decoder > Paste Parameters**.
- Added changing **Properties > Duration** on image clips on the **Timeline** (behavior depends on **Ripple** similar to changing **Properties > Speed** on an audio/video clip).


##### Release 24.01.28

- Fixed distort mode in **Size & Position** GPU filter.
- Fixed zombie values in **Time Remap** filter while working with keyframes.
- Fixed saving B frames in custom **Export** preset with hardware encoder.
- Added support for multiple selection to **Split At Playhead**.
- Added **Timeline > Edit > Split All Tracks At Playhead** <kbd>Shift</kbd>+<kbd>S</kbd>.
- Added **Edit > Undo** and **Redo** support for adding, removing, changing, and disabling **Filters**.
- Fixed 10-bit **Export** with NVENC (NVIDIA) encoders.
- Fixed proxy generation failing with NVENC if **Settings > Proxy > Use Hardware Encoder** is on.
- Fixed toggling **Export > Use hardware encoder** resets all options to defaults.
- Fixed **Export > Each Playlist Item > Directory** incorrectly shows a filename.
- Changed the name of the **Declick** time filter to **Declick Audio**.
- Fixed intermittent crash moving a clip on the **Timeline**.
- Fixed **Playlist > Select All** and **Remove All** are disabled until selection changes.
- Added **Player > Loop** <kbd>\\</kbd> and **Player > Set Loop Range** to the menu and player controls.
- Changed the player controls to automatically adapt to 2 rows so the **In Point** and **Selected Duration** show more reliably.
- Fixed some filter parameters' sliders may overflow using new keyframe easings that over- or under-shoot.
- Added **Timeline > Edit > Nudge Forward** <kbd>.</kbd> and **Nudge Backward** <kbd>,</kbd>.
- Added **Pause** and **Resume** to the context menu in **Jobs**.
- Changed the low memory warning dialog to automatically close itself when the free memory becomes high enough.
- Changed the low memory detection to automatically pause and resume a currently running job as the free memory becomes too low and then high enough again.
- Added **Settings > Backup** with options for:
  - **Manually**
  - **Hourly**
  - **Daily** (default)
  - **Weekly**
  This creates a backup of the current project file in a manner similar to **File > Backup and Save** except it is automatic now unless **Manually** is chosen.
- Added **File > Other Versions** sub-menu that tries to find similarly-named project files in the same folder create by Shotcut backup or recovery mechanisms.
- Added **Timeline > Selection > Group/Ungroup** <kbd>Ctrl</kbd>+<kbd>G</kbd>.
  This is basically a saved multi-selection system. So, the operations it supports are all those available for multiple selection. That does not include trim, **Filters**, or **Properties** at this time.
- Changed **Timeline > Detach Audio** to automatically create a group.
- Added **Settings > Player > Audio API** on Linux and Windows.
  Basically, this makes the `--SDL_AUDIODRIVER` command line option available in the **Settings** menu.
- Added a **Previous** button to **View > Application Log** dialog that goes to the log file created by the previous app session.
  Now, on startup, Shotcut makes a backup of `shotcut-log.txt` to `shotcut-log.bak`.
- Added a **Copy** button to all text viewer dialogs that does the same thing that the non-obvious Select All and Copy actions in the context menu.
- The **Jobs** log viewer now updates automatically and scrolls to the end if it is left open while a job is running.
- Fixed a crash in **Playlist > menu > Add Selected to Slideshow** when something is playing.
- Changed the **Slideshow Generator** to remember all options.
- Fixed **Layers > New > Emoji** is disabled in Glaxnimate on Windows.
- Fixed a possible crash in **Timeline > Split** or trim actions if the clips have certain filters with keyframes.
- Fixed some bugs in **Undo** after moving clips on the **Timeline**.
- Fixed proxy generation failing for videos with full range color on macOS with **Settings > Proxy > Use Hardware Encoder** turned on.
- Made the splitter between UI panels easier to find and grab to drag.
- Fixed a possible crash when opening project.
- Fixed sometimes (25 fps) frames are dropped and others repeated in **Export** on macOS.


##### Release 23.12.15

- Fixed crash on start on Wayland on Ubuntu 22.04 and 23.10 - may require installing `qt6-waland` (broke in v23.11).
- Fixed numerous audio filters missing on macOS/Intel (broke in v23.11).
- Fixed crash in **No Sync** video filter with new **Ease Back** and **Ease Elastic** keyframes.
- Fixed **Equalizer: Parametric > Preset** not loading (broke in v23.09).
- Fixed **Timeline** waveform is not updated when changing **Properties > Audio > Track**.
- Fixed `#filename#` and `#basename#` keywords in **Text: Simple** video filter with non-ASCII filenames on Windows.
- Fixed **Properties > View Bitrate** opens too big on high DPI screen.
- Fixed **Properties > View Bitrate > Save** image is not anti-aliased.
- Fixed **Slideshow Generator** not padding videos on mismatching aspect ratio (broke in v23.09).
- Fixed **Properties > Measure Video Quality** accuracy when **Color range** is **Full**.
- Fixed some minor memory leaks.
- Changed all NVENC hardware encoders in **Export** to use CQ instead of constant QP for VBR rate control.
- Ugraded FFmpeg to version 6.1
- Upgraded AV1 decoder `dav1d` to version 1.3.0 and AV1 encoder `libaom-av1` to version 3.8.0
- Upgraded `rubberband` audio pitch library to version 3.3.0


##### Release 23.11.29

- Fixed honoring the "Do not show this anymore" checkbox in the **Convert to Edit-friendly** dialog (configuration key `showConvertClipDialog`) (broke in v23.09).
- Fixed the new batch convert dialog (**View > Resources**) appeared instead of the old **Convert to Edit-friendly** one when dragging a *single* concerning clip to **Playlist** or **Timeline** (broke in v23.09).
- Fixed **Motion Tracker** filters are forgotten upon switching to **Source** player (broke in v23.09).
- Fixed **Mask: Simple Shape > Softness** not working on macOS (broke in v23.05).
- Fixed **Text: Simple > #createdate#** keyword deletes preceding text.
- Fixed a crash when opening **View > Scopes > Audio Loudness**.
- Fixed saving a favorite for **Filters > + > Sets**.
- Fixed marker at start of the next clip was deleted when using **Timeline > Edit > Ripple Trim Clip Out**.
- Fixed **Properties > Transition** changes were lost when **Undo** after trimming a clip's out point on the **Timeline**.
- Fixed a crash when **Undo** after trimming a transition that resulted in a new transition. With this fix Shotcut no longer permits creating a new transition within the same mouse drag that removes a transition.
- Fixed AMD (AMF) quality options in a saved **Export** preset shows up in the **Other** tab overriding **Codec > Quality**.
- Fixed **Timeline** appears all white on Qt 6.6.
- Fixed libvpx security vulnerability CVE-2023-5217.
- Fixed libwebp security vulnerability CVE-2023-4863.
- Added **Crop:Rectangle > Apply to Source** button.
  This button is only enabled when the aspect ratio of the source media matches your project's **Video Mode** because it is impossible to include the black padding that Shotcut adds to a source. This feature is the primary way to simply "crop a video." You do not need to use the timeline for this. You can simply:
  1. set **Settings > Video Mode** to **Automatic**,
  1. open a video file,
  1. add the **Crop: Rectangle** video filter,
  1. adjust the rectangle control in the player,
  1. click **Apply to Source** in the **Filters** panel,
  1. choose **Yes** in the dialog asking to change the **Video Mode**, and
  1. **Export**.
- Added **Opacity** to **GPS Text**, **Text: Simple**, and **Timer** filters.
- Improved performance of **Timeline > Zoom**.
- Added rectangular selection to **Timeline**.  
- Added **Settings > Timeline > Rectangle Select**.  
  This is on by default, and scrubbing with the mouse on the timeline requires clicking near the play head.
  When this is on, hold <kbd>Shift</kbd> to turn it off temporarily. When this is off, hold <kbd>Shift</kbd> to temporarily turn it on.
- Changed the **Smooth** keyframe type to avoid overshoots and cusps.  
  This only applies to new projects made with this and future versions. Thus, the behavior of smooth keyframes made with an earlier version remains the same for compatibility reasons.
- Added **Ease In**, **Ease Out**, and **Ease In/Out** to **Keyframes**.  
  This also changes the appearance of keyframes in the timeline view of **Keyframes** to make it more clear where the behavior applies - *between* keyframes. Remember this: when thinking about "in" or "out", for Shotcut "in" refers to the beginning of something - a clip, filter, or parameter between keyframes. And "out" refers to the end of something. So, this is not easing *into* a keyframe and easing *out of* a keyframe. Rather, it is easing *into* or *out of* the change/segment/span/tween of a parameter between keyframes.
- Added **Properties > View Bitrate...**.  
  If you have ever used the classic **Bitrate Viewer** for Windows and frustrated with the lack of updates or not available on your current OS, here you go.
- Added a **Track Auto Fade Video** filter. This can only be added to tracks and makes a dip to black or other color or fade in and out opacity for overlays to each clip.
- Changed **Export > Codec** and **Audio** to disable some options when a lossless-only or an intra-only codec is selected.
- Added **Settings > Timeline > Automatically Add Tracks**.  
  The defaults for this is off because adding tracks increases memory usage. Also, it does not automatically add a track if nothing is in the **Timeline** as the timeline is optional in Shotcut. Also, it does not automatically add a track when you open a project with no empty tracks. It only adds tracks when you add something to the timeline or move a clip between tracks.
- Fixed YouTube export preset is not H.264 high profile with some hardware encoders.
- Fixed a memory leak when using YADIF deinterlacers.
- Fixed color of export from still images when using full range and `pix_fmt=yuv444p`.
- Added a button in **Filters** to save a filter set and change the **Copy checked filters** button to not show a dialog.
- Added **Filters > Set > Glow Intensity**.  
  This demonstrates how you can mix a filtered output with the input to reduce it.
  Also, change the **Mask: From File > Treshold** to do a side-by-side comparison with and without the filter.
- Added **Split at Playhead** back into the timeline clip context menu.
- Changed the **Save** option in the low memory dialog to perform a backup and save to prevent breaking projects.
- Added support for `av1_nvenc` NVIDIA AV1 hardware encoder on Windows and Linux.
- Upgraded MLT to version 7.22.0.


##### Release 23.09.29

- Added **Grade %, Grade degrees, Cadence, Temperature, Vertical Speed, 3D Speed** to **GPS Text** video filter.
- Added **Timecode (non-drop frame), Creation date, File base name** to **Text: Simple** video filter.
- Added **Blur alpha** option to **Blur: Box** and **Blur: Gaussian** video filters.
- Fixed crash when changing **Properties > Rotation** on interlaced video.
- Fixed crash when changing **Properties > Video > Track** on video-only file.
- Added audio **Declick** filter (appears in Time category due to technical reason).
- Added **View > Resources...** to show all unique and sorted files in the **Playlist** and **Timeline**.
- Added dialog to convert multiple files as-needed on import.
- Added **Mode > Reset** to **Alpha Channel: Adjust** video filter.
- Fixed **Undo** after trimming an out point on **Timeline** with **Ripple All Tracks** enabled.
- Fixed H.264 **Export > Use hardware encoder** with **Codec > Rate control > Constant Quality** on macOS/ARM.
- Added **Preferences** to the menu on macOS.
- Fixed **Export** or turning off **Settings > Proxy > Use Proxy** if the file starts with a data stream such as videos recorded on Google Pixel phones, for example.
- Fixed memory leak in **Load Keyframes from Motion Tracker** in several video filters:
  - **Crop: Rectangle**
  - **GPS Text**
  - **Size, Position & Rotate**
  - **Spot Remover**
  - **Text: Rich**
  - **Text: Simple**
  - **Timer**
- Fixed reordering when there are many filters in **Filters**.
- Added keyframes to **Band Pass** and **Notch** audio filters.
- Added simple keyframes to **Speed: Forward & Reverse** and **Speed: Forward Only** time filters.
- Added keyframes for color parameters in several video filters:
  - **Crop: Circle**
  - **Crop: Rectangle**
  - **GPS Text**
  - **Text: Rich** (Background only)
  - **Text: Simple**
  - **Timer**
- Improved the the color dialog on GNOME.
- Fixed **Keyframes** panel not working properly when moved.
- Fixed **Add Selected to Slideshow** with **Timeline > Ripple All Tracks** misbehaves and should be ignored.
- Added **File > Backup and Save**.
- Added **Settings > Timeline > Scrolling** sub-menu with options:
  - **Center the Playhead**
  - **No** (new option)
  - **Page** (v23 default)
  - **Smooth** (old behavior)
- Fixed some memory leaks and random crashes due to memory management.
- Fixed overall speed of loading projects and editing that degraded in 2023 versions. (Existing projects must be saved after opening to upgrade them to benefit loading speed.)
- Changed **Export > Presets > audio > FLAC** to (raw) flac format instead of Matroska.
- Upgraded **Glaxnimate** to version 0.5.4 with limited support for After Effects projects (no plugins and no video or audio media - drawing and image animations only).
- Fixed some usability quirks with drag-n-drop and <kbd>Ctrl</kbd> multiple selection in the **Playist > Icons** view.
- New and improved installer for Windows.
- Improved the speed and memory of **Timeline > Append**, **Insert**, and **Overwrite**.
- Fixed **Filters > + > Time** is sometimes empty when player tab is **Source**.
- Fixed timeline marker may be incorrectly deleted when **Timeline > Ripple Markers** is on.
- Fixed unable to save export job **View XML** with `.mlt` file name.
- Changed **Missing Files > Search** to save the directory chosen.
- Added `--glaxnimate` command line option to launch Glaxnimate instead (handy for Linux AppImage and Flatpak).
- Fixed keyboard behavior of **Help > Actions and Shortcuts** on macOS.
- Improved the quality of **Settings > Proxy > Use Hardware Encoder** on macOS.


##### Release 23.07.29

- Fixed crash on startup on older Windows 10 computers that do not have Direct3D 11 (broke in v23.05).
- Added **Track Auto Fade** and **Track Seam** audio filters. These filters address an old problem where clicks and pops may be heard in export when switching between clips due to discontinuities in the audio stream. A recommended technique was to add a 2 frame Fade Audio Out and Fade Audio in filters on clips. **Track Auto Fade** automates that. **Track Seam** works on a similar level but rather attempts to do a smoothing between outgoing and incoming samples around edit points. Both of these new filters may ONLY be added to individual tracks--audio or video.
- Added **Transition type > Cut** to the **Slideshow Generator**.
- Added <kbd>Ctrl</kbd>+Wheel (<kbd>command</kbd> on macOS) to numeric fields to increment and decrement by a larger amount.
- Fixed shift-drag-drop from Windows Explorer to **Playlist** deletes the files! This is an old bug, and Shotcut is not deleting the files. But it accepts a move drop action for the purpose of reordering playlist items. However, doing so with a list of filenames makes Windows assume the receiving application did something appropriate with thes file and then... delete them on behalf of the app just to be sure?!? Smooth move. (Another Windows file manager *Directory Opus* does not exhibit this bad behavior.)
- Fixed another very old bug on Windows where sound does not follow the default output device, for example plugging headphones, until you restart the app. Please note that if you are using **Settings > Audio Channels > 6 (5.1)** after the default sound output changes, you will likely experience distortion in the audio playback until you restart the app.
- Added the `--SDL_AUDIODRIVER` command line option for Windows and Linux.
- Fixed **Timeline** scrubbing and skimming accelerate too much (broke in v23.06).
- Fixed **Stabilize** analysis jobs not working on a speed-adjusted timeline clip (broke in v23.05).
- Fixed the visibility of the cursor in the **Text: Rich** filter's editor (broke in v23.05).
- Fixed the up and down cursor keys not working in some numeric fields (broke in v23.05).
- Fixed seeking on the new **Speed: Forward Only** and **Speed: Forward & Reverse** filters.
- Fixed appending to **Playlist** from clipboard with nothing yet opened in the **Source** player.
- Fixed UI in macOS shows white blocks on startup.
- Fixed the **Export > Audio > Quality** range for the `aac` codec.
- Fixed the color level of RGB and RGBA sources (e.g. images) with **GPU Effects**.
- Fixed trying to drag a keyframe vertically may snap changing its horizontal position.
- Fixed clicking **OK** in a color dialog on Windows without changing anything resets the alpha to 255.
- Fixed the buttons in the **Delete Filter Set** confirm dialog are hidden if the name is long.
- Fixed crash adding a GPU filter to **Timeline > Output** by not showing GPU filters for that selection.
- Fixed top-field-first interlaced output.
- Updated Qt libraries to version 6.4.3.
- Updated libebur128 to version 1.2.6.
- Updated rubberband library to version 3.2.1.
- Updated MLT to version 7.18.0.


##### Release 23.06.14

- Fixed H.264 output when using **Export > Use hardware encoder** with NVIDIA (`h264_nvenc`)`.
- Fixed file dialogs in filters crash Shotcut in Linux AppImage or on KDE.
- Fixed crash in **Text: Rich > File > Open** when choosing a text file.
- Fixed crash changing **Video Mode** with **Count** generator with **GPU Effects** on.
- Fixed crash when trying to **Open MLT XML as Clip** (nest project) with **GPU Effects** on.
- Fixed loading JPEG images over 32 megapixels.
- Fixed player not working if **Settings > Player > External Monitor** was used in a previous version.
- Improved the smoothness of fast forward (up to 64x) playback.
- Improved **Timeline** performance and automatic scrolling.
- Fixed **Timeline > Replace** on a clip breaks some of its video filters.
- Fixed custom keyboard shortcuts for actions in the **Timeline** or **Keyframes** context (right-click) menu.
- Fixed **Keyframes > Add Keyframe** in the **Mask: Simple Shape** filter.
- Fixed changing **Keyframe Type** or a keyframe's time position in the **Mask: Simple Shape** filter.
- Fixed **Properties > Copy Fill File Path** uses incorrect directory separator on Windows.
- Fixed chroma bleeding on some (e.g. Ut Video) interlaced 4:2:0 files.


##### Release 23.05.14

- Restored **Settings > Theme**.
- Fixed a crash in **Stabilize** video filter during preview.
- Fixed bold fonts not working correct in text filters.
- Fixed some audio and export issues with video clips with no audio.
- Fixed **Spot Remover** video filter during preview.
- Fixed filter UI not working after changing **Settings > Audio Channels**.
- Fixed translations (**Settings > Language**) not loading completely.
- Fixed the order of **Recent** revered when migrated from previous version.
- Fixed saving a filter set with the same name.
- Fixed a crash when adding a filter to **Output** of an empty **Timeline**.
- Added a **GPU** category to the filter chooser.
- Allow adding any non-GPU video filter with **GPU Effects** on.


##### Release 23.05.07

- Restored **Settings > GPU Effects**.
- Restored **Lens Correction** video filter.
- Added **Motion Tracker** video filter.
- Added **Speed: Forward Only** and **Speed: Forward & Reverse** filters.
- Added saving and loading filter sets: **Filters > + > Sets**.
- Added an **Add To Timeline** button to many things in **Open Other**.
- Added a visual rectangle control to the **Mask: Simple Shape** filter.
- Holding <kbd>Shift</kbd> while dragging a point in the **Corner Pin** filter moves all corners together.
- Added faster and better quality YADIF deinterlacer plus addition of BWDIF deinterlacer.
- Added 10-bit export presets under the "ten_bit" category.
- Added support for Intel ("qsv") AV1 and VP9 hardware encoders on Windows including 10-bit for AV1.
- Less audio crackling in exports when audio source is not 48000 Hz sample rate.
- Less audio crackling upon start of playback in preview.
- Upgraded *Qt* to version 6.4.
- Upgraded *Glaxnimate* to version 0.5.3, which fixes some bugs and can animate motion along a drawn path.
- Upgraded *FFmpeg* to latest version 6.
- Upgraded *MLT* to latest version 7.16.0.
- Upgrade *AV1* codecs to latest versions.
- **Stabilize** and **Normalize: Two Pass** on a timeline clip is faster.
- The **Lens Correction** video filter is back.
- Added **Settings > Language > Hebrew**.
- **Open Other > Text** now has a **Rich** option.
- Changed **File > Export > Video** and its shortcut to be the same as clicking **Export > Export File**.
- Fixed seeking on raw FLAC audio files.
- Fixed **Record Audio** breaks the state of the player's mute toggle when you unmute the Shotcut audio during recording.
- Fixed using the mouse wheel to scroll the timeline horizontally on macOS and Linux.
- Fixed image padding not transparent during a transition.
- Added low disk space warnings to the Properties > Convert and Reverse actions.
- Fixed loading projects made with version before 19.06 using comma for decimal symbol.
- Fixed chroma bleeding for interlaced YUV 4:2:0 video sources.
- Fixed Shotcut became very slow if something wrong and very large was saved to **Recent**.
- Removed **Settings > Theme**.
- Removed **Settings > Player > External Monitor** with a system monitor.
- Removed **Settings > Player > Gamma** with GPU effects on.
- Removed **Settings > Display Method** on Windows and macOS.
- Removed export progress on the Windows taskbar icon.
- The minimum version for Windows is now Windows 10.
- The minimum version of our non-Flatpak Linux binaries is now based on Ubuntu 20.04 LTS, which uses glibc 2.31.
- The macOS app is now universal and runs on either Intel or Apple Silicon without Rosetta.


##### Release 22.12.21

- Fixed the keyframes button sets size and position parameters to all zeroes in the following filters (broke in v22.11):
  * **Blur: Pad**
  * **Crop: Rectangle**
  * **Size, Position & Rotate**
  * **Spot Remover**
  * **Text: Rich**
  * **Text: Simple**
- Fixed a crash when changing a parameter in the **Pitch** audio filter (broke in v22.11).
- Fixed a crash on **File > New** or **File > Close** while also playing (bug in v22.09).
- Fixed a memory leak in slideshow dialog and transition properties preview (bug in v22.09).
- Fixed **Time Remap** video filter disables a **Crop: Source** filter.
- Fixed making a gradient stop transparent (alpha value 0) in various filters:
  * **Audio Level Visualization**
  * **Audio Light Visualization**
  * **Audio Spectrum Visualization**
  * **Audio Waveform Visualization**
  * **GPS Graphic**
  * **Gradient**
- Added new seek actions to the **Player** menu:
  * Forward Jump <kbd>Alt</kbd>+<kbd>Page Down</kbd> (<kbd>option</kbd>+<kbd>page down</kbd> on macOS)
  * Backward Jump <kbd>Alt</kbd>+<kbd>Page Up</kbd> (<kbd>option</kbd>+<kbd>page up</kbd> on macOS)
  * Set Jump Time <kbd>Ctrl</kbd>+<kbd>J</kbd> (<kbd>command</kbd>+<kbd>J</kbd> on macOS)
- Added **Cycle Marker Color** with default keyboard shortcut <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>M</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>M</kbd> on macOS).
- Added **Advanced > Sample rate** to the **Properties > Convert** dialog.


##### Release 22.11.25

- Fixed including sub-project with **Open MLT XML as Clip** breaks the project (broke in v22.10).
- Fixed custom transition preview in **Properties** degrades quality and accuracy of the transition preview in the player (bug in v22.09).
- Fixed memory leak in the transition **Properties** and **Slideshow Generator** previews (bug in v22.09).
- Fixed crash when using the `--appdata` command line option (broke in v22.09).
- Fixed dragging multiple selection in **Timeline** does not show all selected clips (broke in v22.09).
- Fixed huge memory consumption when using certain filters before keyframes on the **Size, Position & Rotate** filter: **Corner Pin**, **Mask: Simple Shape**.
- Fixed <kbd>Alt</kbd> (<kbd>option</kbd> on macOS) not suspending snapping in filter rectangle controls.
- Fixed updating the filter UI value when deleting a keyframe.
- Improved sound quality of **Pitch compensation** and **Pitch** audio filter.
- Added **Reset on discontinuity** option to the **Normalize: One Pass** audio filter.


##### Release 22.10.25

- Fixed translations not updated (broke in v22.09).
- Fixed crash in **Size, Position & Rotate** filter when size approaches zero, for example when editing a size numeric
  field (broke in v22.09).
- Fixed bitrate in some **Export** presets such as VP8, VP9, D10, and XDCAM (broke in v22.09).
- Fixed **Timeline > Lift** and **Delete** not working with no clip selected (broke in v22.09).
- Fixed **Transition > Properties** resets the **Invert** and **Softness** options (broke in v22.09).
- Fixed an incorrect timecode appears at 2 minutes in 24 or 23.98 fps.
- Fixed **Timeline > Select Clip Above** and **Select Clip Below** not working with no clip selected.
- Fixed incorrect resulting aspect ratio when changing **Export > Video > Resolution** and pixel aspect ratio is not square.
- Fixed **Properties > Measure Video Quality** on Windows.
- Fixed **Fade Out Video** filter not working after trimming the in point.
- Fixed updating an animation **Properties > Duration** after changed in Glaxnimate.
- Fixed ripple trim on the in point of a clip that is at the very beginning (00:00:00:00) of the **Timeline**.
- Fixed adjusting keyframes of the second clip when a trimming the in point of a transition.
- Fixed **Keyframes** UI when using **Timeline > Trim Clip In** menu-item/action/shortcut (not interactive trim).
- Fixed opening a MLT XML file with a `%` in its path or name.
- Fixed keyframes after an undo and redo upon making a transition while trimming the in point of a clip.
- Finished the menu technology updates (marker context, rich text editor) that were mostly done in v22.09.23.
- Added icons for the 360 video filters. 
- Disallow allow adding **Filters** to a device or live input since this is not working and could interfere with integrity of capture.
- Increased the maximum values in the **Mask: Simple Shape > Horizontal** and **Vertical** video filter.
- Changing **Timeline > Zoom** no longer pauses playback.


##### Release 22.09.23

- Added limited support for reading WebP Animation.
- Show audio-clips without album art as a checkboard for transparent instead of white.
- Added the **GPS Graphic** video filter (see its presets).
- Added the `gopro2gpx` utility to let you export a GPX file from a GoPro video using
  **Properties > menu > Export GPX**. This saves the `.gpx` in the same folder as the video file with the same name
  but different exension.
- Added **Fisheye** video filter (see its presets).
- Fixed opening files with a `%` in their path or name.
- Added snapping to the playhead to **Keyframes**.
- Added **Help > Actions and Shortcuts**:
  - Provides a unified action search and shortcut editor.
  - Replaces the old **Keyboard Shortcuts...** item in the **Help** menu and takes its keyboard shortcut <kbd>?</kbd>.
  - <kbd>/</kbd> is also a default shortcut, and either shortcut can be changed.
  - Searches both action name and shortcut.
  - Press <kbd>Return</kbd>/<kbd>Enter</kbd> within search to move focus to the list of actions.
  - Press <kbd>Return</kbd>/<kbd>Enter</kbd> on a selected action to trigger it and close the dialog.
  - <kbd>Shift</kbd>, <kbd>Ctrl</kbd>, or <kbd>Alt</kbd> + <kbd>Return</kbd>/<kbd>Enter</kbd> on a selected action to
    trigger it and NOT close the dialog.
  - Double-click an action to trigger it but NOT close the dialog.
  - The dialog is not modal so you can leave it open and to the side while working.
  - Press <kbd>Esc</kbd> when the dialog has focus to close it.
  - Press <kbd>F2</kbd> when an action is selected to edit its first shortcut.
  - Single-click a selected shortcut to enter edit mouse using the mouse. This means you typically need two single
    clicks: one to select, the second to enter into edit mode.
  - You can <kbd>Tab</kbd> out of edit mode to navigate focus to the apply button and press <kbd>Space</kbd> to
    trigger the apply. It is intentional that you cannot assign <kbd>Tab</kbd> as a keyboard shortcut to an action.
  - There are some keyboard buttons such as J/K/L that are reserved and cannot be used in a shortcut.
    You will see an error message when you try to apply it.
  - You can define up to 2 shortcuts per action! You may want to leave the default as well as add your preferred shortcut.
  - A big portion of the UI had to be rewritten to support this. As a result:
    - All panel (hamburger) menus are consistently on the left/first.
    - Panel-specific Options sub-menus were moved to **Settings** main menu.
    - The keyboard shortcut to switch the player between **Source** and **Project** is now <kbd>P</kbd>.
    - Various hidden or under-exposed actions now have a menu item somewhere including a new **Player** main menu.
    - Many translations will be lost.
    - The default shortcuts to change the current track now require <kbd>Ctrl</kbd>+<kbd>Alt</kbd> in addition to
      cursor up and down.
- Improved support for custom video transitions:
  - There is a folder now in the App Data Directory named `transitions` where you can store these.
  - All files in the `transitions` folder are listed in transition **Properties**, the **Mask: From File** video filter,
    and the **Slideshow Generator** dialog.
  - Added a favorite button in transition **Properties** and **Mask: From File** that copies your chosen custom file to
    the `transitions` folder.
  - Added a quick preview to transition properties.
- Added the ability to drag-scroll/pan using the middle mouse button (press mouse wheel) to **Timeline**,
  **Keyframes**, and the player when zoomed in.
- Improved the **Filters** picker:
  - Added translatable keywords to facilitate search. For example, "transform" includes **Size, Position & Rotate**.
  - Added the English filter name in an untranslatable manner to the keywords so people using a translation can more
    more easily find things based on proliferic English advice.
  - Added support for a small animated icon.
- Added the alpha **Operation**, **Reverse**, and **Invert** parameters to the **Mask: Draw** video filter.
- Added **Settings > Reset...** to reset _all_ settings including hidden ones.
- Fixed **Move Track Up** or **Move Track Down** breaks the order of blending/compositing.
- Fixed sometimes a date does not appear in **Playlist**.
- Fixed **Old Film: Scratches** video filter not working (broke in version 22.04).
- Fixed **Stabilize** video filter uses invalid analysis data after pasted.
- Fixed **File > Open MLT XML as Clip...** changes the current Video Mode.
- Fixed audio artifacts introduced after splitting a clip that has been converted or reversed using
  the **better/large/DNxHR** option.
- Fixed **Text: Rich** filter's toolbar may not reflect the current text color.
- Deprecate and hide the **Lens Correction** video filter since it is low quality (no interpolation) and now there is **Fisheye**.
- Upgraded FFmpeg to v5.1.0
- Upgraded dav1d AV1 decoder v1.0
- Upgraded AOM AV1 encoder to v3.4.0
- Upgraded libvpx VP8/9 encoder to v1.12.0
- Upgraded VMAF to v2.3.1
- Upgraded Glaxnimate to v0.5.1


##### Release 22.06.23

- Added **Edit...** to **Timeline > Output > Properties**.
- Added **Timeline > menu > More > Align To Reference Track** to synchronize clips based on similar audio.
  See its [documentation](https://forum.shotcut.org/t/align-to-reference-track/33893).
- Added support for reading Lottie and rawr JSON animation formats.
- Added **Open Other > Animation**.
- Added a **Mask: Draw (Glaxnimate)** video filter.
- Added **Glaxnimate** vector animation tool with a video preview of Shotcut. Known issues:
  - Preview on macOS may stop working due to out-of-resources until reboot.
  - Some Lottie animations make export fail. The one that I have a problem with shows warnings upon opening in Glaxnimate.
  - Glaxnimate python not working in AppImage and currently require some external dependencies on Linux and macOS.
- Added support for **Keyframes** to the following audio filters:
  - **Low Pass**
  - **High Pass**
  - **Reverb**
- Added keyboard shortcut <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>A</kbd> to select all clips on the current track.
  (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>A</kbd> on macOS)
- Added an options dialog to **File > Export > Markers as Chapters** to exclude colors or include range markers.
- Added support for fractional display scale (125%, 150%, 175%) on Windows.
- Fixed **Text: Rich** does not export the same as preview on system with fractional display scale on Windows.
- Fixed **Record Audio** and **Open Other > Audio/Video Device** crashing on macOS due to insufficient entitlements.
- Fixed **Time Remap > Image mode > Blend** not working.
- Fixed a crash combining two **Size, Position & Rotate** filters with a mask filter on a square video mode.
- Fixed a possible crash with an odd width video.
- Fixed dragging a clip leftward beyond other clips with **Timeline > Ripple** turned on.
- Fixed changing the color of a color clip resets a custom name.
- Fixed changing **Properties > Speed** drops a **Crop: Source** filter if added.
- Fixed prompting for a duration and possibly a crash when dragging non-seekable files to **Playlist**.
- Fixed filters on a clip are removed when **Undo** after a change to **Properties**.
- Fixed **File > Export > Markers as Chapters** incorrect text encoding resulting in corrupt unicode characters.
- Fixed video track blending may be broken after moving a track.
- Fixed repairing a project with **Settings > Proxy > Use Proxy** on saves proxy file paths into repaired project file.
- Fixed **Ripple Markers** not working with ripple trimming.
- Fixed trimming a clip on timeline may change the length of a neighboring clip.
- Converted the build system from qmake to CMake (qmake is removed).

  
##### Release 22.04.25

- Fixed **Open Other > Audio/Video Device** and **Timeline > Record Audio** not working on macOS.
- Fixed **Open Other > Color Bars** not appearing on macOS.
- Fixed **Filters > Paste filters** for some filters (broke in v22.03.30):
  * Normalize: Two Pass
  * Chroma Key: Simple
  * Crop: Source
  * Mask: Apply
  * Time Remap
- Fixed **Export > Color range > Full** if resolution or frame rate were changed.
- Fixed **Export > Codec > Rate contol > Quality-based VBR** with videotoolbox_hevc on macOS.
- Fixed changing **Export > Format** does not suggest a file name extension.
- Fixed keyframes for **Corner Pin** video filter.
- Fixed keyframes for **Rotate** parameter of the **Size, Position & Rotate** video filter after trimming the clip.
- Fixed **Size, Position & Rotate** video filter UI incorrect for non-square pixels.
- Fixed running **Analyze** more than once in **Normalize: Two Pass** audio filter.
- Added **Detected Loudness** and **Normalization Gain** status fields to **Normalize: Two Pass** audio filter.


##### Release 22.03.30

- Fixed converting full color range 10-bit video to limited MPEG range.
- Fixed very choppy playback with certain weird or /unreduced-fraction framerates.
- Fixed **Video Mode > Automatic** when using a webcam/video-device input.
- Fixed **Position** and **Size** in **Crop: Rectangle** video filter may become read-only.
- Fixed **Gradient** video filter when a color alpha value is not fully opaque.
- Fixed marker duration may change when dragging to change its starting time.
- Fixed **Size, Position & Rotate > Zoom** may change when changing the player zoom level.
- Fixed accidentally changing an unmodified clip-only project by opening a new media file.
- Fixed changing **Properties > Speed** may overwrite and does not honor **Ripple** mode.
- Fixed a transition may show "INVALID" after you undo removing it.
- Fixed **Presets** for the **Equalizer: 3-Band** audio filter not working.
- Fixed **Blur: Box** filter creates darker edges.
- Fixed **Reduce Noise: Quantization** video filter overwrites alpha chnanel.
- Fixed **Properties > Audio > Sync** not showing change after reloading properties (broke in v22.01).
- Restored the **Use Higher Performance Waveforms** option in the **Timeline** menu.
- Changed `melt` command line tool to no longer be locale-sensitive by default.
- Changed **Q** in **Equalizer: Parametric** to **Bandwidth** in octaves.
- Changed background capture jobs to use a high process priority.
- Changed **Paste Filters** to not paste a clip-only filter onto a track.
- Changed **Paste Filters** to not paste a filter that can only be added once.
- Removed **Timeline > Copy Timeline to Source** (use Markers instead).
- Stop showing the **Convert to Edit-Friendly** dialog when opening a HLG HDR video.
- Upgraded libraries:
  - FFmpeg 5.0
  - MLT 7.6.0
  - frei0r 1.8.0
  - Rubberband 2.0.2
  - VMAF 2.3.0
  - Qt 5.15.2 for Intel macOS - **macOS 10.14 is now the minimum macOS version.**
- Improved A/V synchronization in **Properties > Reverse**.
- Improved webcam/video-device capture on macOS.
- Improved the accuracy of **View > Scopes > Audio Peak Meter**.
- Improved speed of **Old Film: Projector** video filter.
- Added **Export > Advanced >> Video > Color range**.
- Added multi-threading for all implicit video scaling including **Settings > Preview Scaling**.
- Added multi-threading to some video filters:
  - **Blur: Box**
  - **Blur: Gaussian**
  - **Color Grading**
  - **Invert Colors**
  - **Mask: From File**
  - **Old Film: Grain**
  - **Old Film: Scratches**
  - **Old Film: Technocolor**
  - **Reflect**
  - **Sepia**
  - **Sketch**
  - **Spot Remover**
  - **Threshold**
  - **Vignette**
  - **Wave**
- Added track reordering by drag-n-drop a track header and the **Timeline** menu:
  - **Move Track Up**: Alt+Shift+Up (shift+option+up on macOS)
  - **Move Track Down**: Alt+shift+Down (shift+option+down on macOS)
- Added **View > Notes** panel with keyboard shortcut Ctrl+Shift+3 (shift+command+3 on macOS).
- Added **Convert to Edit-friendly** when opening a HDV video file.
- Added a **Record Audio** button to the **Timeline** toolbar:
  - It chooses an audio device based on either first found or last used in **Audio/Video Device**.
  - It uses the current track if it is audio and not empty at the playhead and beyond.
    Otherwise, it adds an audio track.
  - It does not prompt for a save file name when a project folder has been established.
- Added audio filter **Stereo Enhancer**.
- Added tooltips to **Timeline** clips.
- Added **Markers > menu > Add Markers Around Selected Clips** with keyboard shortcut Alt+M (option+M on macOS).
- Added an option to the Windows installer to register the `.mlt` filename extension to open with Shotcut.


##### Release 22.01.30

- Fixed **File > Export > Markers as Chapters** if project contains transitions.
- Fixed a possible crash moving clip inside blank on same track.
- Fixed a crash when dropping a `.mlt` MLX XML file from a file manager to **Playlist** and then **Timeline**.
- Fixed the appearance of Shotcut's description in Windows Task Manager (broke in v21.12).
- Fixed a crash on undo insert/overwrite after undo add transition.
- Fixed **Hold** undo in **Noise Gate** audio filter.
- Fixed audio mutes after setting an in or out point when playing not 1x forward in **Source**.
- Fixed the **Segment Gap** goes to zero when reloading an **Audio Spectrum Visualization** filter.
- Fixed **Mask: Simple Shape > Rotate** not working in presets.
- Fixed page up/down incorrect when **Current position** (timecode) spin box has focus.
- Fixed extra blanks being removed when drag moving a clip right with **Ripple** turned on.
- Fixed paths to additional files used by some filters not saved as relative on Windows.
- Fixed tiny clips created when trimming on the **Timeline** with **Ripple All Tracks** turned on.
- Fixed filters when **Export > From** is **Source** or **Each Playlist Item** (broke in v21.05).
- Fixed removing simple keyframes.
- Fixed the **Text: Rich** video filter shows the editor when playhead is not over selected clip.
- Fixed **Properties > Menu > Measure Video Quality** (VMAF) not working on Windows.
- Fixed a possible crash in **Glitch** video filter.
- Fixed a crash changing **Properties > Video > Rotation** when the clip has a transition.
- Fixed the **Mask: From File** video filter's **Reverse** option not working as intended.
- Fixed broadcast standard non-integer frame rates (e.g. 30000/1001) for Matrosk and WebM files.
- Fixed a bad job percentage complete when making a proxy or running a convert job on a GoPro video file.
- Reduced audio distortion in **Properties > Reverse** for the best/MKV option.
- Removed **Use Higher Performance Waveforms** (default is on but still in configuration).
- Added a warning dialog when trying to use simple keyframes when advanced keyframes are being used.
- Changed to remove full keyframes when switching to simple keyframes.
- Added a warning dialog when trying to use advanced keyframes when simple keyframes are being used.
- Changed to convert simple keyframes to advanced keyframes.
- Changed tooltips on the **Timeline** and **Keyframes** toolbar to simplify and remove shortcuts from translated strings.
- Improved compatibility of VA-API hardware encoding on Linux, particularly on Wayland.
- Updated AV1, VP8, and VP9 encoders to latest releases.
- Updated Rubberband (audio pitch library) to latest release.
- Added an **Equalizer: 3-Band (Bass & Treble)** audio filter.
- Removed the old **Bass & Treble** audio filter.
- Added an **Equalizer: 15-band** audio filter.
- Added an **Equalizer: Parametric** audio filter.
- Added **File name extension** to the **Add Export Preset** dialog box.
- Added **Segments** parameter to the following video filters:
  - **Audio Level Visualization**
  - **Audio Spectrum Visualization**
  - **Audio Waveform Visualization**
- Added **Settings > Job Priority** to the main menu with a **Normal** option to improve performance on Intel 12th
  generation CPUs with E-cores. **Low** priority is the default as it has always been and is generally recommended.
- Added Wayland compatibility to Flatpak for Linux.

##### Release 21.12.24

- Fixed a bug that was found in version 21.12.21 that affected the **video blending** between two non-opaque image/video sources. 
- Added video filter **Audio Level Visualization**.
- Added segmented bar type of display to the **Audio Spectrum Visualization** filter.
- Added snapping for markers - dragging clips or their edges snaps to markers and dragging markers snaps to clip edges or playhead.
- Changed **Detach Audio** to separate the audio and video filters.
- Fixed audio was muted after changing view layout or window size when playback speed is fast forward or rewind.


##### Release 21.12.21

- Fixed **Timeline > menu > Track Operations > Insert Track** breaks video track blending (broke in v21.10).
- Fixed copy and paste multiple clips from another project can change the video mode (broke in v21.10).
- Fixed **Open Other > Audio/Video Device** capture (broke in v21.10).
- Fixed a crash when changing **Properties** of **Audio/Video Device**.
- Fixed a crash in **Old Film: Projector** video filter with 360p preview scaling.
- Fixed a possible crash in the **Mosaic** video filter when width or height is 0.
- Fixed the output alpha channel of **Timeline** with more than one video track (thanks @andre-caldas!).
- Fixed the **Time Remap** video distorts audio when the speed is zero and resampling.
- Fixed color range of **LUT (3D)** video filter on transitons with full range clips.
- Fixed a possible crash in **Audio Loudness** scope.
- Fixed window is initially all white on Windows.
- Fixed a small white window appears on startup on Windows.
- Fixed delete marker keyboard shortcut may delete wrong marker.
- Fixed unwanted keyframes appear in **Corner Pin** video filter when trimming in.
- Fixed ugly pink video, not black background after undo a remove/ripple-delete.
- Fixed **Export > From > Marker** may export from wrong region marker.
- Fixed keyframes can sometimes be dragged before previous or after next.
- Fixed double-clicking a keyframe does not delete it (broke in v20.11.28).
- Fixed incorrect filter parameter values after the last keyframe after a **Split** operation.
- Fixed a crash pasting from the clipboard to an empty timeline.
- Fixed inaccurate frame rate override with many decimal places in **Properties > Convert**.
- Fixed incorrect colors when reloading the **Audio Spectrum Visualization** filter UI.
- Fixed being able to select the last filter when there are many **Filters** applied.
- Removed some harmless error messages in logs.
- Changed **Properties > Audio > Sync** to hide when it is not applicable (no video track in the clip).
- Change the units of the **Hue** parameter in the **Hue/Lightness/Saturation** video filter to degrees.
- Improved accuracy of bubble help when trimming in **Timeline** and **Keyframes**.
- Improved the accuracy and snap reliability of the 10 and 20-pixel grid player overlays.
- Improved various mouse and keyboard operations in **Timeline** and **Keyframes**.
- Improved the VMAF speed and accuracy of the **Properties > Measure Video Quality...**.
- Added **Properties > Rotation** for video clips.
- Added support for keyframes to the **Hue/Lightness/Saturation** and **Chroma Hold** video filters.
- Added **View > Markers** panel with search, seeking, and editing.
- Added previously used colors to the marker context menu.
- Added keyboard shortcuts <kbd>&lt;</kbd> and <kbd>&gt;</kbd> to seek between markers.
- Added **File > Export > Markers as Chapters...**.
- Added a file save dialog upon repairing a project file to prevent overwriting a previous repair.
- Added a **Ripple markers with edits** button to the **Timeline** toolbar.


##### Release 21.10.31

- Fixed export to MP4 or MOV may not give constant frame rate (broke in v21.09.20).
- Fixed **Properties > Speed** with GoPro `.LRV` proxy file (broke in v21.09.20).
- Fixed **Export > Reset** did not deselect a preset.
- Changed <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>V</kbd> in **Text: Simple** to paste.
- Changed the color of an alert vs. the proxy/preview-scaling status messages.
- Increased the time for some messages, and added the ability to click a message to dismiss it.
- Upgraded FFmpeg to version 4.4.1.
- Added help message boxes to the **Mask: Simple Shape**, **Mask: From File**, and **Text: Rich** filters.
- Added **Properties > Comments** for color clips.
- Added a **Mask: Chroma Key** filter for convenience, for example secondary color correction.
- Added support for multiple selected clips to the timeline **Cut**, **Copy**, **Paste**, **Overwrite**, and **Append**
  operations.  
  **Copy** exclusively uses the system clipboard in this mode and does not show in the **Source** player.
- Added **Markers** to the **Timeline**!  
  - Click toolbar button or press <kbd>M</kbd> the first time to add a marker at the playhead (current position) with no dialog.
  - Markers appear in the time ruler/track/row at the top of the **Timeline**.
  - A marker shows a tool tip with its name and time when you hover the mouse over it.
  - Click a marker to seek to it.
  - Click toolbar button or press <kbd>M</kbd> when the playhead is on the exact start time of a marker to open the **Edit** dialog where you can change the name, color, start, and end times.
  - A color change is remembered for all new markers until changed.
  - Right-click a marker to open its context menu to **Edit** or **Delete** a marker.
  - Press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>M</kbd> when the playhead is on the exact start time of a marker to **Delete** it.
  - Drag a marker to move it.
  - <kbd>Ctrl</kbd>+drag (<kbd>command</kbd> on macOS) a marker to changes its duration (a marker with a duration longer than one
    frame is also called a **Range**).
  - **Export > From** lists all **Range**s.
  - Markers are saved to the project file and reloaded with the project XML in a `<properties name="shotcut:markers">` element.
  - Marker operations support **Undo** and **Redo**.


##### Release 21.09.20

- Fixed dragging to **Timeline** broken if there is MLT XML on the clipboard (broke v21.08.29).
- Fixed seeking backwards after seeking to the end (broke in v21.08.29).
- Fixed **File > Save** immediately after **File > Close** can corrupt a saved project.
- Fixed **Add Custom Video Mode > Frames/sec** was not accepting some legitimate values.
- Fixed encoding HEVC without hardware encoder (x265) would always output 10-bit instead of 8 (broke in v20.11.28).
- Changed **Copy the filters** to only copy enabled filters.
- Changed fading on the Timeline to automatically fade the opacity when it is not the bottom video track.
- Added **360: Equirectangular to Stereographic** video filter.
- Expire old QML cache items at startup to reduce app data footprint.
- Improved performance of **360:** video filters.
- Added direct support for GoPro `.LRV` files as proxy videos. These must be in the same folder as the corresponding MP4 file and proxy mode enabled.

##### Release 21.08.29

- Added support for **WebP** export with presets for still sequence and animation.
- Added **Properties > Measure Video Quality...** using
  [**VMAF**](https://netflixtechblog.com/toward-a-practical-perceptual-video-quality-metric-653f208b9652).
- Added a new video filter **GPS Text** (contributed by Daniel F).
- Added a new video filter **Reflect**.
- Added a new **Deband** video filter (contributed by Austin B).
- Added a warning dialog before **File > Export Frame...** from a proxy file.
- Added support for keyframes to **Mask: Simple Shape > Rotation**.
- Added support for the operating system clipboard when copying and pasting filters.
- Added support for the operating system clipboard when cut, copy, paste, overwrite or append a clip.
- Added a dialog when **Timeline > Track Operations > Insert Track** on the top audio track to choose audio or video.
- Added handles to the sides of the rectangle on-screen control (VUI) (contributed by TRA).
- Changed the storage for thumbnails and waveforms to use files instead of database.
- Changed **Time Remap** to limit input values to the maximum duration of the clip.
- Changed to set the file date on proxy files to match original file.
- Improved reliability of **Time Remap** status/feedback info.
- Improved the speed setting in the **Time Remap** filter with an option to either modify or lock the input time.
- Improved player grid display and snapping when zoomed.
- Improved image sequence if there is a numeric filename discontinuity or rollover to > 0.
- Fixed possible crash when using **Audio Waveform Visualization** filter.
- Fixed **Mask: From File > Custom...** might lose track of its file.
- Fixed **Text: Simple > File date** broken in v21.05.
- Fixed **Timer** filter's new **Speed** parameter not scaling **Duration**.
- Fixed a possible crash reading a YUV 4:2:2 uncompressed video.
- Fixed some clips' duration in project XML saved in frame units instead of seconds.
- Fixed **Timer** start and end buttons when filter in point is set.
- Fixed quality/rate control with `libx264rgb` in **Export > Codec**.
- Fixed undo simple keyframes  in **Size, Position & Rotate** turned on advanced keyframes.
- Fixed undo followed by redo when trimming clips on **Timeline** may not be correct.
- Fixed a crash moving multiple clips to the beginning with **Ripple All Tracks** on.
- Fixed changing **Time Remap > Enable pitch compensation** in disables **Zoom keyframe Values**.
- Fixed file paths with special characters not working in filters such as **Mask: From File**.
- Fixed exported HEVC MP4 and MOV files are not playable with macOS QuickTime Player or iOS.
- Fixed **Properties > Reset** for an image.
- Fixed a possible crash when a transition is removed during trimming on the **Timeline**.
- Fixed keyframes may be dragged past another.
- Fixed **Time Remap** filter may cause image artifact when using **Export > Parallel processing**.
- Fixed **Properties > Extract Sub-clip...** on GoPro videos or other videos with non-muxable data
  track.
- Fixed **Stabilize** video gives incorrect results after splitting or trimming clip.
- Fixed a crash when dragging multiple clips with variable frame rate to timeline.
- Fixed the timeline playhead could go beyond the end of the timeline.
- Fixed opening a project starts paused on the second frame instead of the first.


##### Release 21.06.29

- Added **Speed** parameter to the **Timer** video filter.
- Added keyboard shortcuts to switch between the stock layouts: <kbd>Alt</kbd>+<kbd>1</kbd> through <kbd>6</kbd>.
- Added **Import** button to **Playlist**. (Thanks, @hbtalha!)
- Added an **Apply** button next to **Properties > Speed** to improve workflow when using mouse wheel.
- Fixed playback may hang when playing different **Playlist** items (broke in v21.05.01).
- Fixed **alpha** presets in **Export** (broke in v21.05.01).
- Fixed a possible crash when changing **Settings > Preview Scaling** (broke in v21.05.01).
- Fixed a possible crash when using **Crop: Source** and **Size, Position & Rotate** filters on the same clip (broke
  in v21.05.01).
- Fixed **Size, Position & Rotate** filters not reloading (broke in v21.05.01).
- Fixed reloading **Keyframes** for a filter on **Output** (broke in v21.05.01).
- Fixed changing **Properties > Color Range** for a clip in the **Source** player (broke in v21.05.01).
- Fixed playhead moves to the beginning of the **Timeline** when dragging an image from **Source** (broke in v21.05.01).
- Fixed a proxy may used instead of the original when dropping from file manager to **Timeline** (broke in v21.05.01).
- Fixed **Fade In/Out** on **Timeline** may add filters in wrong order (broke in v21.05.01).
- Fixed a crash trying to make thumbnail for an invalid playlist item when loading a project (broke in v21.05.01).
- Fixed **Playlist > Play After Open** not working (broke in v21.05.01).
- Fixed missing proxies not generated for an opened project when **Settings > Proxy > Use Proxy** turned on (broke in v21.05.01).
- Fixed **File > Export EDL** creates empty file (broke in v21.05.01).
- Fixed **Center bias** in **Crop: Source** filter.
- Fixed a crash using **Mask: From File** and **Size, Position & Rotate** filters on the same color clip.
- Fixed the **Export > H.264 High Profile** preset was producing main profile on NVIDIA.
- Fixed a crash when using **Paste** after a **File > Close** or **File > New**.
- Fixed a **Project name** with a slash is accepted but fails.
- Fixed a possible crash when changing **Settings > Theme**.
- Fixed **Mask: Simple Shape** moves when deleting all keyframes: no longer allowed to delete the last keyframe; use
  the keyframe toggle button in the parameters area of **Filters**.
- Fixed maintaining the image center when reset **Size, Position & Rotate > Zoom**.
- Improved using the mouse wheel to zoom in **Size, Position & Rotate** filter.
- Improved the range of the new **Zoom keyframe values** when keyframes are changed or removed.
- Fixed custom **Export** preset may load with incorrect frame rate.
- Fixed **Playlist > Replace** may replaced with timeline and appear as `<tractor>` and cause a crash if the **Project**
  player it active.
- Fixed inconsistent handling of keyframes when splitting a trimming a clip.
- Fixed high CPU usage and a long wait after multiple **Stabilize** analysis jobs.
- Fixed a crash when a **Stabilize** analysis (.stab) file fails to open.
- Fixed a crash when **Stabilize > Accuracy** is 9 or higher.
- Fixed remembering the last-opened folder when choosing **Properties > Video > Custom...** for a transition with video
  filter **Mask: From File > File > Custom...**.


##### Release 21.05.18

- Fixed a "requires newer version" dialog appears when opening a corrupt project.
- Fixed some systems unable to load video clips by downgrading FFmpeg to version 4.2.
- Fixed crash with **File > Open MLT XML as Clip**.
- Fixed "INVALID" appears in export after **Copy Timeline to Source** or with old project that includes MLT XML as Clip.
- Fixed many extra keyframes are created as video plays for any filter with on-video controls: Text: Simple, Text: Rich,
  Timer, Audio Visualization, Size Position & Rotate, Crop: Rectangle or Cirle, Spot Remover, etc.
- Fixed **Settings > Use JACK Audio**.
- Changed export jobs to use `melt-7` on Linux.
- Added changing a **Keyframes** parameter's vertical zoom range when its value is changed.
- Fixed **Time Remap > Image mode** reverts to **Nearest** when reloading the filter.
- Fixed being unable to enter numeric values larger than 999 in some filters.
- Fixed **Crop: Source > Center bias** not working with media lower resolution than the video mode.
- Fixed presets with many keyframes not loading all keyframes.
- Fixed **Properties > Image sequence** does not turn off an image's proxy resulting in a broken sequence.
- Fixed the initial state of **View > Full Screen** on Windows.
- Fixed adding a custom **Export** preset does not reload correctly.
- Fixed the **About Shotcut** window title missing shows "%1" instead of "Shotcut".
- Added shortcut <kbd>Ctrl</kbd>+<kbd>T</kbd> to focus the timecode field below the player.
- Added **Romanian** to **Settings > Language**.
- Added a restart dialog to **Settings > Theme**.


##### Release 21.05.01

- Added a new filter **Time Remap** in the new **Time** category that affects both audio and video.
- Added an Apple Silicon build.
- Added an option to **Ignore** missing files in **Export > Export File** (blocking dialog added in v21.01).
- Added a suggested file name to **File > Export Frame...** and remembers the last chosen format. These changes make
  this feature more convenient.
- Added a button in the **Keyframes** parameter track header to vertically zoom in to the minimum and maximumn values.
- Added a **Use Sub-clip** checkbox to the **Convert to Edit-friendly** dialog, under **Advanced**. This will convert
  only the trimmed portion of a clip plus up to 15 seconds before the in point and after the out point for a timeline
  clip. When this is on, only the selected clip is replaced and not every clip based on the same source. This option
  is especially convenient for use with **Time Remap** in which case it defaults to on if the clip has been trimmed.
- Added a **Keep Advanced open** checkbox to the **Convert to Edit-friendly** dialog that remembers your choice between
  sessions.
- Added a status message tip about useful keyboard modifiers to use when dragging keyframes.
- Added the display of minimum, maximum, and midpoint values to the vertical axis of curved parameters in **Keyframes**.
- Improved the sound quality for **Properties > Pitch Compensation** when **Speed** is between 0.5 and 2.0.
- Changed **Keyframes** when trimming a clip or filter to move, delete, or disable full keyframes.
- Upgraded FFmpeg to version 4.3.2
- Upgraded Rubberband (pitch) to version 1.9.1
- Upgraded MLT (engine) to pre-release version 7.0.0
- Improved the color accuracy of the video preview.
- Converted all numeric text fields in filters to spinners.
- Reduced memory in audio resampler per clip.
- Fixed black frames in slideshow (broken in v21.02).
- Fixed **Export Frame** dialog reappears (broken in v21.02).
- Fixed **Opacity** filter may misbehave when using all smooth keyframes.
- Fixed **Export > Format** = `flac` does not write a file with a duration.
- Fixed using the mouse wheel over zoom sliders in **Timeline** and **Keyframes**.
- Fixed an incorrect path to a file in proxy mode when the path starts with the name of a sibling folder.
- Fixed converting non-animated **Text: HTML** to **Text: Rich**.
- Fixed filter values do not update when moving keyframes.
- Fixed waveform after adding a transition by drag a clip to the left.
- Fixed showing `<tractor>` or `blank` as a missing file.
- Fixed a possible crash on setting **Properties > Speed** higher than 23x.
- Fixed a possible infinite loop in **Pitch** audio filter or **Properties > Pitch Compensation**.
- Fixed disabling **Keyframes** toolbar buttons for trim and simple keyframes if they are not supported.
- Fixed a custom export preset may not include attributes of the video mode
- Fixed video glitches using multiple **Text: Rich** filters with **Export > Video > Parallel processing**.
- Fixed **Undo** after using the ripple trim in shortcut (broken in v21.03).
- Fixed applying a custom preset for the **Contrast** video filter.
- Fixed the **Timeline** ruler may be incorrect after starting a new project in the same session.
- Fixed some filters may get lost after **Undo** a **Split** operation.
- Added a context menu to **Text: Simple** and all numeric spinners (broken in v21.02).
- Fixed changing **Properties** on a timeline clip moved to another track overwrites **Playlist** items.
- Fixed **Properties > Repeat** for an image sequence.
- Fixed a crash changing the **Size, Position & Rotate** after applying a shake preset.
- Fixed a possible deadlock changing **Properties > Speed** when **Video Mode** is NOT **Automatic**.
- Fixed disabling keyboard shortcuts for disabled filter trimming and simple keyframe actions.
- Do not let a keyframe be placed beyond the end of a clip.
- Fixed PNG and GIF as album art in music or poster image (previously only JPEG).
- Fixed **Detach Audio** might go to a hidden video track.
- Fixed updating the clip name in **Playlist** and **Timeline** with its speed when changing **Properties > Speed**.
- Fixed a rounding error in aspect ratio of a custom video mode that could cause problems on certain resolutions. 
- Fixed showing a non-functional keyboard shortcut <kbd>X</kbd> in the context menu for a blank region of the **Timeline**.


##### Release 21.03.21

- Fixed writing a raw flac file does not set its duration.
- Improved sound quality with small changes in **Speed** with **Pitch Compensation** or **Pitch** audio filter
  (broke in v20.11).
- Fixed being able to use mouse wheel over **Timeline** and **Keyframes** zoom sliders (broke in v20.01).
- Fixed `<tractor>` and `blank` considered missing and blocking export (broke in v21.01).
- Added an **Ignore** button to the missing files error dialog in **Export**.
- Fixed the **Timeline** clip audio waveform incorrect after adding transition by dragging the clip left.
- Fixed black frames appearing in **Slideshow Generator** (broke in v20.02).
- Fixed repairing a project file opened using a UNC path on Windows.
- Fixed ellided file name in clip **Properties** can become the clip name.


##### Release 21.02.27

- Added a file naming dialog for **Export > From > Each Playlist Item > Export File**.
- Fixed a possible crash using a PNG with alpha channel (transparency) especially with a **Size, Position & Rotate** filter (broke in version 20.06).
- Fixed seeking video in some files particularly AVCHD (broke in v21.01).
- Fixed changing **Properties > Video > Color Range** does not work (broke in v21.01).
- Fixed selecting text with the mouse in various filter numeric fields (broke in v21.01).
- Fixed difficult to enter some numbers in various filter numeric fields (broke in v21.01).
- Fixed unable to make tracks as short as before (broke in v21.01).
- Fixed time bar in **Timeline** &amp; **Keyframes** hidden on vertical scroll and not clickable (broke in v21.01).
- Fixed scroll bars in **Timeline** &amp; **Keyframes** may clash with clips or keyframes making them difficult to use (regression in v21.01).
- Fixed keyframes disappear when changing selected clips on various filters (broke in v21.01): 
  - **Gain/Volume**
  - **Pan**
  - **Pitch**
  - **Saturation**
- Fixed appending to the timeline may change the current track.
- Fixed **Properties > Extract sub-clip** on a file with cover art.
- Fixed **File > Export Frame** on a clip with a **Text: Rich** filter.
- Fixed toggle **Properties > Image sequence** may deadlock on high frame rate video mode or break playback.
- Fixed **Timeline > Merge with next clip** may move other clips on the track.
- Fixed undo a trim in point on **Timeline** may shift other clips on the track.
- Fixed undo after trim in point to create a 1 frame transition may delete the clip.
- Fixed right-click in **Playlist** icons view mode breaks multiple selection on Windows.
- Fixed **Properties > Convert** after **Timeline > Detach Audio** makes video black.
- Fixed some keyboard shortcuts may be broken when not using **Settings > Language > English (United States)**.
- Upgraded JACK audio library on Windows to version 1.9.17.
- Fixed possible crash on Windows due to not loading the packaged DLL over one in a system folder or in `%PATH%`.
- Fixed a crash when selecting a missing video clip.
- Fixed unicode in **Text: Rich > Save As** followed by **Open**.
- Added the ability to repair a near future version project file.
- Added an error dialog when trying to open a far future version project file.


##### Release 21.01.29

- Fixed image skewed with odd width when using certain combinations of filters and transitions (broken in v20.11).
- Fixed being unable to pick transparent black in filters with color pickers (broken in v20.11).
- Fixed some tooltips in **Timeline**, **Filters**, &amp; **Keyframes** not showing on multi-monitor systems (broken in v20.10).
- Fixed **Zoom** in **Scale, Position & Rotate** does not always default and undo at 100% (broken in v20.10).
- Fixed crash with files having more than 32 multiplexed streams.
- Fixed quality-based VBR encoding with the VP8 **Export > WebM** preset.
- Fixed leading zeros for seconds in **Timer** video filter with MM:SS.SSS or SS.SSS formats.
- Fixed support for explicit fractional high DPI (e.g. `--QT_DISPLAY_SCALE 1.5`).
- Fixed bad text formatting when **File > Open** a plain text file in **Text: Rich** filter.
- Fixed drag-n-drop from **Playlist** when a project (MLT XML clip) is in **Source** player.
- Fixed using the numeric keypad for some shortcuts.
- Fixed selecting the same filter **Preset** again.
- Fixed **Export File** does not check for missing files.
- Upgraded Qt to version 5.15.2 for Linux & Windows and 5.12.10 for macOS.
- Improved the playback speeds of fast forward and rewind.
- Changed **Playlist** to not automatically start playback when add to playlist of empty project.
- Finished converting **Timeline**, **Filters**, & **Keyframes** to Qt Quick Controls 2 API.
- Changed keyframe interpolation **Discrete** to **Hold**.
- Changed the default option in the **Convert to Edit-friendly** dialog to MP4 and reduce its output size (crf).
- Improved multi-threaded performance of video track blending and video filters:
  - **Alpha Channel: View**
  - **Chroma Key: Advanced**
  - **Chroma Key: Simple**
  - **Elastic Scale**
  - **Key Spill: Advanced**
  - **Key Spill: Simple**
  - **Levels**
  - **Mask: Apply**
  - **Noise: Keyframes**
  - **Posterize**
  - **Saturation**
  - **Unpremultiply**
  - **White Balance**
- Added support for AV1 decoding and encoding.
- Added **Color space** and **Color transfer** to **Properties > Video**.
- Added an **Advanced** mode to the **Convert to Edit-friendly** dialog with:
  - Added **Deinterlace** option (bwdif) that outputs one frame for each field.
  - Added **Override frame rate** and **Frame rate conversion** with **Blend** and **Motion Compensation** options.
  - Added **Convert to BT.709 colorspace** that provides HDR-to-SDR tonemapping.
  - Added detection of a HDR transfer function (ITU-R BT.2020 or SMPTE ST2084) to automatically show **Convert** dialog.
- Added **Use Higher Performance Waveforms** to **Timeline** and **Keyframes** menus (default on).
- Added a red outline around the thumnbail of the currently opened **Playlist** item.
- Added video filter **Reduce Noise: Quantization**.


##### Release 20.11.28

- Fixed **Insert Track** creates wrong layer/composite ordering (broke in v20.11.25).
- Fixed gradient color chooser affecting filters: Gradient, Audio Light Visualization, Audio Spectrum Visualization,
  and Audio Waveform Visualization (broke in v20.11.25).
- Fixed clicking Open in LUT filter on Linux Snap crashes (broke in v20.10.31).
- Fixed VUI (on-screen controls) of a clip filter disappear when there is a filter on the track or Output (broke in v20.11.25).
- Fixed some filter parameter controls are missing on macOS: Alpha Channel Adjust, Alpha Channel View, Chroma Key
  Advanced, Blends Mode, Gradient, Timer (broke in v20.11.25).

##### Release 20.11.25

- Fixed running on macOS 11.0 Big Sur.
- Fixed **Properties > Reverse** job always fails (broke in v20.10).
- Fixed dropping multiple files to **Timeline** (broke in v20.10).
- Fixed **Timeline, Keyframes, and Text: Rich** editor menus and drop-downs in all filters not showing on systems with multiple monitors (broke in v20.10).
- Fixed drop-downs in all filters not showing the correct value when the filter is reselected (broke in v20.10).
- Fixed appearance of **Settings > Theme > System** on Windows and macOS (broke in v20.10).
- Fixed text looks too big in Windows with display scale 150% (regression in v20.10).
- Fixed **Size, Position & Rotate** filter when a size value becomes 0, possibly while editing the field (broke in v20.10).
- Fixed some library dependencies not bundled in Linux (broke in v20.10).
- Fixed **Size, Position & Rotate** distorting the aspect ratio when image width or height > 16000 (broke in v20.10).
- Fixed bad performance regression and high memory usage when automatically scrolling timeline during  playback (regression in v20.09).
- Reduced memory usage on systems with more than 8 CPU threads.
- Fixed high memory usage when increase **Properties > Speed** large amount with **Pitch Compensation** on.
- Fixed showing the convert dialog twice when dropping files to **Timeline**.
- Fixed **Size, Position & Rotate** filter behavior in generated slideshow.
- Fixed hiding a filter's VUI when the playhead is not over the filtered clip.
- Fixed a possible crash when audio waveforms are updated in the background.
- Fixed simple keyframes for **Stretch X & Y** parameters of **Corner Pin** video filter.
- Fixed some of the undo buttons in the **Corner Pin** video filter.
- Fixed jagged edges on text in the **Text: Rich** editor.
- Fixed cursor disappears between some characters in the **Text: Rich** editor.
- Fixed proxy generation when video includes cover art/thumbnail.
- Fixed a possible crash when drag clip to empty timeline after closing a project with multiple tracks.
- Improved behavior when press enter/return in the current position timecode field.
- Made it is easier to choose opaque black in the color chooser dialogs.
- Changed numeric fields in **Size, Position & Rotate** and **Text: Rich** to require <kbd>Enter</kbd>, <kbd>Tab</kbd>, or click outside (de-focus) to apply the change. This prevents the filter going to weird or undesired sizes or positions as you enter values.
- Changed **Text: Rich** default size and postion to have a 10% margin inside the frame.
- Added a warning dialog when the computer is getting low on available memory.
- Added **Properties > menu > Set Equirectangular...**.
- Added a **Start Offset** time parameter and **Apply transform** option to the **360: Stabilize** video filter.
- Added a **Show Grid** option to the **360: Transform** video filter as a visual aid.
- Added a dialog to confirm trying to add or paste filters to **Timeline > Output**.
- Added **Move Up**, **Move Down**, and **Deselect** buttons to **Filters**.
- Added command line option `--QT_SCALE_FACTOR_ROUNDING_POLICY` that accepts values:
  `Round, Ceil, Floor, RoundPreferFloor, PassThrough`.
  The default is `Round` except on Windows where it is `RoundPreferFloor`, which makes it treat 150% like 100% to reduce the UI text size.


##### Release 20.10.31

- Removed QtWebKit and WebVfx (HTML5 components) from all builds.
- Upgraded Qt to version 5.15.1 on Linux and Windows and version 5.12.9 on macOS.
  As a result, the minimum macOS version is 10.12.
- Updated Linux build to a Ubuntu 18.04 base (glibc version 2.27).
- Completely new Windows build based on msys2, and discontinued the 32-bit build.
- Migrated Windows and Linux builds to GitHub Actions, and automated builds of AppImage and snap for Linux.
- Added **Invert** (reverse polarity) audio filter.
- Added showing the job progress in Windows taskbar button. (thanks @lolametro!)
- Added converting **Text: HTML** filters to **Text: Rich**.
  This does not retain full fidelity, but hopefully it retains the text.
- Added using the H.264 hardware encoder if HEVC not available when **Proxy > Use Hardware Encoder** is on.
- Added **Scroll to Playhead on Zoom** option to **Timeline** menu.
- Added ability to change position in **Size, Position & Rotate** by dragging anywhere inside the rectangle while also holding <kbd>Shift</kbd>.
- Added rectangle VUI help tips for various video filters.
- Added **Size, Position & Rotate > Zoom** now works in any **Size mode**!
- Added **Scroll to Playhead on Zoom** to **Keyframes** menu!
- Added keyboard shortcut for **Center the Playhead**: Ctrl+Shift+P.
- Added keyboard shortcut for **Scroll to Playhead on Zoom**: Ctrl+Alt+P.
- Added keyboard shortcut for rich text editor **Paste Text Only**:  Ctr+Shift+V
- Added common preset resolutions and aspect ratios to the **Add Custom Video Mode** dialog.
- Improved **Text: Rich** filter export on Windows and Linux when display scale is fractional (e.g. 150%).
- Improved the performance of the **Fade In Video**, **Fade Out Video**, and **Brightness** filters on multicore systems.
- Improved image quality when using **Size, Position & Rotate**.
- Changed **Export > Codec > Dual pass** to not write a video file for the first pass.
- Removed "Shotcut" as default text in **Text: Rich** filter.
- Reduced memory usage in **Export** with many clips.
- Fixed time rulers hiding on vertical scroll in **Timeline** and **Keyframes** (regression in v20.09).
- Fixed **Crop: Rectangle > Corner radius** not exactly the same as in version 20.07 (regression in v20.09).
- Fixed a compatibility issue for some systems by downgrading FFmpeg to version 4.2 (regression in v20.09).
- Improved the **Timeline** scrolling speed and smoothness (regression in v20.09).
- Fixed **Blur: Pad incorrect** after splitting clip.
- Fixed moving the cursor in filter fields may move playhead.
- Fixed **Filters** allowed pasting filters when nothing selected.
- Fixed saving projects to Dropbox on Windows leaves temporary files.
- Fixed saving the current stock layout when switching to a custom layout.
- Fixed progress dialog appears over the convert variable frame rate dialog when dragging to **Timeline**.
- Fixed dropping file with comma in its name to **Timeline**.
- Fixed delete keyframe button in **Keyframes** may remove keyframe for another parameter.
- Fixed convert dialog for variable frame rate never appears if dragged directly to non-empty playlist or timeline.
- Fixed a crash dragging multiple clips to **Timeline** if some are variable frame rate.
- Fixed the **Blur: Pad** filter appearing correctly if used that option in slideshow generator.
- Fixed zooming in near end of timeline scrolls timeline backward.
- Fixed deleting all text in **Text: Rich** filter changes font to very small black.
- Fixed editor toolbar in **Text: Rich** filter usually overlays the text by default.


##### Release 20.09.27

- Fixed file dialogs in various filters not openening on macOS (regression in v20.09.13).
- Fixed setting color alpha (opacity) to 0 in **Open Other > Color** and **Open Other > Text** (regression in v20.09.13).
- Fixed a possible crash when using **Center bias** in the **Crop: Source** filter (regression in v20.09.13).
- Fixed incorrect font size in **Text: Rich** filter in export on Windows when the system **Settings > Display > Scale
  and layout** > 100% (High DPI).
- Fixed **Text: Rich** filter when **Export > Video > Parallel processing** is on.
- Fixed **Text: Rich > Preset > Scroll Up/Down** when the background is not transparent.
- Added collpase & expand buttons to the **Text: Rich** editor's toolbar.
- Added **Overflow** parameter to the **Text: Rich** filter.
- Added **Paste Text Only** to the **Text: Rich** editor's menu.
- Added a **Lower Third** preset to **Text: Rich**.
- Fixed the actual workspace layout may not match the currently selected layout when restarting after a crash.
- Fixed **Filters** and **Keyframes** broken on **Source** clip after changing **Settings > Video Mode**.


##### Release 20.09.13

- Added a **Blur: Pad** video filter and made it available in Slideshow generator as **Pad Blur**.
- Added a **Text: Rich** video filter and made **Text: HTML** hidden since it is deprecated (still loads in old projects).
- Added a workspace layout switcher to the main toolbar for the new stock workspace layouts.
- Added a VUI to the **360: Transform** video filter to adjust parameters by dragging.
- Added **Set Equirectangular Projection...** to the **Jobs** menu for a successful export job. This is used to add metadata to a video file to indicate it is 360॰ video in the equirectangular projection as required by most players and web services.
- Added **Zoom to fit** icons to the **Timeline** and **Keyframes** toolbars.
- Improved the performance of the **Timeline** especially with projects over one hour long.
- Upgraded FFmpeg to version 4.3.1.
- Changed **Size and Position** to **Size, Position & Rotate** and made **Rotate and Scale** hidden (only appears in old projects).
- Replaced **Choppy**, **Crop: Circle**, and **Crop: Rectangle** filters with new versions that do not use HTML through WebVfx, which was deprecated in version 20.06.28.
- Changed the **Rutt-Etra-Izer**, **Swirl**, and **Text: 3D** filters to be hidden since they are deprecated  (still loads in old projects).
- Replaced **View > Layout > Timeline Project** with new, better **Logging**, **Editing**, **FX**, **Color**, **Audio**, and **Player** stock layouts.
- The current layout is saved automatically for each stock layout if selected, and **Restore Default Layout** is different for each stock layout.
- Changed the video track hidden icon on the System theme to be more clear and obvious.
- Show an error dialog on startup if the frei0r plugins are not installed (only affects Linux distribution packages).
- Changed the keyboard shortcut <kbd>0</kbd> to zoom timeline to fit.
- Changed the keyboard shortcut <kbd>Alt</kbd>+<kbd>0</kbd> to zoom playlist to fit.
- Changed the Timeline and Keyframes time ruler interval to 1 second when zoomed in.
- Fixed using a secure connection to get the upgrade URL.
- Fixed a rounding error for **Color Grading** video filter.
- Fixed a crash and incorrect preview scaling with more than one **Rotate and Scale** or **Size and Position** filter.
- Fixed colors when using an alpha/VP8 or alpha/VP9 export preset.
- Fixed video compositing with nothing on video track V1 or V1 hidden.
- Fixed export may fail when using extended (non-Latin-1) characters in path.
- Fixed EDL export.
- Fixed **Export**, **Convert**, or **Reverse** may fail if a temporary file it creates becomes locked on Windows.
- Fixed **Properties > Color** button not opening the color dialog with the current color.
- Fixed the **Crop: Source** video filter when using **Settings > Proxy**.
- Fixed a crash when dragging a MLT XML project file to a non-empty **Timeline**.
- Fixed the font dialog may too big or the preview inside the font dialog too big for **Text: Simple** filter.
- Fixed filters not being applied to the portion of a clip inside a transition after undo of **Cut**, **Lift**, **Remove**, **Ripple Delete**, or move.
- Fixed a crash changing speed of a clip with non-standard non-integer or variable frame rate.
- Fixed some dialogs not opening or staying in the foreground.
- Fixed some crashes in timeline overwrite mode.
- Fixed clicking the filters icon next to **Output** not opening the filters panel.


##### Release 20.07.11

- Fixed noisy sound playback on some Windows systems.
- Fixed UI layout glitches and default/minimum size of timeline too short.
- Fixed Quick Sync Video hardware encoder (h264_qsv or hevc_qsv with Quality-based VBR) not working on Windows on older Intel chips.
- Fixed **Properties > Speed** not working correctly on trimmed clip in **Source** player.
- Fixed **Stabilize** and **Normalize: Two Pass** filters not working on trimmed clip in **Source** player.


##### Release 20.06.28

- Added **Playlist > menu > Add Selected to Slideshow** slideshow generator!
- Added **Settings > Proxy** for videos and images. See the [documentation](https://forum.shotcut.org/t/proxy-editing/18517)
- Added bigsh0t 360&deg; video filters:
  - **360: Equirectangular Mask**
  - **360: Equirectangular to Rectilinear**
  - **360: Hemispherical to Equirectangular**
  - **360: Rectilinear to Equirectangular**
  - **360: Stabilize**
  - **360: Transform**
- Added **Open Other > Blip Flash** generator.
- Added 2 new Export presets: **Slide Deck (H.264)** and **Slide Deck (HEVC)**.
- Added a **Background color** parameter to the **Rotate and Scale** and **Size and Position** video filters.
- Added **Help > Topics** with keyboard shortcut <kbd>F1</kbd>.
- Added the ability to drag-n-drop from external file manager (Explorer, Finder) directly to **Timeline**.
- Added **Merge with next clip** to the timeline clip context menu. This only works for clips that are from the same source and contiguous. This is not clip grouping.
- Added returning to the original file if you **Reverse** a reversed clip.
- Added **Settings > Synchronization...** to calibrate the Shotcut player. This works while something is currently playing to help you calibrate using a known good clip.
- Added millisecond **Format** options to the **Timer** video filter.
- Added **Add a keyframe** button to the **Keyframes** panel for all parameters (previously it was missing on some paramters).
- Added the **Reduce Noise: Wavelet** video filter.
- Added a context menu (right-click) to the **Recent** panel with a **Remove** action.
- Added keyboard shortcut <kbd>;</kbd> to toggle a keyframe at the playhead position.
- Added keyboard shortcut <kbd>F2</kbd> to rename a clip.
- Added keyboard shortcut <kbd>F3</kbd> to search in **Recent**.
- Added keyboard shortcut <kbd>F11</kbd> to toggle fullscreen.
- Added **View > Enter Full Screen** on Windows, but simply maximizes due to issues with popup (dialog) windows not appearing on top.
- Added the UI files for the `bigsh0t` 360 video filters.
- Added progress dialogs in several places where time consuming activities occur that otherwise block the user interface.
- Renamed **Timeline > Master** to **Output**.
- Stop selecting **Output** (formerly Master) by default when opening a project.
- Removed **Settings > External Monitor > DVEO VidPort**.
- Export now sets color primaries automatically based on the Video Mode colorspace.
- Use Qt's internal image orientation detection instead of libexif.
- Upgraded Mesa software OpenGL in Windows build to version 19.2.7.
- Upgraded SDL audio output library in Windows build to version 2.0.12.
- The keyboard shortcut to open a playlist item is changed to <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>Cmd</kbd>+<kbd>Return</kbd> on macOS).
- Changed the keyboard shortcut to open the web page of keyboard shorcuts to <kbd>?</kbd>.
- Change the timeline toolbar icon for **Timeline > Split** to something more clear and obvious.
- **Timeline** no longer shows thumbnails for video when the track height is at its lowest.
- The Timeline toolbar button to toggle **Scrub while dragging** is now saved to settings.
- **Export > Video > Deinterlacer** is no longer disabled when **Scan mode** is **Interlaced** (Anything that causes a change to the vertical resolution of an interlaced source is automatically deinterlaced.)
- Deprecated the following video filters. These will be removed in the next version.
  - Rutt-Etra-Izer
  - Swirl
  - Text: 3D
  - Text: HTML
- Added a **Detect** button to the **Use hardware encoder > Configure** dialog.
- Memory is now released when you choose **File > New**, **File > Close**, or **Export File**. (Previously it would keep most of it for reuse.)
- Improved constant quality rate control mode for Intel Quick Sync Video.
- Changed **Playlist > Sort > By Name** to be case insensitive.
- Improved the performance of image sequences.
- Significantly improved the performance of the automatic image padding.
- Show a project's current **Video Mode** as selected in the **Settings** menu when opened.
- Added a timecode tooltip to the mouse pointer when over the player, **Timeline,** or **Keyframes** scrub bars.
- Filter VUIs (video user interfaces) are now disabled when the filter is disabled.
- Fixed **Open Other > Audio/Video Device** on Windows with special characters in name.
- Fixed changing **Properties > Audio > Track** sometimes does not work.
- Improved A/V synchronization on speed-changed clips with **Pitch Compensation** or using the **Pitch** audio filter.
- Fixed changing **Crop: Source** video filter, **Right** parameter on an image with odd width skews the image.
- Fixed audio pops and clicks in a few places.
- Improve A/V synchronization when resampling audio rate is required.
- Fixed incorrect color when using **Export > Codec > libx264rgb**.
- Fixed the clip name after using **Properties > Convert** or **Reverse**.
- Fixed showing the waveform after undo **Detach Audio**.
- Fixed **Audio Tone** in Timeline loses focus after change in **Properties**.
- Fixed moving clip sometimes does not adjust background duration.
- Fixed **Filters**, **Timeline**, and **Keyframes** responding to touch screen.
- Fixed a crash when you use **Timeline > Append**, **Insert**, or **Overwrite** after choosing **File > Close** or **File > New**.
- Fixed <kbd>Backspace</kbd> or <kbd>Delete</kbd> key in input fields sometimes delete timeline clip.
- Fixed **Timeline > Select All** incorrectly includes clips on locked tracks.
- Fixed track filter out points are changed after reopening a project.
- Fixed the default timeline height is too short.
- Fixed **Properties > Convert** ruins filters on clips that were never selected.
- Fixed a crash when using **Crop: Source > Center bias**.
- Fixed seeking to the out point in the **Source** player when you click to seek after the out point.
- Fixed setting in > out or out < in in the **Source** player not reliably updating a playlist clip.
- Fixed saving projects with relative paths.
- Fixed keyframes for the **Level** parameter of the **Opacity** filter.
- Fixed drop-framed timecode for 59.94 fps to follow a strict cadence.
- Fixed the **Reduce Noise: Smart Blur** and **Reduce Noise: Wavelet** video filters to not overwrite the alpha channel.
- Fixed the image quality (interpolation) of a **Size and Position** or **Rotate and Scale** filter inside of a transition.
- Fixed loading image sequences when the sequence number in the file name does not start with 1.
- Fixed a crash when using JACK audio and **File > Open Other**.
- Fixed **Export > Video** not updated when open clip-only project.


##### Release 20.04.12

- Added **Properties > Speed > Pitch Compensation** for automatic pitch correction for speed changes > 0.1x.
- Added a **Replace** command to **Timeline** clip menu including blank regions with shortcut <kbd>R</kbd>.
- **Properties > Reverse** now automatically replaces a selected clip on the timeline (or in **Source** player if using that).
- Added 15 second handles when using **Properties > Reverse** on a timeline clip. Handles are extra footage before the in point or after the out point. This makes it easier to adjust edits or add transitions around reversed clips.
- Added **Properties > Duration > Timeline** to show (not editable) the duration of a timeline clip.
- Added a **Corner Pin** video filter (thanks to @sauron in the forum for the initial effort).
- Added a **Properties > Convert** button to make **Convert to Edit-friendly** in the menu more convenient (kept in the menu for now because a number of support tips reference it).
- **Properties > Convert** now automatically replaces respective clips in **Source** and **Timeline** and adds its clip to the **Playlist**.
- Fixed `=` in **Text: Simple** filter ignores all text before the sign (broken in v20.02).
- Fixed a crash when using some video filters with **Preview Scaling** and multiple video tracks:
  - **Choppy**
  - **Rutt-Etra-Izer**
  - **Swirl**
  - **Text: 3D**
  - **Text: HTML**
- Fixed Offset X and Y parameters of **Rotate and Scale** filter with **Preview Scaling**.
- Fixed video artifacts when using a video for a custom transition and **Export > Parallel processing**.
- Fixed video artifacts when using the **Distort** video filter and **Export > Parallel processing**.
- Fixed video artifacts when using the **Rotate and Scale** or **Size and Position** filters, multiple video tracks, and **Export > Parallel processing**.
- Fixed missing code-signing entitlements for macOS that caused crashes when using the following (broken in v20.02):
  - **Open Other > Audio/Video Device**
  - HTML-based video filters:
    - **Choppy**
    - **Crop: Circle**
    - **Crop: Rectangle**
    - **Rutt-Etra-Izer**
    - **Swirl**
    - **Text: 3D**
    - **Text: HTML**
- Fixed floating or docking some panels may crash on some Linux systems:
  - **Filters**
  - **Keyframes**
  - **Timeline**
- Fixed changing the name of a track in **Timeline** when leaving the field without pressing <kbd>Enter</kbd>.
- Fixed **File > Export Frame** exports uses **Preview Scaling** instead of project resolution.
- Fixed switching between **Cut** and **Dissolve** in transition properties.
- Fixed project not modified when changing transition properties.
- Fixed pressing <kbd>Enter</kbd> in **Filters** search may open a playlist item.
- Fixed a regression in **JACK** transport control (broken in v19.12).
- Fixed a missing **Timeline** track **Lock** button animation when lock prevents something.
- Fixed clips can be moved to **locked** timeline tracks (broken in v19.12).
- Fixed treating paths with Windows drive letters as relative on macOS and Linux.
- Fixed automatically relinking filters with HTML files (when app location changes or moving projects).
- Fixed **Undo** followed by **Redo** after a **Lift** or **Remove** on a transition saves the transition as `INVALID`.
- Fixed some filters than use external files broken when using network (UNC) paths on Windows:
  - **LUT (3D)**
  - **Mask: From File**
  - **Text: HTML**
- Fixed **Filters > Copy** & **Paste** does not keep filter in and out points.
- Fixed opening with a file from the command line on Linux snap or portable.
- Fixed **Export** can overwrite a source when run from command line.
- Fixed **Keyframes** previous/next buttons not using the parameter track to which they belong but rather the current track.
- Fixed opening a playlist clip or a new clip breaks filters on **Timeline > Master** if it is selected.
- Changed **Export > Video > Parallel processing** to default to *OFF* but also now it save the state between export jobs and app session.
- Added support for FFmpeg `sample_fmt` option to **Export > Other**.
- Automatically disable parallel processing on add-on bigsh0t (360) video filters.
- Stop adding `title="Anonymous Submission"` to MLT XML.
- Increased the priority of background jobs a little on macOS and Linux (still less than normal).
- Added `448k` to **Export > Audio > Bitrate**.
- Added automatically scroll the **Timeline** when you double-clock a clip to select-and-seek.
- Updated the mouse wheel behavior in **Keyframes** to match the changes to **Timeline** in version 20.02.
- Added an option to place an icon on the Desktop to the Windows installer.
- Add a cursor to the **Audio Waveform** scope.
- Removed **Export > Stream** as it is not supportable in its current state.
- Changed shortcuts <kbd>C</kbd> and <kbd>Ctrl</kbd>+<kbd>C</kbd> to work with the clip under the playhead of the current track if no clip is selected. This makes it behave similar to other editing shortcuts.
- Changed the keyboard modifier for **skim** to <kbd>Shift</kbd>+<kbd>Alt</kbd>. This prevents <kbd>Shift</kbd> (previous modifier) when selecting multiple clips from changing playhead position. 
  NOTE: On macOS, in order to scroll Timeline or Keyframes horizontally with a mouse wheel (not Magic Mouse or track pad), you must also use *one* of the following:
  - <kbd>Control</kbd>
  - <kbd>Control</kbd>+<kbd>Option</kbd>
  - <kbd>Control</kbd>+<kbd>Command</kbd>
  - <kbd>Option</kbd>+<kbd>Command</kbd>
- Changed the **Matrix** parameter of the **Dither** video filter to be a drop-down combo box without keyframes support.
- Changed **Alpha operation > Write On Clear** to **Overwrite** on some video filters to make them more clear:
  - **Mask: Simple Shape**
  - **Chroma Key: Advanced**


##### Release 20.02.17

- Added **Settings > Preview Scaling**!  
- Added **Export > Advanced > Video >Use preview scaling**.  
- Added **Views > Scopes > Video Vector**.  
- Added **Filters > Audio > Pitch**.  
- Added the ability to rename clips in **Properties**.
- Added support for using a video clip in Transition **Properties > Video**.   
- Added a few more export presets:
  * audio/ALAC
  * audio/FLAC
  * intermediate/DNxHR HQ
  * intermediate/ProRes HQ
  * intermediate/ProRes was changed to ProRes 422
- Added **Arabic** translation.
- Fixed dropping multiple files to **Playlist** in a new project (broken in v19.12.31).
- Fixed some broken keyboard shortcuts in the Turkish translation.
- Fixed **Properties > Speed** not working after a project file repair.
- Fixed clip selection after **Insert Track** or **Remove Track**.
- Fixed **Playlist > Add Selected to Timeline** creates corrupt clips (broken in v19.12.31).
- Fixed **Settings > Display Method > Software (Mesa)** on Windows (broken in v19.12.31).
- Fixed creating a **Project folder** with leading or trailing spaces.
- Fixed saving the `length` property in MLT XML as a time value independent of
  frame rate.
- Fixed starting **Text: Simple** video filter with "@" shows "0".
- Fixed seeking previous &amp; next on the first track in **Keyframes** where
  you trim a filter or use simple keyframes.
- Fixed an unexpected transition is created when moving a clip rightward
  adjacent to the next clip in **Timeline** (regression in v19.12.16).
- Fixed drag-n-drop from **Source** player to **Timeline** left player in an
  inconsistent state (broken in v19.09.14).
- Fixed an inconsistent colorspace conversion when accessing a cached image.
- Fixed **Playlist > Copy** followed by a change in **Properties** incorrectly
  changes the playlist item.
- Fixed clicking on the rectangle control may change its size.
- Fixed using the **LUT (3D)** filter with file with extended characters in its
  file path on Windows.
- Fixed a crash when using a transition on every track at the same time.
- Improved the reliability of **Timeline > Select None**.
- Changed **Timeline > Master > Properties > Frame rate** to show 6 decimal digits.
- Reduced the latency of scrubbing (regression in v19.12.31).
- Changed the video-overlay rectangle control used in some filters to allow
  changing the position by dragging from anywhere inside the rectangle.  
- Changed the **Filters** panel on macOS to prevent floating to avoid a
  frequently reported problem of the **Filters** window appearing blank/black.
- Changed **Timeline > clip context menu > Detach Audio** to not seek afterwards.
- Improved mouse wheel and trackpad behavior in **Timeline**.  
- Upgraded MLT to version 6.20.0 and WebVfx to version 1.2.0.


##### Release 19.12.31

- Fixed a **Timeline** clip corruption bug in version 19.12.16 when moving clips
  with **Ripple** on.
- Added support for moving multiple clips on the **Timeline**.
- Added two new video scopes were added: **RGB Parade** and **RGB Waveform**.
- Allow reducing track height to very short in **Timeline** and **Keyframes**.
- Fixed crackly audio playback for some Windows users.
- Fixed loading project files made before v19.06 when not using a period for a
  decimal point.
- Fixed **Lift** and **Ripple Delete** on **Timeline** not reliably removing all
  selected.
- Fixed checking **Properties > Image sequence** may not update duration in
  **Playlist**.
- Fixed the intra-VLC and non-linear-quantizer options in the XDCAM-422 and D10
  export presets.


##### Release 19.12.16

- Fixed **Scale** animation not linear in the **Rotate & Scale** filter.
- Fixed audio crackles in first couple of seconds of export.
- Fixed <kbd>Ctrl</kbd>+<kbd>A</kbd> selects all in **Playlist** as well as Timeline.
- Fixed the size and position of the **Text: HTML** editor with **Settings >
  External Monitor** enabled.
- Fixed drag-drop from **Playlist** to **Timeline** sometimes reorders the
  **Playlist**.
- Fixed **Color Grading** and **Contrast** creates a weird color after deleting
  a keyframe.
- Fixed updating `x265-params` in **Export > Other** after making changes in **Codec**.
- Fixed opening another project in the same session breaks master track filters.
- Fixed saving a preset with a slash in the name.
- Fixed export fails if the system temporary directory is not writable.
- Fixed removing some temporary files on exit.
- Fixed the timeline **Ripple All Tracks** option was not saved with history
  (before the current setting used during undo and redo).
- Fixed an image sequence in **Export > From > Playlist** may show "INVALID" on export.
- Fixed changing **Properties** (for example, image duration) not updating the **Playlist**.
- Fixed snapping to horizontal grid lines.
- Fixed **Timeline** clip context menu > **Properties** broken in v19.09.
- Fixed bad transitions created by trimming beyond media beginning or end.
- Fixed audio does not follow default device changes on Windows.
- Fixed changing the speed of the clip on the right side of a transition creates
  INVALID transition.
- Fixed track filters were not restored when undoing a **Remove Track**.
- Changed the minimum of the **Gain/Volume** filter to -70 dB.
- Removed **Settings > Deinterlacer > YADIF**. (This was causing crashes, and
  this option only affects preview, not export.)
- Added support for adding a transition in **Timeline** when dragging over a gap.
- Added support for free-form movement of clips on the **Timeline** (no more
  snapping back).
- Change the **Timeline** and **Keyframes** toolbars respond to **View > Small** Icons.
- Upgraded Mesa software OpenGL in Windows build to version 19.2.7.
- Upgraded SDL audio output library in Windows build to version 2.0.10.
- Added a limit to undo **History** configurable to new configuration key
  `undoLimit` that defaults to 1000.
- Added 3 new filters:
  * **Gradient** video filter
  *  **Scan Lines** video filter
  * **Noise Gate** audio filter
- Added a new color gradient control to the following filters:
  * **Audio Light Visualization**
  * **Audio Spectrum Visualization**
  * **Audio Waveform Visualization**
- Added **View > Scopes >  Video Zoom**.
- Added **Reverse** checkbox to the **Mask: From File** filter.
- Added **Remove Finished** to the **Jobs** menu.
- Added **Playlist > Update Thumbnails**.
- Added **Update Thumbnails** to the timeline video clip menu.
- Added keyboard shortcut <kbd>Shift</kbd>+<kbd>Escape</kbd> to give the player
  focus (take focus away from certain widgets).
- Added a **Two Column Scroll** template to the **Text: HTML** filter.


##### Release 19.10.20

- Fixed **Open Other > Audio/Video Device** capture (broken in v19.09).
- Fixed a crash in **Timeline** when you **Lift** the first clip in a track 
  (broken in v19.09).
- Fixed automatic configuration of VA-API for **Export > Use hardware encoder**
  (broken in v19.09).
- Fixed **Blend Mode** filter affects other clips on the track (if the track
    **Properties > Blend mode** was not changed).
- Fixed adding keyframes to some video filters into area after extending the clip:
  - **Text: Simple**
  - **Rotate and Scale**
  - **Size and Position**
- Fixed color picker not automatically changing alpha from 0 to 255.
- Fixed a restarted job reports stopped when completed successfully.
- Fixed HTML file names with extended UTF-8 chars on Linux.
- Fixed **Timeline** audio waveform after changing **Properties > Audio > Track**.
- Fixed a crash opening a project that includes itself by making a self-repair
  on open.
- Fixed saving the length property in MLT XML as a time value independent of
  frame rate.
- Fixed changing **Video Mode** of an opened project breaks timing of edits.
- Fixed **Timeline** ruler not synchronized with the tracks' scroll after
  resizing panel or window.
- Fixed **Timeline > Undo** after splitting the second clip of a transition
  corrupts the timeline.
- Use the main video stream by default when there is an embedded
  album/poster/thumbnail.
- Minor improvements to the **ProRes Export** preset.
- Improved performance of some video filters when using parallel processing:
  - **Blur: Exponential, Gaussian, Low Pass**
  - **Glow**
  - **Mask: Simple Shape**
  - **Reduce Noise: HQDN3D**
  - **Sharpen**
- Improved performance of track blending in areas with transparency.
- Reduced the free disk space check to 25 GB.
- Opening Matroska files containing HuffYUV or Ut Video is much faster.
- **Timeline** waveforms are dimmed instead of hidden when track is muted.
- Changed RGB video clip **Properties > Color range** to **Full** and disabled.
- Changed **Properties > Reverse** and **Convert to Edit-friendly** best option
  (MKV) to use PCM for audio.
- Changed the **Export > lossless > Ut Video** preset to the **matroska** format.
- The signed macOS app is now notarized.
- Added new video **Filters**:
  - **Choppy**
  - **Nervous** (a random selection of previous and current frame)
  - **No Sync**
  - **Trails**
  - **Vertigo**
- Added **Keyframes** toolbar buttons and keyboard shortcuts for filter-trimming
  and simple keyframes:
  * [ = set the filter start
  * ] = set the filter end
  * { = set the first simple keyframe
  * } = set the second simple keyframe
  * Alt+[ = seek previous simple keyframe
  * Alt+] = seek next simple keyframe
- Added keyboard shortcuts for **Filters**:
  * F = open the Filters panel and filter chooser. (At this point search has
focus and the first filter is selected...)
  * Up/Down - select the previous or next filter in the list
  * Enter = add the selected filter to the list
  * Shift+F = remove the selected filter from the list
- Added Thai translation.


##### Release 19.09.14

- Added the option **Play After Open** (default on) to the playlist menu to control above behavior.
- Added multi-select to **Playlist** as welll as **Select All** (Ctrl+Shift+A) and **Select None** (Ctrl+Shift+D) to its menu.
- Added multi-select to **Timeline**, which is currently limited to the remove/delete and lift operations.
- Added **Select All** (Ctrl+A) and **Select None** (Ctrl+D) to the **Timeline** menu.
- Added keyboard shortcuts for some existing **Timeline** menu actions:
  - **Insert Track** (Ctrl+Alt+I)
  - **Remove Track** (Ctrl+Alt+U)
  - **Copy Timeline to Source** (Ctrl+Alt+C)
- Added new video filters:
  - **Dither**
  - **Halftone**
  - **Posterize**
  - **Threshold**
  - **Elastic Scale** (non-linear horizontal scaling)
  - **Blend Mode** (overrides the track **Properties > Blend mode** for that clip)
- Added a **Galician** translation.
- Fixed a crash in some audio filters when using 1 or 6 channels.
- Fixed showing language **English (Great Britain)** when **English (United States)** is chosen.
- Fixed a crash bug in v19.06 when changing image sequence **Repeat** in **Properties**.
- Fixed a bug in v19.08 where dropping a video into **Playlist** on a new project does not update the **Automatic Video Mode**.
- Fixed a bug in v19.08 in the on-screen rectangle control (as used in **Text: Simple** and **Size and Position** filters among a few others).
- Fixed changing speed of a clip with a colon in the file name.
- Fixed reading MLT XML with a colon in the file name of a relative path.
- Fixed the playlist menu button disabled after removing all clips.
- Fixed reloading **Fade In Video** or **Fade Out Video** using opacity may alter the colors.
- Fixed **Convert to Edit-friendly** failing on GoPro videos.
- Fixed filters during a transition are truncated after a **Split** on the timeline.
- Fixed a bug in v19.08 where **Keyframes** becomes broken after trimming on the timeline.
- Reduced the size of the installation by 255 MiB
- Upgraded FFmpeg to v4.2.
- Increased export process priority on Windows from Low (idle) to Below Normal.
- Changed default HEVC quality to 45% so the x265 crf matches its default of 28.
- Added the clip's name to the end of a clip in **Timeline** if its block is wide enough.
- No longer seek after dropping a clip from the player to the **Timeline**.


##### Release 19.08.16

- Changed **Playlist > Open As Clip** to simply **Open**. This action now opens the playlist item directly in the **Source** player, and all changes made in **Source** (trim in/out), **Properties**, **Filters**, and **Keyframes** apply to the playlist item immediately without an explicit update.
- Added **Playlist > Copy** that opens a copy of the playlist item in **Source** just like the old behavior. This is useful if you want to trim out another shot from the same source clip or create a different sub-clip with different filtering.
- Changed double-click on a playlist item to **Open** the clip instead of **Copy** it.
- Added keyboard shortcut `Shift+C` to **Copy** a playlist item.
- Now, when you drag a clip from **Playlist** to **Timeline** the timeline shows an appropriately-size box on a track.
- Fixed a performance regression (since v19.06) in the following filters: **Chroma Hold, Flip, LUT 3D, Mirror, Noise: Fast, Reduce Noise: Smart Blur**.
- Fixed reloading the filter UI for **Rutt-Etra-Izer**, **Text: 3D**, and **Text: HTML** resets the filter trimming in **Keyframes**.
- Added support for keyframes to the **Lens Correction** and **Mosaic** video filters.
- Fixed **Swirl** when maximum = 0%
- Changed the minimum values for **Mosaic** to 0%.
- Removed the scrolling animation from the **Blank Web Animations** HTML template.
- Fixed pasting filters changes the trim and keyframes of the existing filters.
- Fixed **Crop: Circle** and **Crop: Rectangle** not clearing the canvas resulting in trails in some situations.
- Fixed color incorrect when using the **LUT 3D** filter with some other filters following it.
- Fixed reliability of the **Stabilize** video filter to write its results (.stab) file.
- Fixed showing vidstab.trf as a missing file.
- Fixed updating **Stabilize** and **Normalize: Two Pass** results to clips copied between **Source**, **Playlist**, and **Timeline**.
- Added the ability for the **Stabilize** and **Normalize: Two Pass** filters' analysis jobs to update pending export jobs.
- Added the option to run pending **Stabilize** and **Normalize: Two Pass** filters' analysis jobs on export. This only works for **Stabilize** if you are using the project folder feature. Or, if not using the project folder feature, you must click **Analyze** to assign a results file name, but you can stop the analysis job.
- Added support for interlace output to **Properties > Reverse** and **Convert to Edit-friendly** including overrides for **Scan mode** and field order.
- Improved detection of interlaced video in some files such as Ut Video in Matroska.
- Added **Comments** to image properties along with a menu button with: Copy Full File Path, Show in Folder, and Set Creation Time...
- Add resolution and refresh rates to the screens in **Settings > External Monitor** to make them easier to differentiate.
- Fixed switching between different external screens on the same GPU.
- Fixed external screen not showing on correct screen in some arrangements.
- Changed the default video quality to 55% for the **Default** and **YouTube** presets. This aligns with the x264 default crf of 23 and produces a smaller file that most people desire for upload without significant quality loss.
- Added text after **Export > Advanced > Codec > Quality** to show the generated codec-specific quality level (e.g. crf for x264).
- Fixed **Stream** broken by check for writable file.
- Fixed double-click in **Recent Projects** loading twice.
- Fixed disabling meters in the **Audio Loudness** scope not shrinking space.
- Added version metadata to the AppImage for Linux.
- Added md5sums.txt and sha256sums.txt to the GitHub releases page.
- Added saving **Timeline** track height to configuration, not only a project file.
- Fixed trimming an unselected clip in **Timeline** does not correctly adjust its filters.
- Changed **Settings > Interpolation > Nearest Neighbor** to no longer relax seek accuracy. Instead, seek accuracy is now relaxed only during trick playback (reverse, rewind, fast forward).
- Added a **Korean** translation.


##### Release 19.07.15

- Fixed **Timer** video filter shows incorrect decimals.
- Fixed clips that become INVALID were saved as uneditable text clips.
- Fixed a crash in **Wave** video filter.
- Fixed a crash when changing clip **Speed** to something very low.
- Fixed long **Projects folder** path in the **New Project** view.
- Fixed the temporary backup file is empty when saving MLT XML.
- Fixed saving existing project on Dropbox gives an error.
- Fixed advanced keyframes removed when trimming.
- Fixed loading the frame rate from an export preset.
- Fixed multiple **Stabilize** video filter analysis jobs may try to write to
the same .stab file.
- Fixed reported timecode of failed **Export** job if (**Frames/sec** is not 25
or not changed in **Advanced > Video**).
- Fixed incorrect audio waveform after **Undo** after insert/paste into **Timeline**.
- Fixed filters added to a clip with a transition are not the correct length
and not active during the transition.
- Fixed **Blur: Gaussian** filter makes bottom 3 rows of the image with black
or garbage.
- Fixed help text in the **New Project** view may be truncated without scroll bar.
- Fixed **Crop: Circle** > Radius = 100% not completely extended.
- Fixed loading image sequences that do not put leading zeroes into their
number (bug introduced in v19.06).
- Changed **Average Bitrate** for libopus audio codec to set vbr to constrained.
- Changed **Crop: Source** to use the source clip's resolution as maximum for
parameters.
- Changed the **Convert to Edit-friendly** and **Reverse** "better" option from
ProRes to DNxHR, which is faster.
- Changed the **Convert to Edit-friendly** and **Reverse** "best" option from
FFV1 to Ut Video, which is faster.
- Improved full range handling in **Convert to Edit-friendly** and **Reverse**
by respecting an override in **Properties > Color Range**.
- Improved detection of full range color in video clips.
- Changed ripple move on the Timeline to push the clips when the drop zone is a gap.
- Added " - Converted" into the suggested file name when using **Properties >
Convert to Edit-friendly...**
- Added a status message at the start of opening a project.
- Added a drop-down of common frame rates to **Export** and **Custom Video Mode**.
- Added a dialog to ask if the standard, fractional frame rate was intended in
**Export** and **Custom Video Mode**.
- Added a **HD 1080p 50 fps** video mode.


##### Release 19.06.16

- Fixed deleting the project file if there was a save error.
- Fixed reliability of **Settings > Display Method > Software** on Windows.
- Fixed **Crop: Source** filter not working with **Color** clip.
- Fixed using filters on **Color Bars** and other generator clips.
- Fixed audio filters (**Compressor, Expander, Limiter, Notch, Reverb**) broken\
on comma for decimal.
- Fixed alpha video opaque on gaps in **Timeline**.
- Fixed **Convert/Reverse** if there no audio track.
- Fixed **Measure Video Quality** broken.
- Fixed saving the app directory in XML. 
- Fixed **Alpha: Adjust > Invert** checkbox on reload.
- Fixed color eye-dropper (picker) error.
- Fixed audio **Pan** filter channel resets on reload.
- Fixed a crash using **Mirror** filter before **Rotate and Scale** or **Size
and Position**.
- Fixed poor reverse audio quality for mp4 and mkv options.
- Fixed Simple Scroll HTML template may not scroll Up or Left completely.
- Changed project file to use period for decimal point regardless of OS locale
(region/language setting).
- Changed **Export > From** to show **Source** instead of base file name.
- Improved Export Job progress and estimated time remaining.
- Changed **Timeline** ruler interval to 5 seconds.
- Renamed video filter **Circular Frame** to **Crop: Circle**.
- Renamed video filter **Crop** to **Crop: Source**.
- Renamed video filter **Text** to **Text: Simple**.
- Renamed video filter **3D Text** to **Text: 3D**.
- Renamed video filter **Overlay HTML** to **Text: HTML**.
- Renamed video filter **Blur** to **Blur: Box**.
- Renamed **Reduce Noise** video filter to **Reduce Noise: Smart Blur**.
- Changed the default for **Settings > Display Method** back to **DirectX** on
Windows.
- Changed maximum duration of **Color**, **Text**, and **Color Bars** clips to
4 hours.
- Added **Jobs** to the main toolbar.
- Reordered panel buttons on main toolbar to match **View** menu.
- Increased maximum value of Timer filter's Start Delay, Duration, and Offset
to 24 hours.
- Added **View > Show Text Under Icons** to menu.
- Added **View > Show Small Icons** to menu.
- Added support for alpha channel to **Crop: Circle**.
- Added **Crop: Rectangle** video filter with support for alpha channel.
- Added **Add Keyframe** button in Keyframes (only on parameters that show a
  curve UI).
- Added **Ripple All** button to **Timeline** toolbar.
- Added keyboard shortcuts Ctrl+0-9 to toggle the panels.
- Added Alt 0/+/- shortcuts to adjust the zoom in **Keyframes**.
- Added a vertical **Flip** video filter.
- Added **Blur: Exponential** video filter (fast and bleeds to edges).
- Added **Blur: Low Pass** video filter (fast and bleeds to edges).
- Added **Blur: Gaussian** video filter (slow and bleeds to edges).
- Added **Reduce Noise: HQDN3D** video filter.
- Added **Noise: Fast** video filter.
- Added **Noise: Keyframes** video filter.
- Added Swedish translation.


##### Release 19.04.30

- Fixed reading some AVCHD files after a camcorder splits.
- Cosmetic fixes for timecode spinner and toolbar icons on high DPI systems.
- Bundled libnsl for Linux to fix Fedora.
- Fixed **Video Waveform** scope graticule not showing on non-dark theme.
- Fixed incorrect compositing z-order after **Insert Track**.
- Fixed cosmetic problem with main toolbar using **System** theme on macOS.
- Fixed current track changes after inserting or overwriting a clip in Timeline.
- Fixed absolute paths can be introduced on Windows when using a project folder.
- Fixed sometimes showing forward slashes for file paths on Windows.
- Fixed first clip does not start at beginning when drop to Timeline after
  **File > New** or **File > Close**.
- Fixed **Properties > Convert** and **Reverse** on files with album art or
  embedded thumbnail.
- Fixed a possible crash on **File > New** or **File > Close**.
- Fixed filters on clips not extended into transition when adding a transition
  by trimming or resizing a transition.
- Fixed **Open Other  > ALSA Audio** on toolbar on Linux.
- Fixed changing **Properties > Speed** or **Color Range** on a timeline clip
  may crash.
- Fixed timeline correction when drag clip to another track and then back to
  original.
- Fixed reloading the **Mask: From File** filter resets **Threshold** keyframes.
- Fixed the **Mask: Simple Shape** filter does not work when **Width** or
  **Height** is 0%.
- Increased parameter ranges in the **Rotate and Scale** filter.
- Added verification that saved MLT XML is well-formed XML before (over-)writing
  the target file.
- Changed default **Outline Thickness** (3) and alpha of **Text** filter to
  match **Open Other > Text** and prevent a problem where the text outline is
  aliased when the clip is transparent.
- Changed the version check to use HTTPS for increased privacy.
- Added DLL redirection files for other .exe programs on Windows to prioritize
  Shotcut-provided DLLs over those in system or $path.
- Removed the buggy **Merge with next clip** from Timeline clip context menu.
- Added (creation) **Date** column to Playlist **Details** view.
- Added **Set File Date...** to the Playlist menu and item context menu.
- Added **Sort By Name** and **Sort By Date** to the Playlist menu.  
  These are single-shot sorting commands. The playlist is still fixed-ordering.
  The new options do not automatically sort new playlist entries.
- Added new video filters:
  * **Grid**
  * **Audio Dance Visualization**
  * **Audio Light Visualization**
  * **RGB Shift**
  * **Glitch**
  * **Distort**
- Added **Zoom 300%, 400%, 500%, 750%, and 1000%** to the player's zoom menu.
- Added **Settings > Drawing Method > Software (Mesa)** on Windows.  
  This is not good for performance, but it improves compatibility. Use only as
  a last resort.
- Added **Display Method > OpenGL** or **Software (Mesa)** on Linux.
- Added **Norwegian Nynorsk** translation.

##### Release 19.02.28

- Fixed opening image sequence on Windows with extended/special characters in
  file path/name.
- Fixed crash on some video clips, particularly those with Google Pixel 3 and
  likely others.
- Fixed field order with interlaced export.
- Fixed an image artifact when using keyframes with the **Mask: Simple Shape**
  filter.
- Fixed image and alpha channel integrity with transitions on clips with a
  non-opaque alpha channel.
- Fixed a crash when changing clip **Properties > Audio > Track**.
- Fixed **Properties > Video > Color Range** inaccurate after changing it.
- Fixed **Shake One Second** presets in regions that use comma for decimal point.
- Fixed moving a **Playlist** item to the end.
- Fixed more dialogs to be modal to prevent them from going behind the main
  window.
- Fixed **Overlay HTML** webvfx templates when using a project folder.
- Fixed volume slider appears before main window at launch on macOS.
- Fixed more dialogs to use sheet style on macOS.
- Fixed a few small memory leaks in MLT.
- Upgraded Qt to version 5.9.7.
- Changed **Width** and **Height** minimum to 0 for **Blur** filter.
- Set the **Save as type** list on all file save dialogs (convert, reverse,
  text, EDL, image).
- Improved the quality of Export Frame > WebP.
- Show "Not Seekable" instead of "Live" when opening a non-seeable clip (or device or stream).
- Show a status message when trying to drag from Project player.
- Prefer loading DLLs in Shotcut's install folder over those in System32.
- Default the out point of the **Color**, **Count**, and **Text** generator clips to the same as image duration (default 4 seconds).
- Added **Offset** to **Timer** video filter.
- Added **Vertical HD 30 fps** and **Vertical HD 60 fps** video modes.
- Added support for HTTPS.
- Added [`--QT_SCALE_FACTOR` and `--QT_SCREEN_SCALE_FACTORS`](https://doc.qt.io/qt-5/highdpi.html#high-dpi-support-in-qt) command line options.
- Added **English (Great Britain)** translation.

##### Release 19.01.27

- Fixed **Text** animation/keyframes not working in v19.01.24.
- Fixed distortion when a **Mirror** filter is placed before a **Size and
  Position** or **Rotate and Scale** filter.
- Fixed **Levels** filter in locales with comma for decimal point.

##### Release 19.01.24

- Fixed launch crash on Linux by excluding libdrm libraries.
- Fixed audio level changed by the **Mask : From File** filter.
- Fixed **Text** filter may have glitches with **Export > Parallel processing**
  (regression in v18.12.x).
- Fixed missing file detected when **Stabilize** filter added without clicking
  **Analyze**.
- Fixed external monitoring on Linux screen.
- Fixed unable to detect hardware encoders with spaces in the installation
  folder path.
- Fixed changing **Speed** can move a clip.
- Fixed changing **Speed** has no effect when the system region and language
  decimal separators are different.
- Fixed filter duration not adjusted when trimming a transition.
- Fixed ripple trim when clip has a transition.
- Fixed removing a transition by trimming adds some frames.
- Fixed aspect ratio for **File > Export Frame** with non-square pixel video.
- Fixed handling relative paths to external resources in the **Overlay HTML**
  editor.
- Fixed a crash opening a project after removing the bottom video track.
- Fixed the lossless/H.264 preset to be completely lossless.
- Fixed dropping a file from a file manager whose name has special/extended
  characters (e.g. `[`, `]`).
- Fixed the state of the enabled checkbox for the **Overlay HTML** filter and
  when using a color picker.
- Fixed distortion after changing the **Keyframe Type** of a keyframe for the
  **Scale** parameter in the **Rotate and Scale** filter.
- Fixed right-clicking a keyframe to open context menu may change its position.
- Upgraded FFmpeg to v4.1
- Improved **Color Grading** filter by letting all parameters go from -100% to 100%.
- Added an automatic retry without **Parallel processing** when **Export** job fails.
- Set the **Save as type** list on the **Export File** dialog on Windows when a
  preset defines a filename extension.
- Added **Center Playhead** option to the **Timeline** and **Keyframes** menus.
- Added **Slow Zoom ___, Hold ___** presets to the **Size and Position** filter.
- Added a **Chroma Hold** video filter.
- Added a **Swirl (HTML)** video filter.
- Added a simple **Templates** framework to the **Overlay HTML** filter (see
  path `Shotcut\share\shotcut\qml\filters\webvfx\templates` to add your own)
  with the following templates:
  - Blank HTML
  - Blue Middle Bar
  - Creative Commons Music
  - Blank with Web Animations
  - Simple Scroll

##### Release 18.12.23

- Fixed color accuracy of **lossless/Ut Video** preset and use yuv422p format.
- Fixed number of digits for seconds in the **Timer** video filter when using **Format > MM:SS.SS**.
- Fixed compositing completely transparent areas of alpha channel darkens output.
- Fixed some generators (**Color Bars, Ising, Lissajous, Plasma**) not working correctly in **Timeline**.
- Fixed **Settings > External Monitor > DeckLink/Intensity** can stall when **Settings > Realtime** is enabled.
- Fixed making project folder if a parent folder does not exist.
- Fixed **New Project > Start** does not save a .mlt file until you open media and save.
- Fixed launch on some Linux (e.g. gentoo) by including libselinux .
- Fixed crash when undo **Playlist > Remove All**.
- Fixed auto-saved file not removed when save and exit with no changes.
- Fixed the color accuracy of the **Color** generator.
- Fixed numeric locale bug in the **Audio Spectrum Visualization** and **Audio Waveform Visualization** filters.
- Fixed clip reloaded when leaving **Properties > Speed** with no change.
- Fixed **Settings > External Monitor** on Windows screen.
- Fixed launch crash on Linux with (Csound) csladspa < 6.11.1 installed.
- Improved color accuracy of internal RGB-to-YUV conversions.
- Changed **Quality** to 100% when using the **intermediate/ProRes** preset.
- Added 16:9, 9:16, and 1:1 aspect ratios for transition wipes.
- Moved **Properties > Reverse...** from the overflow menu to a button.
- Changed **Properties > Reverse...** to use project folder if used.
- When **Reverse** job completes, automatically open it and add it to the **Playlist**
- Start playback from the beginning if you play when the play head is at the end.
- Improved speed of the **Text** and **Timer** video filters.
- Added **View > Scopes > Video Histogram**
- Added **Preset** to some more filters:
  - **Audio Gain/Volume**
  - **Blur**
  - **Brightness**
  - **Opacity**
- Added **Preset** and simple and advanced keyframes to the **Balance** and **Pan** audio filters.
- Added a **Levels** video filter with simple and advanced keyframes!
- Added **Properties > Color Range** for video clips.
- Replace the **Mask** video filter with 3 new filters:
  - **Mask: Simple Shape**
  - **Mask: From File**
  - **Mask: Apply**

##### Release 18.11.18

- Fixed crash in Export (bug in v18.11.13).
- Fixed NVENC hardware encoders on Windows and Linux.
- Fixed VA-API hardware encoders on Linux. As a result, the Linux build is now
  based on Ubuntu 16.04 (glibc 2.23), which may reduce compatibility with older
  Linux systems.
- Fixed hardware encoder detection on Windows.
- Added **Audio Waveform Visualization** video filter.
- Added **MM:SS.SS** to **Timer** filter.
- Added IRE graticule and tooltips to the **Video Waveform** scope.
- Added support for the mouse wheel to the **Color Grading** circles.
- Added configuration setting player/warnGPU, which is a boolean that defaults true.

##### Release 18.11.13

- Added an **Advanced** mode to **Export**.
- Added **Use hardware encoder** checkbox to **Export**.
- Added VA-API hardware encoding for Linux.
- Added videotoolbox hardware encoding for macOS.
- Added **New Project** / **Recent Projects** screen.
- Added **10 Pixel Grid** and **20 Pixel Grid** options to the player grid button menu.
- Added **Spot Remover** video filter.
- Added **View > Scopes > Video Waveform**.
- Added **Settings > Video Mode > Non-Broadcast > Square 1080p 30 fps** and 60 fps.
- Added **Ut Video** presets to **Export**.
- Added signed app bundle for macOS.
- Fixed support for macOS 10.10 and 10.11.
- Fixed clearing export preset search collapses categories.
- Fixed searching export presets in categories.
- Fixed initial rectangle size for **Size and Position** filter.
- Fixed reopening **Timeline** changes zoom level.
- Fixed exit sometimes hangs.
- Fixed some filters' presets do not save any values:
  - **Key Spill: Advanced**
  - **Chroma Key: Advanced**
  - **Reduce Noise**
- Fixed A/V synchronization on some files.
- Fixed seeking on audio files with album art.
- Fixed saving multiple lines of text in preset for **Text** generator.
- Fixed crash when undoing split and transition on Timeline.
- Fixed filters not applied correctly when using **Export > From > Each Playlist Item**.
- Improved reliability of **Audio/Video Device** capture.
- Fixed **Color** generator did not signal colorspace.
- Fixed transfer characteristic conversion and full range output in **Export**.  
  (Add `mlt_image_format=rgb24`, `color_range=jpeg`, and `pix_fmt=yuvj420p` in
  **Other** for full range output.)
- Made **GPU Effects** hidden and discouraged.
- Added support for project folder to **Stabilize** and **Overlay HTML** filters.
- Increased **Scale** maximum to 500% for **Rotate and Scale** filter.
- Improved support for DDS, ICO, and WebP images.
- Bundle more library dependencies on Linux.
- Converted macOS build to standard app bundle layout.


##### Release 18.10.08

- Added support for [Intel Quick Sync Video](https://www.intel.com/content/www/us/en/architecture-and-technology/quick-sync-video/quick-sync-video-general.html) hardware-accelerated video encoders to the Windows build (in **Export > Codec** choose h264_qsv or hevc_qsv).
- Added **Grid** and **Safe Area** overlays with a toggle/menu button to the player.
- Added snapping to the grid and safe areas for the VUI rectangle control as used by **Text**, **Size and Position**, and more filters.
- Added **Open Other** to the main toolbar with a drop-down menu.
- Added the ability to drag-n-drop folders from a file manager into Shotcut.
- Added the ability to supply multiple file and folder name arguments to the shotcut command line executable.
- Added the ability to make a temporary **Custom Video Mode** (leave **Name** blank).
- Added **Settings > Video Mode > Custom > Remove....**
- Added **View > Layout > Remove....**
- Added **Settings > Clear Recent on Exit** checkbox to prevent saving data on a shared computer account.
- Added command line option `--clear-recent` to enable **Clear Recent on Exit** and hide that option in the **Settings** menu.
- Added a dialog when you click to check for an update that asks if you want to check for update automatically (at startup only) with the option to suppress the dialog indefinitely.
- Fixed audio preview distortion on Windows (regression in v18.09).
- Fixed some AAC MP4 files start in the middle.
- Fixed un-mute a track may not draw its waveforms.
- Fixed whitespace in **Text** filter removed in **Export**.
- Fixed crash adding clip to **Timeline** after removing all tracks.
- Fixed simple keyframes go missing or not all the way to 00:00.
- Fixed switching from simple to advanced keyframes in **Text**, **Rotate and Scale**, **Timer**, and **Size and Position** filters.
- Fixed a possible crash when adding a transition by trimming.
- Fixed crash on macOS after the app restarts itself when some **Settings** are changed.
- Fixed moving a clip to the left where the right edge is not a blank.
- Fixed some **Timeline** actions do not work correctly after a **Ripple** move.
- Fixed undo/redo form trim-to-transition over a blank/gap.
- Fixed **Ripple** moving a clip to the end of a track was not extending the hidden black background.
- Hide the **Text** generator if **Settings > GPU Effects** is on (incompatible).
- Fixed the **Rotate and Scale** filter preset not saving keyframes for the **Scale** parameter.
- Fixed a crash opening multiple files at once either through **File > Open** or drag-n-drop from a file manager.
- Fixed a crash closing a playlist-only project with **Automatic Video Mode**.
- Fixed changing position or removing advanced keyframes for the **Scale** parameter of the **Rotate and Scale** filter distorting the aspect ratio of the image.
- Fixed **Timeline > Split** not working if the current track is empty. (It should split the topmost clip under the playhead.)
- Fixed clicking the reset button of the **Center** checkbox of the **Crop** filter does not re-enable the other controls.
- Fixed the **Timeline** and **Keyframes** timeline rulers are incorrect after changing **Settings > Video Mode**.
- Fixed a crash when the project frame rate is very low (< 6 fps).
- Fixed a crash when switching keyframes on and off for position and size parameters in video filter such as **Size and Position**, **Text**, and **Timer**.
- Fixed trimming multiple track filters hides them.
- Fixed making a **Text** preset does not save the text (only all other parameters).
- Changed resolution restriction from a multiple of 8 to a multiple of 2.
- Improved the layout of the filter chooser in **Filters**.
- Changed **Timeline** fade controls to behave the same as **Keyframes** simple keyframes.
- Changed the **Noise** generator from opening as a live source to a clip with a duration.
- Changed drag-n-drop to **Playlist** to not automatically open the first file unless the project is empty.
- Changed the **Rotation** parameter of the **Mask** filter to use degrees, and fixed its reset button.
- Added more library dependencies to the Linux portable tar, AppImage, and snap builds including the SWH LADSPA plugins.

##### Release 18.09.16

Fixed broken color selection in the following (non-GPU) video filters:

- Chroma Key: Simple
- Chroma Key: Advanced
- Key Spill: Advanced
- White Balance

##### Release 18.09.15

- Fixed image transform regression in **Rotate and Scale**, **Size and
Position**, and **Text** filters.
- Fixed image scaling interpolation method when not using a transform filter.
- Fixed a crash applying an image transform filter to an image with alpha
channel (PNG, SVG).
- Added a highlight for the buttons in the **Filters** chooser.
- Fixed new **Ripple** and **Snapping** keyboard shortcuts not always working.
- Fixed moving a clip to another track and back not working correctly.
- Fixed dragging clips to the **Timeline** stops working.
- Fixed redo trimming the in point of clip on **Timeline** not working correctly.

##### Release 18.09.13

- Added **Ripple** support for **moving** clips including **Ripple All Tracks**.
- When **Ripple** is on and you move a clip to the right, it now
ripples (pushes) all the clips to the right instead of making a transition
(including the **Ripple All Tracks** option).
- Added **Ctrl+R** keyboard shortcut to toggle **Timeline Ripple**,  
**Ctrl+Alt+R** to toggle **Ripple All Tracks**, and  
**Ctrl+Shift+R** to toggle both.
- Improved **Snapping** behavior on the **Timeline**.
- Added **Ctrl+P** keyboard shortcut to toggle **Snapping**.
- Added **Reset Track Height** (**Ctrl+0**) to the **Timeline** menu.
- Added a **Timer** video filter.
- Added support for negative rotation to the **Rotate and Scale** filter.
- Added **Shake 1 Second - Scaled** and **Shake 1 Second - Unscaled** presets
to the Size and Position filter.
- Added a **Text** clip to the **Open Other** dialog.  
This is a convenience item that creates a transparent **Color** clip with a
**Text** filter.
- Added **Extract Sub-clip** to **Properties** menu for audio/video clip.
- Added **Export** presets for WebM VP8 and VP9 with alpha channel.
- Fixed a crash when quickly changing clip selections in the **Timeline**.
- Improved closing Shotcut more reliably and the behavior of multiple shotcut
processes.
- Fixed **Undo** beyond **Remove Track** may crash.
- Fixed a crash when moving a clip after undoing a transition.
- Fixed a crash loading project after some sequence of inserting and removing tracks.
- Fixed a crash loading an image with the wrong filename extension.
- Fixed OS audio device changes may cause Shotcut to hang.
- Fixed crash dragging simple keyframes beyond the edges of the clip.
- The 32-bit Windows build can use more memory to reduce risk of crash:  
3 GiB on 32-bit Windows and 4 GiB on 64-bit Windows.
- Improved behavior of opening WebP images.
- Fixed advanced keyframes for the **Size and Position** filter.
- Fixed inserted and then hidden video tracks become audio tracks after
re-opening the project.
- Fixed changing **Video Mode** from **Automatic** to something else with
nothing opened.
- Fixed moving a transition to another track leaves a hidden clip on the old track.
- Fixed trimming the out point of a timeline clip may change the in point of
the following clip.
- Fixed **Properties** > **Speed**, **Convert**, **Reverse**, and
**More Information** does not work sometimes after reloading a project.
- Fixed reliability of changing size and position fields with keyframes
in **Size and Position** and **Text** filters.
- Fixed trimming outward with **Ripple All Tracks** moved clips on other tracks
in the wrong direction.
- Fixed audio waveforms still appear on muted tracks after adding a track.
- Fixed edges of text with the **Text** filter may get cut off (clipped).
- Fixed **Size and Position** and **Rotate and Scale** filters may leave black
right and bottom edge of frame.
- Fixed trimming a timeline clip with **Fade In/Out Video** filters
with "Adjust opacity instead of fade with black" enabled.
- Fixed **Export** may change the actual frame rate and cause timing errors.
- Fixed reducing the **Frame/sec** in **Export** causes timing errors in the output.
- Removed the **Compositing** toggle icon from the **Timeline** track head. Now,
it is located in the track **Properties** as **Blend mode** with a **None** option.
- In the **3D Text** filter, replaced the Droid fonts with Liberation due to an
incompatible license.
- Improved the performance of changing filter parameters and scrubbing.
- Limit the number of background thumbnail and waveform generation threads to 4.
- Prevent trying to generate audio levels for waveforms for still images and
other silent sources.

##### Release 18.08.14

* Fixed regression in 18.08.11 that can put corrupt character in the .mlt XML
  project file.
* Fixed the size of an existing Text filter with animation breaks if you
  select the clip and the filter.

##### Release 18.08.11

* Fixed new crash in v18.08 changing **Settings > Video Mode** with nothing opened.
* Fixed crash while adjusting position or size in **Text** and **Size and Position** filters.
* Fixed position and size information incorrect if resolution or aspect ratio changed in **Export**.
* Fixed **Text** animation (keyframes) when not the first clip in the timeline.
* Fixed track name not editable after the track head had been selected at least once.
* Fixed right-clicking a timeline clip breaks automatic timeline scrolling during playback.
* Added Quicktime Animation **Export** preset to export video with alpha channel.
* In **Export**, let option values in **Other** tab override values generated by other fields.

##### Release 18.08.01

* Added the timecode of failure to the **Jobs** panel when an export job fails
  (makes locating problem areas in the project easier).
* Added an **Unpremultiply Alpha** video filter (handy to fix compositing for
  video clips with an alpha channel that has had its color pre-multiplied with
  its alpha).
* Fixed various crash regressions since v18.05.
* Fixed audio distortion during preview (regression in v18.07).
* Fixed custom **Export** presets broken if name contains parentheses
  (regression in v18.07).
* Fixed **Properties > Reverse...** broken if numeric region setting uses comma
  for decimal (regression in v18.07).
* Fixed **Overlay HTML** editor easily destroys default scripts (introduced in
  v18.07) if **WebVfx JavaScript extension** enabled.
* Fixed custom interlaced **Export** presets loading as progressive (regression
  in v18.07)
* Fixed **Timeline > Copy Timeline to Source > Export** fails on unsaved
  (Untitled) project.
* Fixed **Text** filter has aliased edges (regression in v18.07).
* Fixed **Stabilize** video filter not available on Linux (regression since v18.06).
* Fixed changing **Speed** in **Properties** breaks all filters on that clip
  (regression since v18.05).
* Fixed **Fade Out Video** (and keyframes in general) broken on still images
  whose in point is > 0 (regression since v18.03).
* Fixed accuracy of **Properties > Duration** for image clip on the timeline.
* Some fixes for changing **Settings > Video Mode** after starting a project.
* Fixed compositing of upper video tracks becomes broken if bottom video track
  is deleted.
* Fixed images with alpha channel (e.g. PNG) on upper video tracks have dark
  edges after compositing if the **Size and Position** or **Rotate and Scale**
  filters are not used.

##### Release 18.07

* Numerous fixes as usual.
* Changed shortcut for **Add Video Track** to `Ctrl+I`.
* Changed shortcut for **Redo** to `Ctrl+Y` on Windows.
* Added **10%** to the player zoom menu.
* Hide the VUI (video user interface) when the play head is not over the clip with the current filter.
* Renamed the Rotate filter to **Rotate and Scale**.
* Keyframes are now saved in the project file using time clock values instead of frame numbers to make them adaptive to frame rate.
* Reverted memory manager change from v18.05 pending further testing to improve stability.
* Added advanced keyframes to the **Size and Position** filter.
* Added simple and advanced keyframes to the following video filters:
  - **Rotate and Scale**
  - **Text**
  - **Glow***
  - **Contrast***
  - **Sharpen***
  - **Vignette***  
  \* = including the (still experimental) GPU filter
* Added **Copy Timeline to Source** to Timeline menu.
* Changed the audio codec to AC-3 for the edit-friendly and reverse MP4 file format.
* Changed `J` and `K` key behavior to change speed up or down before changing direction.
* Added categories to the **Export** presets (custom presets can start their name with "category)" to use a category).
* Added **View > Layout** menu for custom and stock layouts:
  - Timeline Project
  - Playlist Project
  - Clip-only Project
  - Player
* Changed the default, first-time user UI layout to **Timeline Project**.
* Changed **Properties > menu > Reverse...** to work on a trimmed clip from either **Source** or **Timeline**.
* Added **Properties** menu items to the context menus for **Timeline** and timeline clips.
* Added logic to sort GoPro files when multiple files are opened or dropped.
* Added support for setting project file name (using **File > Save**) for empty project.
* Added new HTML template for WebVfx JavaScript extensions enabled in **Overlay HTML** video filter.
* Added search field to the filter chooser in **Filters**.
* Upgraded MLT to v6.10.0

##### Release 18.06

* Many bug fixes due to introduction of keyframes and change to memory management in v18.05.
* Added simple and advanced **Keyframes** to the **Blur**, **Mask**, and **Saturation** filters.
* Added seek buttons for simple **Keyframes**.
* Added ability to add and remove advanced **Keyframes** using double-click.
* Added ability to drag advanced **Keyframes** to adjust both value and position.  
  (When dragging, hold down Ctrl key to adjust only value or Alt key to adjust only position.)
* Added double-click to toggle simple **Keyframes** controls (circles).
* Added double-click to toggle fade in/out controls (circles) on **Timeline** clip.
* Added many animated (keyframes) presets to the **Size and Position** filter.
* Added **Hue/Lightness/Saturation** video filter.
* Added **Reverse** to clip **Properties** menu.
* Added **Detach Audio** to timeline clip's context menu.
* Added 5.1 surround support to the **Copy Channel** and **Swap Channels** audio filters.
* Added caution message to GPU Effects confirmation dialog.
* Added a **Keyboard Shortcuts** link to the **Help** menu.
* Changed presets file format to YAML.
* Changed **Settings > GPU Processing** to **GPU Effects**.
* Reduced memory usage on 32-bit builds (by constraining multi-threading).
* Upgraded [FFmpeg to v4.0](http://ffmpeg.org/index.html#news).
* Integrated [AMD AMF](https://gpuopen.com/gaming-product/advanced-media-framework/) hardware-accelerated H.264 and HEVC encoders on Windows (Set **Export > Codec** to **h264_amf** or **hevc_amf**. Requires recent Radeon or AMD APU.)
* Upgraded MLT to git master ([v6.8.0](https://www.mltframework.org/blog/v6.8.0_released/) minimum required to build).

##### Release 18.05

* Added **Keyframes** for Filters:
  - Gain / Volume
  - Brightness
  - Circular Frame
  - Color Grading (no simple)
  - Opacity
  - Size and Position (simple only)
* Added support for mono and 5.1 surround sound: **Settings > Audio Channels** and **Export >Audio > Channels**.
* Added **Finnish** translation.
* Restored **GIF Animation** for Export.
* Reduced memory footprint (especially for Rotate and Size and Position filters).
* Changed **Export** default settings to reduce output size by increasing GOP and number of B frames.

##### Release 18.03

* Added a **Sketch** filter.
* Added numeric fields to the **Color Grading** filter.
* Added **All** option to **Properties > Audio > Track**.
* Added **Estonian** translation.
* Improved image loading speed on Windows.
* Improved mouse-wheel & trackpad scrolling in **Timeline**.
* Improved support for JACK Audio (Linux and macOS only).
* Upgraded FFmpeg to version 3.4 and latest vpx for much faster VP9 encoding.
* Upgrade MLT to v6.6.0.
* Upgraded SDL to version 2.0.

##### Release 18.01

* Added **Audio Spectrum Visualization** filter.
* Added support for font size and italics to **Text** filter.
* Added a **Mask** filter.
* Another important fix for accuracy of XML time values for non-integer frame rates.

##### Release 17.12

* Added icon, progress bar, and time remaining/taken to **Jobs** panel.
* Increased maximum resolution to 8192x8192.
* Indicate if variable frame rate is detected in **Properties**.
* Added **Convert to Edit-friendly...** dialog when variable frame rate or non-seekable file opened.
* Added **Convert to Edit-friendly...** to **Properties** menu for video and audio files.
* Adding, removing, and adjusting **Fade In/Out** filters now updates fade controls on the **Timeline**.
* Major speed improvements for **Timeline** rendering, especially when changing zoom level.
* Stop showing waveforms on muted tracks.
* Fixed audio crackling on some systems.
* Fixed accuracy of reading and writing time values, particularly for non-integer frame rates.

##### Release 17.11

* Changed add-filter menu to be embedded instead of popup.
* Added **Master** label to **Timeline**.
* Show filters icon on track heads if track is filtered.
* Prioritize '0' shortcut for **Timeline** over **Playlist**.
* Do not adjust timeline zoom until slider is released.
* Added warning dialog to **Export** if file cannot be written (e.g. due to permissions).
* Added warning dialog to **Export** if chosen file is in the project.
* Added warning dialog to **Export** if the drive is low on space.
* Added Nepali translation.
* Added button to Text filter to insert the # symbol.

##### Release 17.10

* Fixed multi-threaded decoding with FFmpeg v3.2.
* Added 1080p 59.94 and 60 fps video modes.
* Added support for NVENC to Export panel.

##### Release 17.09

* Show in Folder now selects the file on Windows Explorer or macOS Finder.
* Renewed the code signing certificate for the Windows installer and executable.
* Updated SDL to v2.0
* Updated FFmpeg to v3.2
* Updated x264, x265, and vp8/9 to the latest stable versions.
* Added `--noupgrade` command line option and boolean General/noupgrade option to config/registry options.

##### Release 17.08

* Increased maximum **Timeline** zoom level.
* Increased **Speed** field precision to 3 decimal places.
* Increased maximum value for **Speed** field to 200x.
* Added Norwegian Bokmål translation.

##### Release 17.06

* Change maximum duration of a still image from 10 minutes to 4 hours.
* Added Hungarian translation.
* Fixed Chinese translation.

##### Release 17.05

* Fix opening and saving files on Windows with non-Latin characters in the name or path.
* Updated translations.

##### Release 17.04

* Fix crashing on launch on the new macOS 10.12.4.
* Added Japanese translation.
* Added Turkish translation.

##### Release 17.03

* Converted the track toggle buttons to icons.
* Now, you can press Del or Backspace to delete a selected item in the Recent panel.
* Playback now pauses at the out point in the Source player.
* Some stability improvements.
* Performance boost for Size & Position and Rotate filters on multi-CPU systems.

##### Release 17.02

* Fixed drag-n-drop from other than C: drive on Windows.
* Fixed '/' getting added to front of file paths on Windows.
* Fixed the MLT XML repair tool not correctly handling decimal point in some
  configurations.
* Fixed opening a network stream.
* Improved support for image sequences.
* Improved device capture.
* Added Slovenian translation.

##### Release 17.01

* Mostly just bug fixes.
* Added Chinese Taiwan translation.

##### Release 16.12

* Added **Constrained VBR** for the video codec rate control mode to Export.
* Added **Fixed** option to video **GOP** to Export.
* New audio mixing mode that does not affect levels.
* Increased usage of floating point for audio processing to improve quality.
* Added **Occitan** translation.
* More fixes for copying filters and LUT (3D) video filter.

##### Release 16.11

* Added **portable app** feature with **Settings > App Data Directory** and `--appdata` command line argument.
* Fixed drag-n-drop to Timeline after moving clip to different track.
* Fixed **LUT (3D) filter** for languages/regions that use comma for decimal point.
* Fixed **Properties > Speed** on macOS for languages/regions that use comma for decimal point.
* Added **Gaelic** (Scottish) translation.

##### Release 16.10

* Added **32-bit Windows** build.
* Changed Linux build to be more compatible.
* Added **LUT (3D)** video filter.
* Added **Lens Correction** video filter.
* Added **Merge with next clip** to Timeline clip context menu.
* Fixed **Paste Filters** for Timeline clips and tracks.
* Removed File > Open Other > Screen.

##### Release 16.09

* Added **Tiles**, **Icons**, and **Details** view modes to Playlist.
* Added **Copy Filters** and **Paste Filters**.
* Upgraded Qt to v5.6.1 with HiDPI support. (Set environment variable QT_AUTO_SCREEN_SCALE_FACTOR=0 to turn it off.)
* Converted some 16x16 icons to 32x32 for HiDPI.
* Moved the **Timeline Zoom** slider to the toolbar.

##### Release 16.08

* Added count-down (or up) generator: **File > Open Other > Count**
* Major performance boost for opaque clips on video tracks higher than **V1** with track **C**omposite enabled and **Blend mode: Over**.

##### Release 16.07

* Added **File** > **Export Frame...**
* Added **Remove transition** to **History** by trimming a neighboring clip to
  remove it.
* Fixed version checker.

##### Release 16.06

* Show red outline on scrub bar of **Source** player to indicate selection.
* Added **Cut**, **Copy**, and **Paste** to Edit menu and Timeline tool bar.
* Changed double-click on **Timeline clip** to select+seek instead of copying to **Source** player.
* Changed Timeline keyboard shortcut **A** to append.
* Changed Timeline keyboard shortcut **C** to copy.
* Changed Timeline keyboard shortcut **Enter** to seek to start of clip.
* Added **Peak** and **True Peak** meters to the **Audio Loudness** scope.
* Added version/upgrade-checker.
* Added check for missing files when opening .mlt XML project file.
* Added dialog to locate and resolve (relink) missing files in project file.
* For clips with speed changed, added support for saving and loading relative path and file names.
* Added **Export EDL** to the **File** menu.
* Added **YouTube** preset to **Export** (which does the same thing as not changing any export settings, not selecting an export preset, or clicking Reset).
* Updated Blackmagic Design SDI/HDMI output to work with recent driver updates.

##### Release 16.05

* Mostly just fixes.
* Added **Remove** to **Jobs** panel.
* Added **25%** option to player's **Zoom** button-menu.
* Improved application logging.
* Moved status messages front and central and removed status bar.


##### Release 16.04

* Fixed frequently reported problem with black video on Export.
* Fixed a few crashing bugs.
* Added an option to Windows installer to remove registry settings to help people with new crash-on-launch problems.
* Reduced memory usage when exporting a playlist or multitrack project.
* Added **Normalize: One Pass** audio filter (existing Normalize renamed **Normalize: Two Pass**.
* Added **Audio Loudness** to View > Scopes.
* Added **Brightness** video filter for CPU and GPU.
* Added **Contrast** video filter for CPU and GPU.
* Added **Reduce Noise** video filter for CPU only.
* Install ffplay and ffprobe executables.
* Improved visual feedback about what is selected in **Timeline**, **Properties**, and **Filters** views.
* Added **More Information** to clip Properties overflow-menu.
* Added **Start Integrity Check Job** to clip Properties overflow-menu.
* Added auto-rotate for video clips with orientation metadata.
* Added a Ukranian translation.

##### Release 16.03

* Changed player tab Program to **Project**.
* Changed panel name Encode to **Export**.
* Added a **From** field to the Export panel to allow exporting the project, a
  clip loaded in the **Source** tab of the player, or or each playlist item as a batch of jobs.
* Added an export preset for animated GIF.
* Upgraded FFmpeg to v3.0.
* Upgraded MLT to v6.0.0.

##### Release 16.02

-   Audio waveforms on timeline are updated incrementally as progress is made.
-   Allow dual pass encoding for CBR.
-   Added Show Video Thumbnails option to the timeline menu.
-   Added Rebuild Audio Waveform to a timeline clip's context menu.

##### Release 16.01

-   Added **Speed** parameter to Properties for an audio/video clip.
-   Added **Properties** views for track and timeline when selected.
    Click track head to select track; click the timeline's cornerstone
    (top left block) to select the timeline.
-   Added **Blend mode** to track properties (not available in GPU
    processing mode; only applies when compositing is enabled in the
    track header).
-   Added **Alpha Channel: View** video filter.
-   Added **Alpha Channel: Adjust** video filter.
-   Added **Chroma Key: Simple** video filter.
-   Added **Chroma Key: Advanced** video filter.
-   Added **Key Spill: Simple** video filter.
-   Added **Key Spill: Advanced** video filter.
-   And, as usual, a bunch of fixes and translation updates.

Note: none of the above, new video filters can utilize GPU-processing at
this time.

##### Release 15.12

-   Added crash recovery for untitled sessions.
-   Added Slovak translation.

##### Release 15.11

-   Added Rutt-Etra-Izer video filter.
-   Added audio/video device and screen capture for OS X.
-   Added screen capture for Windows.
-   Added Application Log to View menu.
-   Added Save button to text viewer dialogs (logs, XML).
-   Added video Deinterlace, Interpolation, and Parallel-processing
    options to Encode panel.
-   Reorganize the Settings menu and added headings.
-   Added Close action to File menu.
-   Added keyboard shortcuts for trimming on Timeline: I, Shift+I,
    O, Shift+O.
-   Added support for ripple trimming on Timeline.

##### Release 15.10

-   Mostly just bug fixes.
-   Added **Dutch** translation.
-   Added **Russian** translation.
-   Added project check and repair function.

##### Release 15.09

-   Added **Scrub Audio** to Settings menu.
-   Added **Display Method** to Settings menu (Windows only).
-   Added **Portugal Portuguese** translation.
-   Added **Mute** audio filter.
-   Updated Qt to v5.5.
-   Updated FFmpeg to v2.7.

##### Release 15.08

-   Added a Greek translation.
-   Added a **Ripple All Tracks** option to the Timeline menu.
-   4 new audio dynamics filters:
    -   Compressor
    -   Delay
    -   Expander
    -   Limiter
    -   Reverb

##### Release 15.07

-   4K UHD support
-   5 new video filters:
    -   Old Film: Dust
    -   Old Film: Grain
    -   Old Film: Projector
    -   Old Film: Scratches
    -   Old Film: Technocolor
-   5 new audio filters:
    -   Bass & Treble (3-band graphic equalizer)
    -   Band Pass
    -   High Pass
    -   Low Pass
    -   Notch
-   Added **Insert Track** and **Remove Track**.
-   New default Encode settings produce a better quality H.264 MP4 file.
-   Composite now defaults to on/enabled for new video tracks.

##### Release 15.06

-   Added 64-bit Windows build.
-   Added **Audio Spectrum** analyzer.
-   Changed audio **Gain** filter to use dB and log scale.
-   Added a toggle button to **Lock** a track.
-   Changed **Insert** and **Ripple Delete** to ripple across all
    unlocked tracks.
-   Changed keyboard shortcut to adjust track height to Ctrl+-
    and Ctrl+=.
-   Added keyboard shortcuts to toggle track:
    -   **Mute** - Ctrl+M
    -   **Hide** - Ctrl+H
    -   **Lock** - Ctrl+C

##### Release 15.05

-   Add **Distort** option to Size and Position filter.
-   Add video **Cut** option to Transition Properties.
-   Code-sign Windows executable and installer.
-   In Timeline, operate on clip under the play head if nothing
    is selected.
-   New keyboard shortcuts for Timeline:
    -   Select clip under play head: Ctrl+Space.
    -   Move selection one item to the right/left: Ctrl+Right/Left.
    -   Blanks can be selected to remove/ripple-delete: X or Shift+Del
        or Shift+Backspace.
    -   Deselect everything: Ctrl+D.
    -   Open As Clip: Enter/Return.

##### Release 15.04

-   Added an audio tone generator (in File > Open > Other).
-   Now you can set a new default duration for audio or video
    fade filters.
-   The WebM VP9 encode preset enables multi-threaded encoding.

##### Release 15.03

-   Add Update button to Playlist panel.
-   Double-clicking a successfully completed Encode job, now opens the
    result in Shotcut.
-   Consolidate GPU and Video filters in Filter menu.
-   Add View > Scopes > Audio Waveform.
-   Move audio peak meter to View > Scopes > Audio Peak Meter and
    main toolbar button.
-   Move volume slider to player toolbar icon.

##### Release 15.02

-   Add x265 codec.
-   Add video quality measurement tool.
-   No longer auto-plays upon opening a playlist or multitrack project.
-   Auto-select all text upon giving a timecode field focus.

##### Release 15.01

-   Only a few bug fixes and translation updates.

##### Release 14.12

-   New filter menu allows you favorite filters and see only favorites.
-   CPU-based video filters can be added after GPU-based filters.

##### Release 14.11

-   The HTML5 features are finally available on Windows!
-   Add source code editing to the HTML editor.
-   Add 3D Text filter based on WebGL, typeface.js, and three.js.
-   Add support for DirectShow devices on Windows in the Open
    Other dialog.
-   Add the [Opus audio codec](http://www.opus-codec.org/).
-   Change the VP9 WebM preset to use the Opus audio codec.
-   Add support for the \#localtime\# keyword to the Text filter (no
    button yet).
-   Restart instead of simply closing the app when changing the GPU or
    language settings.
-   Change the Redo keyboard shortcut to Ctrl+Y on Windows only.
-   Save file paths in MLT XML with relative names for assets in the
    same folder or sub-folder. This makes it easier to use a relocatable
    project folder.
-   Add scale and offset parameters and a preset widget to the
    Rotate filter. Usually after rotating a video, part of the image has
    been clipped. These new parameters provide control for that clipping
    processing including no clipping.
-   Add Italian translation.

##### Release 14.10

-   Maintenance release to fix some bugs.
-   Added Polish translation.
-   Restored FFV1 encoding and preset.
-   Change Leap Motion control: close hand to pause, open hand
    to shuttle.

##### Release 14.09

-   Added WMV and WMA encode presets.
-   Enabled the video player zoom and pan controls for OS X.
-   Added *Size and Position* video filter with a rectangle control that
    overlays the video player.
-   Added a simple *Text* video filter also with rectangle
    control overlay. This is a dynamic text filter supports pre-defined
    variables: *Timecode, Frame \#, File date, File name*.
-   Enabled parallel video processing for *Encode File* on systems with
    more than 2 logical cores when not using *GPU Processing*. This
    makes encoding faster when using filters, transitions,
    and compositing.
-   Added an *Opacity* <span style="background-color:
    transparent;"> video filter. </span>
-   Added an option on video fade filters: *Adjust opacity instead of
    fade with black*.
-   Now you can add filters to an entire track by clicking the track
    head and using the *Filters* panel.
-   New projects created with this version now load much more quickly.

##### Release 14.08

-   Now the Stabilize video filter really does work on Windows.
-   Added a Gamma menu item to the Settings menu when in GPU mode, which
    performs gamma correction. Previously, the display gamma was fixed
    at sRGB, but now you can choose Rec. 709. Previously, when applying
    a GPU filter, Shotcut would output sRGB gamma when encoding to a
    Y'CbCr file, and that has been removed/fixed.
-   Transfer characteristic (gamma) metadata is now written to video
    files that support it (e.g., H.264).
-   The filter UI layout now automatically adapts to a horizontal or
    vertical layout to suit more workspace layouts.
-   Upgraded FFmpeg to version 2.3.

##### Release 14.07

-   add "Remove Old Program Files" option to Windows installer
-   ask to exit if there are unfinished jobs
-   fix crash when loading invalid XML
-   add auto-save
-   fix frames repeating at end of some clips
-   fix Stabilize filter on Windows
-   add elegant combination slider and spinner control and revise all
    filter UIs to use it
-   cleanup all filter UIs to be consistent with other areas of UI
    panels
-   improve tooltips on timeline track headers
-   fix bug that gives you a MLT-XML GPU warning when the Balance or Pan
    filters are in a project
-   Save to app config the folder path name of last saved project XML.
    Then, use this path to default save dialogs such as next XML or
    video stabilization data.
-   On OS X, when using System theme, stack the display volume and mute
    toggles so these widgets do not appear so wide.
-   Workaround for the Stabilize filter's analysis job crashing on
    Windows.<br>The analysis job still crashes at the end, but
    the data is still created and usable. So, go ahead and try to use
    the data regardless of the job's failure.
-   Make adjusting image duration on timeline easier.<br>Now,
    the Duration field in Properties adjusts the out point, and the
    actual duration is 10 minutes. This lets you add just a few seconds
    to the Timeline by default but then stretch or shrink the image clip
    on the timeline up to 10 minutes. If you need more than 10 minutes,
    add the clip to the track again.

##### **Release 14.06**

-   upgrade x264 to git master and FFmpeg to v2.2
-   check compatibility of MLT XML with current GPU processing mode
-   introduce logging program activity to text file
-   more fixes for file names with extended characters on Windows
-   fix opening files with path/name with extended characters on Windows
-   upgrade to Movit 1.1.1 and replace GLEW with libepoxy

##### Release 14.05 and Earlier

-   14.04.29: fix crash on Windows w/GPU upon closing Color Grading
    filter UI
-   14.04.17: add Wave filter
-   14.04.14: fix huge memory leak introduced in v14.04.05 while working
    with interlaced clips with GPU Processing enabled
-   14.04.12: fix Overlay HTML filter appearing in filter list as
    Circular Frame
-   14.04.09: now provide 3 simultaneous color wheels for CPU-based
    Color Grading filter
-   14.04.08: add Catalan language
-   14.04.04: require shift key to make editing keyboard shortcuts
    target the playlist instead of the timeline
-   14.04.03: improved reliability for some FLV files and music with
    album art
-   14.04.01:
    -   restore Crop filter for GPU
    -   fix drag-n-drop from playlist to timeline
-   14.03.27: fix GPU processing on OS X
-   14.03.26:
    -   add GPU support for video wipe transitions
    -   fix aspect ratio of encoding on Windows in locales that use
        comma for decimal point (broken since 14.02.27)
-   14.03.25: GPU processing upgrades broke on OS X
-   14.03.24: add transition properties and video wipes
-   14.03.23: add transition by trimming
-   14.03.19: add resizing transition
-   14.03.17: display a time delta while moving, trimming, and fading on
    timeline
-   14.03.12: add initial support for cross-fade audio and video
-   14.03.11: add Open XML As Clip to File menu
-   14.03.09: in Encode, lock-down video parameters for presets that
    have specific resolution and framerate
-   14.03.07:
    -   add search for encode presets
    -   add Show Audio Waveforms toggle to timeline menu
-   14.03.02: add seeking to previous and next edit points using |<
    and >| buttons or alt+left/right keyboard shortcuts
-   14.03.01: add Fade In and Fade Out audio filters and Fade From Black
    and Fade To Black video filters with special timeline fader controls
-   14.02.27:
    -   more fixes for locales using comma for decimal point on Windows
    -   add a Set Default button for duration to the image properties
        panel
-   14.02.18:
    -   add insert and overwrite for drag-n-drop into timeline
    -   add option to scrub over timeline when dragging clips into
        timeline or within it
    -   show clip properties for selected shot on timeline
-   14.02.17: fix overwrite spanning multiple clips & gaps and undo for
    that
-   14.02.15: fix a luma (brightness) change when applying non-GPU
    filters
-   14.02.14: fix undoing a split
-   14.02.13:
    -   fix drag-n-drop from Source player to Timeline on Windows and OS
        X
    -   add keyboard shortcut 'S' to split clip under playhead on
        current track
-   14.02.12: fix encoding with GPU processing on Windows
-   14.02.11:
    -   fix GPU processing on Windows (where compatible)
    -   new video stabilization (
        [faster](http://public.hronopik.de/vid.stab/)) and audio
        normalization ( [EBU R128](https://tech.ebu.ch/loudness))
        filters <br>(video stabilization still crashes on
        Windows 8, but works for us on Windows 7 and other OS)
-   14.02.08: rework integration of playlist and timeline and change
    player tabs to Source / Program
-   14.02.05: add external monitoring on additional system monitor
-   14.02.04: track compositing fixes
-   14.02.03: fix crash on startup on Windows with dock title bars
    hidden
-   14.02.01:
    -   fix accuracy of edits when saving and loading project XML in
        locales with radix not a period
    -   set the UI locale from the language or host OS locale so that
        radix appears and interpreted correctly
    -   add Restore Layout to View menu
    -   add Show Title Bars to View menu
-   14.01.30: add Split At Playhead to context menu of clip on timeline
-   14.01.29: add saving and loading of playlist in a timeline project
-   14.01.28: upgrade FFmpeg libs to v2.1
-   14.01.27: reduce GPU memory usage with GPU processing
-   14.01.25: fix crash using audio only clip on Windows
-   14.01.23: fix inserting into playlist by menu or keyboard command
    (fix for OS X is in v14.01.24)
-   14.01.21: fix broken MP3 encode preset and sometimes wrong aspect
    ratio in encode
-   14.01.20: add Vignette and Diffusion (GPU only) filters
-   14.01.14: improve GPU processing performance
-   14.01.05 - 14.01.18: various timeline bug fixes
-   14.01.05: added insert and overwrite edits
-   14.01.02:
    -   fix GPU processing to work with Timeline
    -   re-enable GPU processing for Windows (still only partially works
        on some systems)
-   13.12.30:
    -   fix broken timeline on Windows
    -   fix putting Timeline panel in a tab stacked with other panels
    -   let Timeline panel be moved to top of window or floated
-   13.12.29: timeline broken on Windows
-   13.12.28: add multitrack timeline
-   13.12.26: fix OS X build broken since v13.12.21 due to Qt upgrade
-   13.12.22: upgrade Qt to version 5.2.0
-   13.11.21:
    -   fix process not completely closing on Windows
    -   fix broken keyboard shortcuts when not using English
-   13.11.18: add Invert and Sepia Tone video filters
-   13.11.17: add OpenGL version and extension test
-   13.11.15: add thumbnail caching
-   13.11.08:
    -   fix keyboard cursor left/right and page/up down (on Linux,
        issues still persist on Windows, OS X)
    -   add Stabilize video filter
    -   add Downmix audio filter
    -   add Swap Channels audio filter
-   13.11.06: add audio Normalize filter
-   13.10.31:
    -   add player zoom button
    -   broke keyboard cursor left/right and page up/down for navigating
        video (workaround: click on scrub bar to give it focus)
-   13.10.29: fix H.264 encoding on Windows - broken since 13.10.02
-   13.10.28: add Rotate video filter
-   13.10.21:
    -   fix encode when GPU is enabled (regression since 13.09.30)
    -   add DeckLink keyer capability
    -   add WebVfx producer widget so you can set HTML generator
        transparent (handy for keying HTML)
-   13.10.17: add audio Pan and Balance filters
-   13.10.16: fix loading tractor-based MLT XML files (e.g. from
    Kdenlive or OpenShot)
-   13.10.15: fix Leap Motion for Linux and Windows
-   13.10.11
    -   disable Leap Motion in Linux builds
    -   fix opening correct file from Recent search
    -   add first audio filters
-   13.10.10: conflict between QtWebKit and libLeap on Linux resulting
    in crash when loading HTML over HTTP
-   13.10.09: crashes in Recent panel when opening new (not in recent)
    file (downloads deleted since high visibility crash)
-   13.10.08: add search field to Recent panel
-   13.10.02 - 13.10.07: writes incorrect playlist
-   13.09.21: Best known version before Qt 5 upgrade
