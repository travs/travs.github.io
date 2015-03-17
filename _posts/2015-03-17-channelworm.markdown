---
layout: post
title: "Adapting a Data Access Layer for Ion Channel Modeling"
date: "2015-03-17 17:27"
---

###The project

So I've been working with [OpenWorm](http://www.openworm.org/) off and on for a while now, mostly with the subproject that deals with data storage and retrieval (read "access"), [PyOpenWorm](https://github.com/openworm/PyOpenWorm/#pyopenworm).

The idea, as the link states, is to have a simple access library for all things *C. elegans*.

I mainly did some testing and small changes to the scripts that were present already, then some documentation editing, while most of the main modules' code was left to the [other contributors](https://github.com/openworm/PyOpenWorm/network/members).

Now it's time for me to write modules myself!

###The new subproject

[Vahid](https://github.com/VahidGh) and I have been working together for a bit now, on his new project [ChannelWorm](https://github.com/VahidGh/ChannelWorm#channelworm), which is to be a data, model and simulation hub for ion channels in OpenWorm's in-silico cells.

I have started adapting PyOpenWorm to ChannelWorm by adding new Python classes and attributes which correspond to ion channel "objects" and their properties.

The ultimate goal is to have a data model that will allow access to information about every aspect of an ion channel that is relevant to biological modeling and, ultimately, simulation.

You can check out code that is finished and work that needs to be done in ChannelWorm [over here](https://github.com/VahidGh/ChannelWorm).

There is still lots of room for other volunteers! :)
