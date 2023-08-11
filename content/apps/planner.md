+++
title = "{{< ico far fa-rectangle-list >}} Markdown planner"
description = "A simple daily planner. Fully customizable via a Markdown template."
head_title = "Markdown Planner"
+++

## Overview 
A simple daily planner. Fully customizable via a Markdown template.

{{< icon-image "/images/planner-icon.png" >}}

## Problem
I find taking the time to plan out and review my day to be very helpful. Being intentional typically means I get more done and end the day feeling satisfied with what I have accomplished. I've tried various systems, from simple notes with no structure to more elaborate systems like Getting Things Done and Bullet Journals. I wrote Markdown Planner with the idea to find a middle ground between pen and paper and apps like Omni Focus. I wanted the flexibility and speed of paper with some more modern features: notifications, searching, device sync and so on.

My projects always come with a secondary goal in the form of some sort of learning outcome. Here I wanted to learn how to use Swift UI and see if I could get the idea of a template defined at runtime to work with Swift UIs more-or-less static type tree.

## Solution
Markdown planner is a simple iOS app written in Swift and SwiftUI. The UI is generated from a Markdown template. Empty lines in the template map to text fields in the UI, checkboxes map to checkboxes and heading map to headings. I also added some markdown-ish elements to support notifications and dynamically addition of checkboxes.

Every entry in the journal serializes to plain markdown on the users device and files are synced over iCloud. Below is an example template and the UI it maps too.

```markdown

# this weeks goal

# before


## 1 hour of self improvement on

## todo
-[ ] 
-[ ] 
-[ ] 
+
## schedule
[9](09:00) 
[12](12:00) 
[17](17:00) 
# after
# habbits
-[ ] Anki
-[ ] Reading
-[ ] Coding
-[ ] Workout
# todays grade

## what will I do tomorrow?


## evening reflection / interesting blog post?


```

![Daily planer](/images/dailyplanner.png)

## Links

- [{{< ico fa-brands fa-github >}} Github](https://github.com/divo/dynamicplanner)
- [{{< ico fa-brands fa-app-store >}} App Store](#)
- [{{< ico far fa-life-ring >}} Need support? Open an issue](https://github.com/divo/DynamicPlanner/issues)
