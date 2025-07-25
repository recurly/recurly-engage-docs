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

<br />

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

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