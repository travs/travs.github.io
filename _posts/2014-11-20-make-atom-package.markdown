---
layout: post
title: "How I Made a Package for Github's Atom"
date: "2014-11-20 17:39"
---

### Identify a need

As I stated in [my previous post](/2014/09/30/learning-javascript/), I had to submit assignments in .pdf, but I liked writing in markdown, for convenience and the sleek look of a rendered file. There was no solution for going directly from editing markdown in Atom to a pdf, so I decided to hack one together.

I was just beginning my js journey at this point, so I had no experience with coffeescript, which most of the packages seem to be written in. Thanks to [a helpful article](http://blog.fxndev.com/create-your-first-atom-package-in-js/), however, I was well on my way to making my first package with vanilla javascript.

### Note the steps needed to get there

In order to get a pdf with the same styling as a rendered Github Flavoured Markdown, I would need to convert the markdown file to HTML with the same styles that Github uses, then capture this styled HTML in a pdf.

*Basic rundown:*

I decided to go with [Marked](https://www.npmjs.org/package/marked) because it claims to support Github Flavoured Markdown by default.

Next, the active theme's styles are extracted and appended to the beginning of the HTML, and all of this is fed into [html-pdf](https://www.npmjs.org/package/html-pdf), finally yielding a beautiful pdf file.

### Fill in the gaps

With this basic pipeline of `markdown | html | css/html | pdf`, I set out on my task.

Even with this simple converter, there were a number of housekeeping tasks to take care of, like making sure the html body was tagged properly, and making the 'user experience' a little more sane/safe.

Most importantly, I had to learn *asynchronous programming*; a style of programming that I was completely naive to previously, but this was a fun challenge.

### Lesson learned

There was a lot of trial and error involved, and I had to go through a number of markdown renderers and html-pdf "converter" modules before I found the combination that worked. Next time I will try these npm packages out on the command line, which is much quicker than including them in my package, updating the package and going from there.
