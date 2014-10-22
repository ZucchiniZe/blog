---
layout: post
title: Working with express
status: draft
tags:
- express
---

# Using express
Express is a fickle beast, its middleware sometimes doesn't work or jade doesn't work sometimes but all together it an
awesome framework for nodejs.

## Using middleware

Since express 4.0 a lot of the middleware is not located under the main express object, here is a list of the changes:

* `express.bodyParser()` -> `bodyParser()`
* `express.favicon()` -> `serve-favicon()`
* `express.logger()` -> `morgan()`
and so on

(This is not the complete list [here is the complete list](https://github.com/senchalabs/connect#middleware))

## Routers

I love routers and how they work.

You can create them by creating a variable `var router = express.Router()` and you then assign it to a url prefix by
`app.use('/route', router)`.

So if `router` had some routes assigned to it like
{% highlight js linenos %}
router.get('/url', function(req, res, next) {
  res.send(req.url);
}
{% endhighlight %}
`/route/url` would return /route/url.

That is how I seperated my api from my application and other misc views.

Have a look at the app I am creating [borderly](http://github.com/borderly/borders) it is created entirely by scratch
and uses jade + express + mongoose for the api router.)`
