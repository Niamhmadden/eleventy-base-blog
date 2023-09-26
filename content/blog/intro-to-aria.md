---
title: Introduction to ARIA
description: This is a post introducing ARIA.
date: 2023-07-01
tags:
  - accessibility
  - ARIA
  - videos
---

<iframe width="100%" height="350px" src="https://www.youtube.com/embed/WJigEBef8Yc?si=Ewl0f_EYBCTb5X7O" title="Introduction to ARIA" frameborder="0" allow="accelerometer;clipboard-write; encrypted-media; picture-in-picture; web-share" allowfullscreen></iframe>

This marks the first video in a series about aria and using it responsibly. Now, this is an introductory video, so i'm going to cover what ARIA is and how we can - and can't (or shouldn't ) use it in our projects. I'm going to cover the topic in much more detail, with more nuance, in subsequent videos so if you have any questions feel free to send me them on LinkedIn or via email. Also, any material that I reference or I think is useful will be linked below so you can access it whenever you want.

Who is this video for? Well, it's for anyone with an interest in or involved in making accessible products. But it's going to be most relevant for designers and developers.

So, let's get going.

## What is ARIA?

ARIA is a set of attributes that extend and supplement native HTML in order to make elements accessible to assistive technology.

These attributes consist of roles, states, and properties.

So an aria role, describes what an element is, and by extension, how it can be used. So, if we have an element with the role of link, we expect to be able to activate the link and be taken somewhere. an aria state, gives information on the state of the element. So a button might be pressed or an input might be checked. Aria properties refer to properties of an element, this include things like: the name, description or value.

Now, aria properties are likely to be static. Which means they'll like stay the same throughout their lifecycle. Whereas aria states are likely to be dynamic. So a button wont always be pressed. A checkbox wont always be checked.

Let's take a look at roles. By default, many HTML elements already have implicit roles mapped to them. You can see here, when we inspect the accessibility tree, the button element already has a role of button.

`<button  class="btn" >HTML button</button>`

There are some HTML elements, however, that don't have an implicit role and we have to explicitly define them. Say we want to make a div element into a button, we would need to define the role of button explicitly. Now, this is just an example and isn't advised because we already have a native HTML element with that role.

`<div tabindex="0" role="button" class="btn">ARIA Button</div>`

When using ARIA in our projects there's some things to consider.

## Not all aria roles, states, properties are available to use on HTML elements

Some attributes aren't valid. For example, you can't use a `role="heading"` on a HTML `button` as a `heading` is non-interactive and a `button` is an interactive element. So that can cause some confusion.

`<button role="heading" class="btn">Heading button</button>`

## Some ARIA roles can only be used as a child to specific role

For example the `tab` role is only valid in the context of `tablist`.

Likewise, a `menuitem` role should be used in the context of `menu` or `menubar`.

There's more info on usage in the w3 specifications, which will be linked.

## What does ARIA not do?

Aria changes the information in the accessibility tree, but it doesn't change the elements in the DOM tree. The accessibility tree is where assistive technologies get their information from. Whereas the DOM tree paints a visual picture of the elements on a page, we can think of the accessibility tree as painting a non-visual picture.

Aria also doesn't add behaviour to an element. If we make a custom button with a div element with the role of button (which isn't advised by the way). We would then need to code all the interactions that are expected on a button using javascript. for example, it would need to be focusable, we need to be able to press it, and it should do something when it is pressed. We're going to look at a live example of this in an upcoming video.

## Overview

For now, let's wrap up with a quick overview.

So, Aria is used to supplement and extend HTML.
We can do this by role aria roles, states, and properties.
We need to be aware that not all of these attributes are available to use on some HTML elements.
and though aria adds meaning, it does not add behaviour - that parts on us to implement.

Thank you for listening and if you have any questions, feel free to reach out to me.

### Resources

<a href="https://webaim.org/techniques/aria/" target="_blank">Intro to ARIA (opens in a new tab)</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA" target="_blank">ARIA - MDN (opens in a new tab)</a>

<a href="https://www.w3.org/TR/html-aria/#:~:text=Authors%20MAY%20use%20the%20ARIA,of%20a%20given%20HTML%20element." target="_blank">Usage of ARIA roles (opens in a new tab)</a>
