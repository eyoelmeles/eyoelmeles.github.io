---
title: 'Color System'
date: 2024-02-18T10:49:40+03:00
draft: false
---

> Choosing a color system really depends on the project size and complexity,
> we should use color to guide the users to use the app in the right path (happy path)
> It is very useful to document the process to convince clients for visual language and branding

For the very basic color system

The whole thing about colors there are only three color categories

- **Brand color** ( buttons, icons, links …)
- **Supporting color** ( usually to draw attention, used less often than brand colors, usually error messages, confirmation, information)
- **Neutral color** (Most of the UI is from this category, some form of gray. Text, background, secondary button, border color).

### Branding color

To Pick a brand color we need to pick something in between the shade and tint

which usually means, 

1. it will be in the right corner of the color picker,
2. works well (accessible) as a button background color.
3. As a background it should have enough contrast for both the dark and light colors of the UI

### Supporting color

These also include the secondary colors.

there are very common colors to always consider, which are

1. Green
2. Yellow / Orange
3. Blue
4. Red

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/f2e3e9f7-369f-4380-9ce4-ed064d0eea85/fce7306e-9e65-4af2-a2b3-f57d8fe840b0/Untitled.png)

> This whole thing is a ***Shade of Supporting color `blue`***
> 

The Important thing to consider is that, we should have the same Saturation and Lightness value as the brand color, we should only have big number difference in the Hue value, when compared to the brand color.

The 900 is usually of a value of 90 - 100 Saturation and Brightness value = 20-30 

The 100 is usually of a value of 20-30 Saturation and Brightness value of 90-100

But for neutral colors we do the reverse for the Saturation and Brightness value.

| Color System |
| --- |
| Primary |
| Secondary |
| Neutral |
| Black |
| White |
| Main |

Each will have a shade of on specific color

Again depending on the complexity of the app, we usually have 9 colors, the median is the actual color, to the left is darker also called `shade` and the right will be lighter also called `tint`

to do so in Figma

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/f2e3e9f7-369f-4380-9ce4-ed064d0eea85/c4cc707a-4e24-4f80-8de6-9b46abf9ff17/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/f2e3e9f7-369f-4380-9ce4-ed064d0eea85/dace757a-7a3f-4df4-b115-adcfd3422602/Untitled.png)

select the next color, and apply the color before it, then change the color  type to `HSL aka Hue Saturation and Lightness` and then **Decrease Saturation and Lightness for Shades** and **Increase Saturation and Lightness for tint,**

> To increase by constant value, use SHIFT + UP / DOWN ARROW
> 

[]()

> another easy way of doing colors from mood board is to use `Foundation Color Generator` or `Material Theme Builder` plugins to do the job for us.
> 

Any color choice should satisfy the following

1. Do you have all the color options you need
2. Does it look astatically pleasing
3. Do the colors feel like they fit together
4. Does it pass the color contrast checker

to Check for color contrast and color blindness, use `stark` plugin

### For implementation

> we should always choose same colors for same purpose for consistent ease of use through out the application
> 

### For Background

> Avoid using mid tone colors for background
> 

common rule of thumb is that  if the app is text for the most part use white backgrounds

and if it is more of photos and videos use darker background color

- also consider day and night time, for the product, if usually is used at dark use dark by default, also dark use less battery.

### Interactives

> use the brand color for those, however not as frequently as possible
>