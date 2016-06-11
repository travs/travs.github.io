---
layout: post
title: How to Implement a Contact-Sharing Service
date: 2015-04-20
---

As described in [another post](2015/04/18/trend-links-platform/), I have built a contact-sharing platform for scientists, working with [TReND](http://trendinafrica.org), an organization helping researchers in Africa.
Check out my other post and the TReND website for more information on what they do; this article is about [TReND-links](http://travs.github.io/TReND-links/)' implementation.

## The Big Picture

The idea behind TReND links was to provide an easy-to-sign-up-for service where scientists could share their contact information and research interests with each other.

I decided to use [Jekyll](http://jekyllrb.com/) and Github Pages to make the site, since they would let me quickly deploy a prototype, and I had a blast using them in the past.

After I stumbled upon [Jekyll-db](https://github.com/rypan/jekyll-db), I though it would be a piece of cake. This project lets you specify entries in the "database" as regular jekyll posts stored in `/_posts`, and then displays them in a neat, searchable table!

Awesome. With some modification to allow non-database posts, I was able to quickly whip up a prototype that looked good, and was functional.

Now, to collect user data I opted for [Google Forms](http://www.google.com/forms/about/), since it's free and simply stores data in a [Google Sheet](http://www.google.com/sheets/about/). This was great, and future editors of the site would have no trouble making changes if need be.

With a few example posts in the Jekyll `_posts` directory, I was ready to show off the site to the world.

## The Little Things

I was excited! That is until I realized that whoever was maintaining the site (not me) would have to create a YAML-formatted markdown file in `_posts` manually with each new entry coming in from the form.

This may not be too much to handle, but it would be better to have an automated solution in case things get busy.

Enter the awesomely-integrated [Google Apps Script](https://developers.google.com/apps-script/) (GAS).

## Driving Automatic

With GAS, I was able to pull all the user-entered data at each form submit, and then transform it into a YAML-formatted front matter block; the kind that Jekyll-db uses for its entries. Sweet.

Now only one issue remains: how to get the data from GAS to the Github repo that TReND-links is hosted from.

Each new entry in the database needs a new post file, and we can [create files with Github's API](https://developer.github.com/v3/repos/contents/#create-a-file).

Ultimately, GAS piped the YAML-formatted user data back into the form's data sheet, where it lived in a separate column from incoming form data.

Using a service called Zapier, I was able to watch for changes in the TReND-links sheet's rows, and react to them. I whipped up [a "Zap"]() that created a new file in the Github repo whenever a user submitted data.

Voila! The YAML data mentioned earlier was sent to Github's API as a base64-encoded string, and a new database entry (and user profile) is born!

## In the Rearview

Of course I realize now that I could have just made the Http request directly from GAS, and circumvented using Zapier altogether.

I still may go back and do this, depending on time constraints, but as of now Zapier is working fine, and I have learned a new service because of it!

In any case, this was (and still is) a great learning experience, and will hopefully be put to use in the community.
