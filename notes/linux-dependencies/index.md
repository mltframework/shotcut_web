---
layout: page
title: Linux Distro Package Dependencies
category: notes
---

Ubuntu, Debian, and Mint
------------------------

required: libopengl0
optional: libjack0 or libjack-jackd2

Fedora
------

required: libXScrnSaver
optional: jack-audio-connection-kit

Generic Directly Dependent Libraries
------------------------------------

basic "platform" libs: glibc 2.35+, libpthread, libm, libdl, librt, libz, libstdc++,
libGL, libX*, libasound (ALSA), libgthread, libglib-2.0, libgobject-2.0,
libselinux, libwayland-egl, libwayland-client, libwayland-cursor

common multimedia libs: libcairo, libjack
