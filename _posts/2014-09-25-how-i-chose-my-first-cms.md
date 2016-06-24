---
layout: post
title: How I Chose a CMS for my First Blog
---

-----

### The decision:

Like many other aspiring developers, I took the leap and decided to start a personal blog. I want some way to document the knowledge I gain in programming, but also have it accessible to others who might learn from my mistakes.

I was convinced by [this](http://www.hackreactor.com/blog/no-cs-degree-programmer-engineer) post, which describes one way to develop a CS background without having a degree in CS. The article was also published on my birthday, so I took the coincidence as a sign that I should at least give it a shot.

Now it was time to choose a platform to start blogging under.

### The options:
After some light googling, I decided not to go with WordPress, if only to try something *slightly* outside the norm. Since this is my first blog I imagine my choice will not be final, and I plan to try some other CMS options in the future. This being said, I narrowed my scope to include:

* [Jekyll](http://jekyllrb.com/) - Famously lightweight and customizable. GitHub friendly.

* [Octopress](http://octopress.org/) - Recommended by that blog post. Uses Jekyll under the hood.

* [Anchor](http://anchorcms.com/) - Looks  simple. Claims to be lightweight and easy to install.

* [Wardrobe](http://wardrobecms.com/) - Also seems simple and prettily-designed.

* [Dropplets](http://dropplets.com/) - Again, looks very simple to use. Supports the lovely [Markdown](http://daringfireball.net/projects/markdown/) format, like the above options.

I was looking for something **simple to use** for a first-time blogger, but also very **customizable**. Oh, I also wanted something **free** which would mean it was probably **open source**.

Before I get into the reasoning, note that I am not giving an analytical review of these options, so if you helped work on one of the above projects and I've overlooked everything, please be merciful and shoot me an email.

#### Not Octopress
I googled around and [dug up](http://joelmccracken.github.io/entries/moving-back-from-octopress-to-jekyll/) [some](http://www.kevindangoor.com/2012/03/wordpress-to-octopress-and-back/) [posts](http://joelmccracken.github.io/entries/moving-back-from-octopress-to-jekyll/) that made me want to avoid Octopress, at least for my first blog. Why?

* The alleged abandonment of the project.
* Looks like it has some features that I will (might?) not need.

#### Dropplets?
I love the look of their homepage and example website, as well as the easy-as-pie setup. Why didn't I go with Dropplets then?

* **"Theme Marketplace"**.
I understand that the people who make these platforms also need to make a living, and I have nothing against paying for something I think has value, but since this is my first blog, I wanted to go completely free with the themes.

Another day Dropplets.

#### Wardrobe or Anchor?
The minimalistic design of these two caught me from the start, but there does not seem to be *quite* as active a community around either of these projects as there is around, say, Jekyll.

The latest blog post in the Anchor dev was just a few months ago, while the Wardrobe blog was last updated over a year ago.

#### What about Jekyll?
I have seen blogs that use Jekyll, and I like the idea of being able to easily (and freely) deploy to [GitHub Pages](https://pages.github.com/). Notes:

* It looks a little more involved to set up, but I can *understand how it works*.
* gh-pages is great, but I already have access to server space, so that's not a factor in my decision.
* It has an [active community](https://github.com/jekyll/jekyll), which is bound to be a resource when adding features/customizing. Also, if I were to contribute some code, more people would benefit from it than a more stale project.

#### The verdict:
I chose to go with **Jekyll** because of the hyper-active community, as well as the customization and simplicity it offers. If I need more features, I will add them in the future.

I am eager to get started with writing, so I will clue up this post here. In all, my values (active community/customization) informed my decision, so examine your personal values - what you want from your blogging platform - and then choose.

#### Caveats, cavdrinks
I still have a lot to learn about blogging, but I like an active community, and if you're reading this then Jekyll is easy enough for a beginner to use and hasn't broken yet.

I didn't fully consider the *database-driven vs static HTML* distinction in this article, and I know that's important to some. Jekyll is more along the lines of a static site generator.
