---
title: "Response web design with css"
date: 2022-09-03T11:54:30+03:00
draft: true
---

## Responsive web design with css

**All Block level elements are Responsive**

Meaning they have 100% width of their parent container and height of their inner content.
therefore setting a custom width or height to the parent or child will come with a consequence which will make the element less responsive.
the problem is the element will eventually overflow. and we have to scroll to see all of the element.

__Percentages vs fixed width__

however setting the width with the percent will make this problem go away, however we don't want to set width or height of elements unless it is necessary.

specially heights are very dangerous as the screen size changes the element inside the container starts to overflow.
a way to combat this setting the height property is to use padding instead of giving it a height.

the take away here is we always want to be using padding or childs margin to specify the height instead of a fixed value or even a percent as it will overflow the content.

__em and rem__

em's get compounding effect, and root em(rem) will not.
since em's get compound be careful when using the ul when they indent goes on and on

and we usually should use the rem for font-size

one thing to use em quite frequently is for setting a padding and margin property on the parent container, this will make it more adaptive so that when the font-size changes the whole container will also get bigger. therefore when we are using media query we are only changing the font-size and the whole thing adapts beautifully. they are very helpful to with a media query letter on.

max and min width and height

max-width usually is helpful when it comes to giving the width of a fixed size for a bigger screens
usually we don't want to use the min-width as it will try to fight the default responsiveness of css. it is like using height don't use it unless it is very necessary.

when setting a max with it usually is in px

vw vh and vmin and vmax

vmax takes the largest side either the width or the height of the viewport and deciede to use vw or vh based on that.
so if the screen is wider then vmax will be the same as vw else it will me vh. 

so usually it is useful when it comes to mobile and desktop design choices

it is also a good practice to use the vw or vh for the font-size of the title texts, but we have to clamp it for big and very small size screens.
again, it is a good practice if we are using it for titles and heading texts not on paragraph as they will shink a lot and make it less visible.

now you already be asking what to use vw or vh? and usually this is where vmax and vmin comes in. usually the vmin
else if we are using vmax it usally will not decrease the size, it just gets bigger and bigger.

summary

In this first week, we've looked at:
Using percentages for widths
Avoiding to set heights
Using max-width

While there is nothing overly complicated with any of that, being comfortable with these things is the key to mastering responsive layouts.

With a good understanding of the above, all we need is a little flexbox and we're going to start knocking even complex layouts out of the park!

In this section of the course, you can find a few links to some extra reading that you can do if you're looking to continue learning a bit. They'll help supplement what we're covering here, but none of it is required reading 😊.

I'll be sharing my solution to the challenge tomorrow. If you're a little bit behind at this point, you can use today and tomorrow to catch up a little.

[read](https://css-tricks.com/tale-width-max-width)

## Flex-box

flex items tries to be the smallest size they could be, so if there is no content they would not be visible.




### css combinator

example

```css
.col + .col {
    /* this code will run when it has a column before it. */
    /* this usually is used to add a margin to the middle childrens */
}
```

### Responsive Images

things to always do as a global css to have a responsive image

```css
img {
    /* this way no overflowing or side scrolling */
    max-width: 100%;
}
```