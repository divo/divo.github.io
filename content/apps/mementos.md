+++
title = "{{< ico far fa-images >}} Mementos"
description = "Beautiful printed custom photo albums ready in a few minutes"
head_title = "Mementos"
+++
[**{{< ico far fa-link >}} mementos.ink**](https://mementos.ink)

## Overview 

Beautiful printed custom photo albums ready in a few minutes

{{< icon-image "/images/mementos-icon.png" >}}

## Problem
Every year I create photo albums for friends and family. I love to travel and this is a great way to show where I've been and generally what I've been doing all year.

I started by laying these out in publication software and having them printed up, then moved to using providers like Google Photos to do most of the work. I was still unsatisfied with the time it took to layout the pages, write up captions, and maybe come up with some interesting artwork to deliminate different trips or events.

Lastly, I just wanted to build something. I've spent my professional life working on web services where many aspects of the development cycle were done by someone else. I wanted to own a web app end to end, from conception, development, infrastructure provisioning and deployment.

## Solution
Mementos is my first attempt at building my own product. I wanted something quick and simple to use. Images are captioned by pulling the GPS coordinates from the EXIF metadata and transformed into captions using Mapboxes Placename API. Photos are grouped into sections based on the country they were taken in, and Mapbox is again used to generate title pages for each section. User update is restricted to editing the captions and deleting the pages after the inital upload.

![Map page](/images/mappage.png)

A Ruby on Rails application handles the business logic and provides the front end. The PDF rendering is done by a separate Node.js application. Building out a separate micro-service was another learning objective but in the end added an unwanted amount of complexity to the development effort. However, the bulk of the time was spent on the Rails application. Deployment, payment integration, provisioning of infrastructure, etc are all time-consuming when done from scratch. I invested some extra time to make these repeatable, e.x. provisioning and deployment are 90% automated. The biggest challenge turned out to be performance. Image processing can be relatively intensive and required several attempts to optimize. There is still room for improvement; the user is confronted with an ugly loading state when creating an album. The easiest way to deal with this would be to throw a bigger box at it and scale the number of workers but I'm not prepared to do that just yet.


I also used it as an excuse to get back into iOS development. It turns out that web upload in Safari strips out all of an image's metadata. The metadata I use to generate the aforementioned captions and sections (The metadata is removed when the image is encoded to a JPEG, not when it is uploaded. I'm unsure if it's completely intentional). This was frustrating but I managed to get an app together in about 2 weeks. Reusing the Rails app inside Web containers and only re-writing the parts that needed to be native saved a lot of time. 

{{< app-image "/images/mementosapp.jpeg" >}}

The result is a decently polished web and iOS application that solves the problem I started with. Upload a collection of photos and in a minute or two have a well-presented album ready to order.

- [{{< ico fa-brands fa-github >}} Rails](https://github.com/divo/photobook_rails)
- [{{< ico fa-brands fa-github >}} Node](https://github.com/divo/photobook_node)
- [{{< ico fa-brands fa-github >}} Canvas](https://github.com/divo/photobook_sketches)
- [{{< ico fa-brands fa-app-store >}} App Store](https://apps.apple.com/ie/app/mementos-albums/id6450715256)
- [{{< ico far fa-life-ring >}} Need support?](mailto:support@mementos.ink)
