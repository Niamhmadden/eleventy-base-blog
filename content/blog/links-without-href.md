---
title: Links without a href
description: This is a post on how to use links
date: 2023-07-04
tags:
  - accessibility
  - Development
  - Javascript
---

Recently, I worked on a small accessibility issue, the problem was a link which was being rendered as a button. We'll come back to the details of it later. Firstly, let's talk about the difference between links and buttons.

## What is a link used for?

A link is used to navigate the user to another location. This location might be, as noted by MDN, "web pages, files, email addresses, locations in the same page, or anything else a URL can address".

## What is a button used for?

A button triggers an action or event. We use buttons to submit forms (Save), to proceed to the next step in a process (Next), or to create or delete an item (New/Delete).

## Links without a href and accessibility

Back to the button which was meant to be a link. It allowed the user to view/download a file or open it in a new URL.

So, why was it being rendered as a button? It was missing a `href` attribute and was being passed an `onClick` function. It was set up like this because we only had access to the `href` after the link had been activated by a mouse pointer or keyboard.

A link with a missing `href` attribute is just a placeholder link and using the `onClick` prop with no `href` is bad for accessibility, as the output looks like a link but behaves like an HTML button.

It will also raise some problems for users of assistive technology, as it’ll let screen reader users know that they’ve landed on a button, rather than a link.

## The solution

The solution was to add a `href` with a unique identifier and to add `e.preventDefault()` to the `onClick` function. This ensured the user had enough context about what was being linked to and ensured the default href wasn't followed. Now the link was no longer a button, we also had the correct set of actions in our context menu. These actions include:

- Open link in new tab
- Open link in new window
- Open link in incognito window
- Copy link address
- Save link as...
