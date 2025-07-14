---
title: Dynamic Image Resizing
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When rendering prompts for different screen sizes on TV devices, you may elect to utilize the Redfast dynamic resizing feature to deliver an image asset sized no larger than a specified max height. In order to request a dynamically sized image, you simply add a screen\_size parameter to the image request. Note that this feature only works for images hosted by the Redfast platform. If no screen\_size parameter is specified, or an invalid value is specified, the original image will be returned.

### Query Params

* screen\_size: Accepted values are `1080`, `720`, and `480`

### Example Request

GET `https://abcdef.redfastlabs.com/assets/test.png?screen_size=720`
