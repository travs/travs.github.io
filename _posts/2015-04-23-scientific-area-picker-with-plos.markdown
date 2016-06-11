---
layout: post
title: "Scientific Area Picker with PLOS"
date: "2015-04-23 23:15"
---

## Background on the Problem

While working on [TReND-links](http://travs.github.io/TReND-links/) ([read up on it here](/2015/04/20/implement-contact-sharing-service.html)), I designed a signup form for new users.

One of the questions on the form asked the main research disciplines that the user has participated in.

Discussions with the folks at TReND made it clear that we needed an authoritative selection of "scientific disciplines" for the users to pick from. This would eliminate the chance of misspelling, enforce some kind of order, and make the database more user-friendly, especially for searching.

## Add some Authority

We settled on the "subject areas" of [PLOS](http://www.plosone.org/taxonomy), since they have a good reputation for openness in the scientific community, and also have a [downloadable thesaurus](https://github.com/PLOS/plos-thesaurus) of terms they index by in their own search engine.

They even have a taxonomy browser on their website, which is almost exactly what we wanted!

<img src="/assets/images/plos_picker.png" width="100%"/>

After contacting PLOS, however, I was informed that there was no official API for accessing the terms, and no embeddable tree diagram for them either.

No biggie; I'll just make one.

## Synthesis

Rather than reinventing the wheel, I found a perfectly fine implementation of a [treeview in Bootstrap](https://github.com/jonmiles/bootstrap-treeview). All the hard work was done for me this time :-)

The treeview took a certain format of JSON as its data, so I had to make [a parser](https://github.com/travs/PLOS-Subject-Area-Explorer/blob/master/parser.js) that extracted and formatted the data correctly.

[It works just as it should](/examples/plos-subject-area-explorer.html). Sweet.

## Nitty-gritty

Now there were just [a few little implementation details](https://github.com/travs/TReND-links/issues/15#issue-70540353) I needed to take care of before I put it on TReND-links.

[A little jQuery and JS](https://github.com/travs/TReND-links/blob/e8e02eceb02ca92c22df6a85284fdc89638e7d25/javascripts/form.js) later and we're in business.

## Check it out

You can take a look at a live PLOS subject area explorer [here](/examples/plos-subject-area-explorer.html), or check out the repo [here](https://github.com/travs/PLOS-Subject-Area-Explorer).
