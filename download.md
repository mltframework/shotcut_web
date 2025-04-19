---
layout: page
title: Download
permalink: /download/
category: about
---

We pledge that our downloads are always free of
malware, spyware, and adware. However, we can only provide that guarantee if you come to this website
to download.

#### Current Version: 25.03.29

<div class="OSTEST">
  <p>
  We think your OS is
    <span id="pOSTEST" style="font-style: italic">
      Well, we don't actually know.
      Either JavaScript is disabled, or I am not working quite right.
      So, I am showing you all the options.
    </span>
  </p>
  <p>
    Show downloads for
    <a class="show_links" id='os_linux'>GNU/Linux</a>&nbsp;| 
    <a class="show_links" id='os_mac'>macOS</a>&nbsp;| 
    <a class="show_links" id='os_win'>Microsoft&nbsp;Windows</a>&nbsp;| 
    <a class="show_links" id='os_all'>All</a>
  </p>
</div>

{:.win}
##### Windows 10/11 on Intel or AMD CPU
<small>(minimum Windows 10 version is build 1809 "October 2018 Update")</small>
{:.win}

<div class="win" style='float: right; text-align: center'>
To avoid ads and get automatic updates:<br>
<a href='//www.microsoft.com/store/apps/9PLNFFL3P6LR?cid=storebadge&ocid=badge'><img src='https://developer.microsoft.com/store/badges/images/English_get-it-from-MS.png' alt='Get it from Microsoft Store' style='width: 284px; height: 104px;'/></a>
</div>

{:.win}
|-----------------------|-------------------
| [Windows installer](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-win64-250329.exe/download) | [Windows portable zip](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-win64-250329.zip/download)
{:.withborders}

{:.win}
&nbsp;

{:.win}
##### Windows 10/11 on ARM CPU

{:.win}
|-----------------------|-------------------
| [Windows installer](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-win_ARM-250329.exe/download) | [Windows portable zip](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-win_ARM-250329.zip/download)
{:.withborders}

{:.win}
&nbsp;

{:.win}
##### Windows 7 & 8
<small>(The last version to support Windows 7 & 8 is 22.12.21)</small>
{:.win}

{:.win}
|-------------------|-------------------
| [Windows 7 installer](https://sourceforge.net/projects/shotcut/files/v22.12.21/shotcut-win64-221221.exe/download) | [Windows 7 portable zip](https://sourceforge.net/projects/shotcut/files/v22.12.21/shotcut-win64-221221.zip/download)
{:.withborders}

---
{:.win}

{:.mac}
##### macOS 12 - 15
<small>(64-bit macOS 12+)</small>  
{:.mac}

{:.mac}
|-----------------------
| [macOS universal](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-macos-250329.dmg/download)
{:.withborders}

{:.mac}
&nbsp;

{:.mac}
##### macOS 11
<small>(The last version to support macOS 11 is 24.11.17)</small>
{:.mac}

{:.mac}
|-----------------------
| [macOS universal](https://sourceforge.net/projects/shotcut/files/v24.11.17/shotcut-macos-241117.dmg/download)
{:.withborders}

{:.mac}
##### macOS 10.14 & 10.15
<small>(The last version to support macOS 10.14 & 10.15 is 24.01.31)</small>
{:.mac}

{:.mac}
|-----------------------
| [macOS universal](https://sourceforge.net/projects/shotcut/files/v24.01.28/shotcut-macos-240131.dmg/download)
{:.withborders}

{:.mac}
**Important**: If you have a Mac that is from 2013 or earlier you might experience a video preview color problem due to our migration to [Apple Metal](https://developer.apple.com/metal/). In that case, use [version 22.12.21](https://sourceforge.net/projects/shotcut/files/v22.12.21/shotcut-macos-221221.dmg/download).

{:.mac}
An [unsigned app bundle is available](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-macos-unsigned-250329.dmg/download) so that you
can modify the build per the Free Software license agreement.

---
{:.mac}

{:.linux}
##### GNU/Linux

<div class="linux" style='float: right; text-align: center'>
<small>To avoid ads and get automatic updates:</small><br>
<a href='https://flathub.org/apps/details/org.shotcut.Shotcut'><img
width='186' height='62' alt='Download on Flathub'
src='https://flathub.org/assets/badges/flathub-badge-en.png'/></a>
<br>
<a href='https://snapcraft.io/shotcut'><img width='186' height='60'
alt='Download on Snap Store' 
src='https://raw.githubusercontent.com/snapcore/snap-store-badges/master/EN/%5BEN%5D-snap-store-black.png'></a>
</div>

<small class="linux">(64-bit Mint 20+, Ubuntu/Pop!_OS 20.04+, Debian 11+, Fedora 32+, Manjaro 20.2+, MX Linux 21+, elementary OS 6+)</small>

{:.linux}
|-----------------------|-------------------
| [Linux portable tar](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-linux-x86_64-250329.txz/download) | [Linux AppImage](https://sourceforge.net/projects/shotcut/files/v25.03.29/shotcut-linux-x86_64-250329.AppImage/download)
{:.withborders}

{:.linux}
**Linux portable tar users**: No install required, simply extract the archive and run
it. You can drag the Shotcut folder to copy and move it wherever you
want. If double-clicking the icon in your file manager does not launch
Shotcut, open Shotcut.app, and try double-clicking the shotcut shell
script. Do not try to run bin/shotcut directly. You may need to **install
JACK** from your distribution.
[Here is a page]({{ "/notes/linux-dependencies/" | prepend: site.baseurl }})
that lists some required packages for specific distributions.

{:.linux}
**Snap Users**: On [snap-enabled systems](https://snapcraft.io/docs/core/install), install
from the store with `snap install shotcut --classic`  
Since this snap is using classic confinement based on the portable zip above,
not all dependencies are bundled, and it has the same run-time requirements as
the portable tar.

---
{:.linux}

##### Other

File checksums for downloads are available in
[md5sum](https://github.com/mltframework/shotcut/releases/download/v25.03.29/md5sums.txt)
or [sha256sum](https://github.com/mltframework/shotcut/releases/download/v25.03.29/sha256sums.txt) format.

[Source code
archive](https://github.com/mltframework/shotcut/releases/download/v25.03.29/shotcut-src-250329.txz)
/ [GitHub repository](https://github.com/mltframework/shotcut)

[Older versions](https://github.com/mltframework/shotcut/releases/) are
available for download.

[Release Notes]({{ "/download/releasenotes/" | prepend: site.baseurl }})

<form action="https://www.paypal.com/donate" method="post" target="_top">
<input type="hidden" name="hosted_button_id" value="XD364WFCHD46N" />
<input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" border="0" name="submit" title="PayPal - The safer, easier way to pay online!" alt="Donate with PayPal button" />
<img alt="" border="0" src="https://www.paypal.com/en_US/i/scr/pixel.gif" width="1" height="1" />
</form>

`This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
or FITNESS FOR A PARTICULAR PURPOSE.`

<script src="{{ "/assets/js/platform.js" | prepend: site.baseurl }}"></script>
<script src="{{ "/assets/js/platform-display.js" | prepend: site.baseurl }}"></script>
