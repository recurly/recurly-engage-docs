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
<div class="rp-page">
<div class="rp-overview">Video Prompts play a video file inside a modal overlay, with optional text and calls to action layered on top. Control autoplay, looping, and mute behavior right from the existing prompt designer—no extra coding required.</div>

<Embed title="" typeOfEmbed="iframe" url="https://www.loom.com/embed/fe1d6051af2d417eb95dddb4702014f1?sid=9ccd4e6f-3e97-474d-8100-a4afc1561db2" height="400px" width="100%" href="https://www.loom.com/embed/fe1d6051af2d417eb95dddb4702014f1?sid=9ccd4e6f-3e97-474d-8100-a4afc1561db2" />
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
</div>
</div>

### Prerequisites

<ul class="rp-list">
<li>Company, App Administrator, or App Member permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">A video prompt is an overlay that plays a video file with optional text and calls to action, designed to capture user attention in a modal window.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>High engagement</strong><span>Video content drives higher attention and conversion rates.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Customizable playback</strong><span>Control autoplay, looping, and mute settings for the best user experience.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Seamless integration</strong><span>Use the existing prompt designer—no additional coding required.</span></div>
</div>

# Key details

## Video-specific configuration parameters

<table class="rp-params">
<tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
<tr><td>Video URL</td><td>Link to the source video file. HLS format is recommended; MP4 files should be under 25 MB.</td></tr>
<tr><td>Video Cover</td><td>Optional poster image displayed before and after playback.</td></tr>
<tr><td>Mute</td><td>Best practice for autoplay videos to be muted by default.</td></tr>
<tr><td>Loop</td><td>Enable continuous playback when the video ends.</td></tr>
<tr><td>Autoplay</td><td>Play the video immediately when the prompt appears. Browsers require muted autoplay.</td></tr>
</table>
