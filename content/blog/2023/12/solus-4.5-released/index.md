---
title: "Solus 4.5 Released"
author: "david"
categories:
  - news
  - releases
date: 2023-12-21
featuredimage: "/solus-4.5-featured.jpg"
url: "/2023/12/21/solus-4-5-released"
---

TODO

- resize the featured image to something smaller. we've used 1200x800 or so in past
- get proper screenshots
- ensure correct publish date
- write something better for "future" at bottom
- steal from https://github.com/getsolus/packages/issues/305
- search for TODO throughout

The Solus team is proud to announce the release of Solus 4.5 _Resilience_. This release brings updated applications and kernels, refreshed software stacks, and a new ISO edition featuring the XFCE desktop environment.

<!--more-->

## General

### Default applications

All our editions feature:

- Firefox 120.0.1
- LibreOffice 7.6.3.2
- Thunderbird 115.5.2

For audio and video multimedia playback, we offer software out-of-the-box that caters specifically to our desired experience for each edition.

TODO: are there other default apps worth highlighting?

- Budgie, GNOME, and MATE editions all ship with Rhythmbox for audio playback, with the latest release of the Alternate Toolbar extension to provide a more modern user experience.
- Budgie and GNOME ship with Celluloid for video playback.
- MATE ships with VLC for video playback.
- Plasma ships with Elisa for audio playback and Haruna for video playback.

### Pipewire by default

Pipewire is now the media framework for Solus, replacing PulseAudio and JACK. Users should notice no difference. For an demonstration of pipewire's out-of-the-box capabilities, see [this forum post](https://discuss.getsol.us/d/9596-showcase-noise-reduction-with-pipewire-and-easyeffects) about noise reduction for microphone inputs. 

### ROCm support for AMD hardware

We now package [ROCm](https://en.wikipedia.org/wiki/ROCm) for users with supported AMD hardware. This provides openCL acceleration for applications like Blender, and enables hardware accelerated machine learning with PyTorch.

###

### Hardware and kernel enablement

This release of Solus ships with Linux kernel 6.6.7, bringing wider hardware support and some interesting configuration changes. Some highlights:

- Our kernel config now enables all bluetooth drivers, sound codecs, and sound drivers
- `schedutil` is now the default CPU governor
- Kernel modules are no longer compressed during initramfs creation, reducing boot times
- We have modified our kernel to use the [BORE scheduler](https://github.com/firelzrd/bore-scheduler) by default. This is a modification of the default CFS scheduler optimized for interactive desktops. Under heavy CPU load the system will try to prioritize processes that it thinks are interactive, maintaining a responsive feel.


Mesa has been upgraded to 23.2.1. This introduces various improvements:

- Device-select and overlay vulkan layers are now enabled
- Added gallium zink driver
- Added gallium VAAPI driver
- Added IO support for built-in opengl overlay
- Added Vulkan support for Intel 7th/8th gen GPUs (which really aren't performant enough to make use of it but some hardware acceleration is better than nothing)
- Added ray-tracing support for Intel XE GPUs
- Added experimental Virtio Vulkan driver

## Budgie

{{< altimg "Budgie.jpg" "/release-images/4.5/" >}}

Solus ships with [Budgie 10.8.2](https://blog.buddiesofbudgie.org/budgie-10-8-2-released/), the latest release of the Budgie Desktop. Since the release of Solus 4.4, our friends over at _Buddies of Budgie_ have been steadily improving the user experience of Budgie and laying the groundwork for Wayland support.


### Dark style preference support

The "Dark Theme" toggle in Budgie Settings now also sets the dark theme preference for applications. Some applications may override with a specific color scheme; for example a photo editor may prefer a dark canvas, however  this standardized, vendor-neutral setting should help to create a more consistent experience for our users.

### Budgie trash applet

The _Budgie Trash Applet_, developed by Buddies of Budgie and Solus team member Evan Maddock, is now part of the default applets available on all Budgie installations. With this applet, users can efficiently empty their trashcan and browse contents for possible restoration.

### Quality-of-life improvements

- System tray icons can optionally scale with panel size.
- Notification system improvements, including slightly decreased memory usage.
- System tray improvements around inconsistent `StatusNotifierItem` implementations.
- Keyword support is now supported in fuzzy searching in Budgie Menu and Run Dialog: search terms like "browser" or "editor" should return better results.
- The privilege escalation dialog will now show the action description and action ID when graphical privilege escalation is requested.
- The battery indicator in the Status applet now enables users to chose power profile modes on supported systems.

Upstream release notes can be found [here](https://blog.buddiesofbudgie.org).

## GNOME

{{< altimg "GNOME.jpg" "/release-images/4.5/" >}}

Solus 4.5 GNOME Edition ships with GNOME 44.1

### Defaults configuration changes

- TODO

### Bug Fixes, cleanup & quality-of-life improvements

- TODO: david note: these bullets cribbed from gnome 44 release notes
- GNOME's file chooser now has a grid view, closing a long-standing feature request. You can now pick files based on thumbnails.
- Mouse and touchpad settings are now demonstrated visually.
- New accessibility settings have been added: sound over-amplification, enable accessibility features using the keyboard, permanent scrollbar visibility
- GNOME Settings now includes a Security menu showing the status of SecureBoot

Upstream release notes can be found [here](https://release.gnome.org/)

## XFCE

{{< altimg "XFCE.jpg" "/release-images/4.5/" >}}

In the [Solus 4.4 release post](/2023/07/08/solus-4-4-released) we announced our intention to deprecate the MATE Edition in favor of a new XFCE edition. The XFCE edition aims to fill the same niche as the MATE edition: users who prefer a more lightweight desktop experience.

The new XFCE edition includes:

- XFCE version TODO
- TODO other default apps introduced for XFCE
- TODO interesting OOTB configs

## Future of MATE installations

We are still working on a seamless transition path for existing users of the MATE desktop. In broad terms, we will provide a way for users to transition their MATE installations to XFCE. MATE will continue to be supported for existing users until we are confident in our transition plan.


## Plasma

{{< altimg "Plasma.jpg" "/release-images/4.5/" >}}

Solus 4.5 Plasma Edition ships with the latest Plasma Desktop 5.27.10, KDE Frameworks 5.112.0, KDE Gear TODO, and, the KDE branch for QT 5.15.11, which brings many new features. Some highlights:

- TODO

Upstream release notes for Plasma since Solus 4.4 can be found here:

- [Plasma 5.27.10](https://kde.org/announcements/plasma/5/5.27.10/)


### Defaults configuration changes

- TODO

## Download

Go to our [Download](/download) page and select direct download or torrent. Happy installing!

## Thank You

Big thanks to everyone backing us on OpenCollective. You have funded direct compensation of developer work, covered our modest infrastructure costs, and provided valuable ISO testing prior to the wide public release. If you are not a backer and that sounds like something you would like to be a part of, consider supporting us on [Open Collective](https://opencollective.com/getsolus)

TODO write something about tier changes?

Thanks also to all of you  who have helped build the Solus community; we love all your contributions! We encourage anyone who want to join the wider Solus community to check out the dedicated [Getting Involved page](https://help.getsol.us/docs/user/contributing/getting-involved) on our Help Center site.

## Future

2023 was certainly a busy year for Solus; we're excited to see what 2024 brings.


