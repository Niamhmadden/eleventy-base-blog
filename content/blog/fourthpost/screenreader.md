---
title: Screen reader basics
description: This is an introductory post to using a screen reader
date: 2023-07-17
tags: accessibility
---

A screen reader is a piece of assistive technology that reads what’s on the screen, most commonly used by those with blindness or low vision. It’s usually operated using only a keyboard.

## How people navigate with screen readers

Those who may have little experience with using screen readers may think that they have to listen to all of the content on a web page during testing.

However, experienced screen reader users use a combination of methods that allow them to efficiently navigate web pages and quickly find information on a page. Using these same methods can be effective when it comes to evaluating web sites with a screen reader.

### Non-linear navigation

Most people don't listen straight through an entire web page nonstop. They're more likely to first navigate by landmark regions, headings, links, or some other method, and then listen only to the part they're interested in.

### Screen readers allow users to navigate to headings, landmarks, and other features

Even though content is linear from a screen reader point of view, screen readers allow users to navigate by other elements, such as:

- Landmarks (sections of the overall design, including the header, navigation, main content, and footer)
- Headings
- Links
- Tables
- Form elements
- Graphics
- List items
- Iframes

## Screen readers work with semantic markup

The only way that users can navigate by these semantic elements is if the semantic elements are present in the markup in the first place. They can't navigate by headings if there are no headings (`<h1>`, `<h2>`, etc.), or if there are only fake headings (e.g. paragraphs with big bold text).

## Always test with a screen reader

Learning a screen reader can seem intimidating at first, but it's the only way to test that a screen reader actually works accurately. Automated tools don’t accurately determine where the keyboard focus should be at any time.

The most important reason to test with screen readers is because real people use screen readers and need access to them.

## Accommodating different screen readers

All screen readers share similar functionality. However, keyboard shortcuts, voices, and ways of calling out links, images, and so on, can vary between them. Users will be accustomed to the one they use, therefore these differences don’t typically impact coding practices.

The key is to adhere to generally-accepted accessibility techniques.

## Additional resources

[NVDA keyboard shortcuts](https://dequeuniversity.com/screenreaders/nvda-keyboard-shortcuts)

[VoiceOver for Mac](https://dequeuniversity.com/screenreaders/voiceover-keyboard-shortcuts)
