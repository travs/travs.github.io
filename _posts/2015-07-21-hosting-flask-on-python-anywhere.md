---
layout: post
title: A Quick Tip on Hosting a Flask App at PythonAnywhere
---

-----

The [Flask app I've been working on lately](https://github.com/travs/TReND-links) has been coming along nicely!
It was time to deploy to the cloud, so I could test my changes somewhere other than my local development environment.

After some difficulty deploying to PythonAnywhere, and looking at the debug logs, I realized that my configs must be off.
I keep them in an external file called `configs.py`, which looks something like this:

```py
class Config(object):
    DEBUG = True
    TESTING = False
    CSRF_ENABLED = True
    SECRET_KEY = 'shhhh'
    HOST = '0.0.0.0'
    PORT = 5000
    DATABASE = SqliteDatabase(None)
```

There was nothing in the debug or server logs about this, so it took a few tries, but after commenting out the `HOST` and `PORT` keys my app worked as described in the PythonAnywhere docs.

So just a quick tip from a lesson learned the (kinda) hard way. For your configs, use something more like this, than the above:

```py
class Config(object):
    DEBUG = False
    TESTING = False
    CSRF_ENABLED = True
    SECRET_KEY = 'wanna-go-for-an-override?'
    DATABASE = SqliteDatabase(None)
```
