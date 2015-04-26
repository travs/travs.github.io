---
layout: post
title: "Add a File to Github with Zapier"
date: "2015-04-25 15:01"
---

##Background

Recently I have built an information-sharing platform called [TReND-links](http://travs.github.io/TReND-links).

It was designed to allow users (scientists) to insert contact information, allowing other scientists to contact them.

Read about the design [here](/2015/04/20/implement-contact-sharing-service/).

##Using Zapier

Part of the design was to automatically add files to Github, which I thought I could do with Zapier.

Unfortunately, there was no option under **"DO THIS"** to add a file to Github.

<img src="/assets/images/zapier_github.png" width="50%" style="margin-left:auto;margin-right:auto;" />

Instead, I had to use Github's API and Zapier's "Webhook" output.

##How To Do It

All we have to do now is make an Http PUT request to Github's API.

If you don't know what this means (as I didn't) then just follow the steps below!

-  Select [Webhook](https://zapier.com/zapbook/webhook/) **PUT** as the output of your "Zap".

<img src="/assets/images/zapier_webhook.png" width="80%" style="margin-left:auto;margin-right:auto;" />

- Set up your triggers according to the input of your Zap (mine was Google Sheets, but it could be any of the others that are supported).

- Here's the important part. We will be interfacing with Github's Repository API to [create a file](https://developer.github.com/v3/repos/contents/#create-a-file) inside an existing repo.
 1. For the **URL** field, use `https://api.github.com/repos/:owner/:repo/contents/:path`, where `:value` means *your* repo/username/whatever.
 2. Under **Data**, use these key-value pairs:
  - content:  (*Add your content here, encoded as [Base64](https://en.wikipedia.org/wiki/Base64)*)
  - path: /(*your desired filename*)
  - message: (*Your commit message for the new file being committed*)
  - branch: (*the branch you want to add to*)
  - Here's what my data looked like: <img src="/assets/images/zapier_data.png" width="100%" />


- Finally, [create a new Access Token on Github](https://help.github.com/articles/creating-an-access-token-for-command-line-use/).
  - Add this to the **Basic Auth** field of your Zap, formatted as `KEY|x-oauth-basic`

Now you're done!

This Zap will listen for an event you define (Google Sheet row addition in my case), and then create a Github file automatically!
