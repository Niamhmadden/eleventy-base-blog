---
title: HTML Landmarks
description: This is a post on landmark regions
date: 2023-07-20
tags:
  - accessibility
  - HTML
---

Today we're going to look at landmark regions: what each of them represent, how to identify them and some best practices for using them.

## What is a landmark?

By definition, a landmark is a geographical location that allows people to easily identify where they are (think prominent buildings or statues: the Eiffel tower in Paris, or the Pyramids in Giza).

Landmarks on the web can be used to communicate important information on a page to people using a screen reader. They are a structural mechanism that help screen reader users orient themselves on a page and quickly navigate to where they need to be.

Screen readers use the accessibility tree that is exposed to the browser to get information about the page. To do this, landmarks need to be implemented correctly using semantic HTML (we'll get to this later).

## Landmark regions and their associated HTML

There are eight landmark regions that can be defined by eight ARIA roles. For most landmarks, a HTML element exists to semantically represent the landmark and implicitly map to its ARIA role.

The types of landmarks include:

## `banner`

The banner landmark contains global information like a company logo, main site navigation, and user login links. A website should ideally expose on banner region.

To create a `banner` landmark, we can use the `<header>` element. When the `header` element is used as a direct child to the `<body>` element, it has an implicit `banner` role and is therefore exposed as a `banner` to screen readers.

When the `<header>` element is used as a child of sectioning elements like `<article>` or `<section>` it is not meant to be exposed as a `banner` region.

## `navigation`

A `navigation` landmark contains navigational information (usually links) used to navigate a website. The HTML element `<nav>` has an implicit role of `navigation` which means it can be used to create a `navigation` landmark.

A single document may have a primary navigation, a breadcrumb navigation, and other navigational elements. As with other landmarks that appear multiple times in the document an accessible name or label should be given to them so users can easily distinguish their purpose. We can do this by:

1. Adding an `aria-label` attribute.
2. Using the `aria-labelledby` attribute if an existing element on the page should be used as a name. For example, we might have an existing heading on the page that accurately describes the navigations purpose.

## `contentinfo`

Another global landmark region (like `banner`) is `contentinfo`. It typically contains contact information, copyright, and links to privacy and accessibility statements.

In most browsers, the `<footer>` element is mapped to the `contentinfo` role when it is scoped to the `<body>`. When a `<footer>` element is contained within other sectioning elements, it is not meant to be exposed as a `contentinfo` landmark.

There should be no more than a single instance of `contentinfo` within the page. If there's a case where it's necessary then a `aria-label` should be provided to each `contentinfo` to distinguish between them.

## `main`

The `main` landmark is used to represent the main content on the page.

There should be one `main` landmark on each page. Having multiple mains would be confusing and use to usability issues. If there is more than one `main`, which one designates your primary content.

A `main` landmark is natively exposed by the `<main>` HTML element and it should be a direct child of the `body` element.

## `form`

If a form has an accessible name it is exposed as a `form` landmark. The `<form>` HTML element isn't treated as a landmark by default.

Forms can be given an accessible name by using the `aria-labelledby` attribute.

## `search`

When a form is used for search functionality, the `search` landmark can be used instead of the `form` landmark. A `search` landmark might also be present on an existing form, where the form has conventional input fields and submits data.

There is no HTML element that maps to the `search` landmark. A `role="search"` attribute is used to define a `search` landmark.

## `complementary`

The `complementary` landmark contains information that is considered secondary to the main content. It should be related to the main content but also should be meaningful on its own. An example of `complementary` content is a list of related blog posts.

You can create a `complementary` landmark by using the `<aside>` element.

## `region`

A `region` landmark is suitable for content that is important but can't be contained within other landmark regions. The usage of `region` landmarks should be limited.

A `<section>` element can become a `region` landmark if an accessible name is given (`aria-label` or `aria-labelledby` attribute). An element can also represent a region via ARIA’s `role="region"` (which would also require an accessible name to be exposed).

## Multiple landmarks of the same type can be used

There are times when we might have multiple landmarks of the same type on one page. For example, we might have a primary navigation and a secondary navigation.

A unique label can help distinguish them from each other, and provide context to people who many be new to using landmarks to navigate a page. An example would be adding an `aria-label` to each one.

Don't use the landmark role as part of the label. For example, a navigation landmark with a label "Primary Navigation" will be announced by a screen reader as "Primary Navigation Navigation". The label should simply be "Primary".

## Use as few landmarks as possible

Too many landmarks dilute the purpose of them. The more landmarks on a page, the harder it becomes for screen reader users to quickly navigate a page.

A good rule of thumb is to use few landmarks but ensure that all the important content is contained within a landmark.
