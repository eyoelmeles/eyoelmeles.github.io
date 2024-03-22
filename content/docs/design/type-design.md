---
title: 'Type Design'
date: 2024-02-18T10:49:40+03:00
draft: false
---

# Type Design

> The whole idea is to show importance hierarchy and increase readability
> 

**Hierarchy**: A typographical scale is essential for creating a visual hierarchy in your design. it is important to establish a clear relationship between different elements of your design using typography.

Consider which element should be emphasized and use font sizes and weights to create hierarchy.

**Legibility**: The typography you choose should be easy to read and legible at different sizes. when selecting a font, pay attention to your size, weight, and spacing of the letters, as well as the contrast between the text and the background. You should ensure that the font you choose is easy to read on different devices and in different lighting conditions.

**Consistency**: Consistency is key when building a typographical scale. Use a consistent font family and font size through out your design to create a cohesive and professional look. Establishing consistent typographical elements also make it easier for the users to understand and navigate your interface.

**Accessibility**: As a designer, it is important to consider the needs of all users, including those with visual impairments. When designing your typographical scale, consider using high contrast fonts and providing options for users to adjust *font size* and *line spacing*

**Flexibility**: Your typographical scale should be flexible enough to accommodate different content types and length. Consider creating a range of font sizes and weights that can be applied to different element of your design, depending on the content and its importance.

### Readability

- `No Widow line` : This means we should not left one word alone in a new line.
    
    we should accommodate the article so we don’t end up with a widow line.
    
- Sentences should be lined based on how they read.
    
    *Example*: 
    
    Flexibility: Your typographical scale should be flexible enough to accommodate different content types and length.
    
    Consider creating a range of font sizes and weights that can be applied to different element of yo design,
    
    depending on the content and its importance.
    
    here on the above paragraph we try to break the sentences down into their own lines so the reader can have a good read.
    
    also make sure to use small text and full width to see as the writer intended it to be,
    

## building type-scales

These are the list of Scales, although we can create our own if we need to.

| Name | Scales |
| --- | --- |
| Minor Second | 1.067 |
| Major Second | 1.125 |
| Minor Third | 1.200 |
| Major Third | 1.250 |
| Perfect Forth | 1.333 |
| Augmented Forth | 1.414 |
| Perfect Fifth | 1.500 |
| Golden Ratio | 1.618 |
- Material UI uses the **Major Second type scale (1.125 this is the multiplier, 14 * 1.125 = 16, 16 * 1.125 = 18, …)**, with 14 as its key base size.
- Apple uses the 17 as their key base size, which is the minimum font size for their type system
    - Apple suggests to use Regular fonts sparingly

### Tools to help with Type Scales

[Good Article about Type Scale](https://spencermortensen.com/articles/typographic-scale/)

[For generating typescale](https://m3.material.io/styles/typography/type-scale-tokens)

[More read about typesccale](https://typescale.com/)

First thing to do is to know what we are using it for AKA **The type styles,** common examples are for Display, Headline, title, body, and label. 

- Usually we would have multiple headings, like h1, h2 .. and displays are for really really big dominant texts

### Creating a type style

when creating a text style, the line height for the text should be the font-size + 8, and then round it to the closest number divisible by 8

*Example:* 

if *Font-Size* = 57, then the Text-Height should be 57 + 8 = 65, this would round to 64

** Google Material Design **

Common example for the typeface, assume we are using ROBOTO font.

| type-face | Font-Size | Line Height | Conning(Spacing between characters) |
| --- | --- | --- | --- |
| Display 1 | 57 | 64 | 0 |
| Display 2 | 45 | 52 | 0 |
| Display 3 | 36 | 44 | 0 |
| Heading 1 | 32 | 40 | 0 |
| Heading 2 | 28 | 36 | 0 |
| Heading 3 | 22 | 30 | 0 |
| Body | 16 | 22 | 0 |
| Body Small | 14 | 22 | 0 |

** Apple Human Design **

| Title  | Font Size | Line Height | Kerning |
|-------|-----------|-------------|---------|
| Large Title | 34pt | 41pt | 0.37pt |
| Title 1 | 28pt | 34pt | 0.36pt |
| Title 2 | 22pt | 28pt | 0.34pt |
| Title 3 | 20pt | 25pt | 0.38pt |
| Headline | 17pt | 22pt | -0.41pt |
| Body | 17pt | 22pt | -0.41pt |
| Callout | 16pt | 21pt | -0.32pt |
| Subhead | 15pt | 20pt | -0.24pt |
| Footnote | 13pt | 18pt | -0.07pt |
| Caption 1 | 12pt | 16pt | 0pt |
| Caption 2 | 11pt | 13pt | 0.06pt |

For **Conning we can eyeball it, also usually good fonts have good conning. so we can leave it as 0**

Finally we can use `Text Styles Generator` plugin to generate the local style for us. we just need to name the text, and select all of them and run the plugin.

