---
title: Video prompts
excerpt: Configuration and best practices for creating video prompts in Recurly Engage.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Video

<Embed url="https://www.loom.com/embed/fe1d6051af2d417eb95dddb4702014f1?sid=9ccd4e6f-3e97-474d-8100-a4afc1561db2" href="https://www.loom.com/embed/fe1d6051af2d417eb95dddb4702014f1?sid=9ccd4e6f-3e97-474d-8100-a4afc1561db2" typeOfEmbed="iframe" height="400px" width="100%" iframe="true" />

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.

# Definition

A **video prompt** is an overlay that plays a video file with optional text and calls to action, designed to capture user attention in a modal window.

# Key benefits

* **High engagement**: Video content drives higher attention and conversion rates.
* **Customizable playback**: Control autoplay, looping, and mute settings for optimal UX.
* **Seamless integration**: Use the existing prompt designer—no additional coding required.

# Key details

## Video-specific configuration parameters

* **Video URL**: Link to the source video file. HLS format is recommended; MP4 files should be under 25 MB.
* **Video Cover**: Optional poster image displayed before and after playback.
* **Mute**: Best practice for autoplay videos to be muted by default.
* **Loop**: Enable continuous playback when the video ends.
* **Autoplay**: Play the video immediately when the prompt appears (browsers require muted autoplay).