---
title: Refactoring CSS
date: 2018-09-18 00:00:00 +0000
layout: post
categories: []

---
My first task at my current job was to make the corporate site lighter, faster and more performant. This was supposed to set the stage for the new products we were to release in the next 8 or 9 months. So not only was it a matter of refactoring but it was building a base from which other apps and sites can be created or skinned.

Naturally, the first thing I did was take a look under the hood. I think most, if not all, front end developers instinctually go through this exercise whenever we see something that impresses or confounds us or otherwise just sparks some curiosity regarding the thought process or execution of a site or app. But as I started to peak at the underlying mark-up, JS and CSS, I had to take a step back and really think about what I was doing.

What was I looking for exactly? What was I going to do with the information?

I needed a plan I could follow and stick to. And so here is the plan I laid out for myself.

## The UI Inventory

I began taking a UI inventory of the entire corporate site. This was a long and boring task but a very necessary one. I went through every page on the site and took screen shots of every piece of UI. Starting from small units like paragraphs, buttons, list items, icons, etc. and ending with components, or chunks of UI comprised of individual units. This included cards, media objects, headers, articles, titled lists, navigation, and so forth. In the end, my UI inventory looked like this:

\[ui inventory image\]

The purpose of this was to get a bird's eye view of what I was dealing with. Once finished, I needed and wanted to learn and/or identify

\-    How are icons used?

\-    Is there a standard icon library?

\-    Is spacing between elements observed and respected consistently across the site (the same with color, typography, images)?

\-    Are there observable patterns in layout and structure that could be identified for re-usability?

// I separated out all these screenshots into their respective categories: images, typography, icons, images, components, and so forth.

After I had a better idea of what the UI consisted of, my next stop was the CSS. The site was built on top of the Twitter Bootstrap framework which was included in its entirety. No problem there. From my previous job, I was used to Bootstrap and had become familiar with a lot of its patterns and especially its documentation site. What was surprising and a little scary was that the custom CSS sitting on top of Bootstrap came in at around 4419 lines. I've seen extremely large CSS files in my time working at the City of Austin and John Deere. However, the EquiTrust site was less than 30 pages. Moreover, the design was minimal which further made me wonder why we'd have such a large file. I knew I had a lot of lines to sift through so as my old friend Oar Willie would say, "Onward thru the fog!"

## Reading the CSS

EquiTrust was not using a preprocessor so all the CSS was really in one large file. Not fun but not daunting, thankfully. I scrolled through the file to get a feel for the coding style, check if it was separated by sections, and identify any glaring issues I could fix quickly. I decided to make the initial scroll through a slow and deliberate inspection. I figured I will have to be intimately familiar with the CSS so might as well start immediately.

Having my UI inventory on one side and the CSS on the other, I had a sort of road map of things I wanted to see and places in the stylesheet I wanted to visit.

One of the first issues I wanted to tackle was the content width of the site. The main content of every major page on the site was consisted of a few paragraphs with 1 to three sentences each. This made for content to appear on one to two lines stretching across the entire site. I made it known before touching any code that this was the first issue I wanted to fix since it looked awkward and