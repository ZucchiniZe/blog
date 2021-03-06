---
layout: post
title: "Ruby, just starting"
---

![Ruby Logo](https://d13yacurqjgara.cloudfront.net/users/26222/screenshots/1395942/ruby2.gif)

Let me start this with, ruby is awesome and always will be.

I recently have started learning and screwing around with ruby and the web frameworks it provides, namely sinatra.

### Sinatra

Once I saw some sinatra code, I fell in love. The easiness to grasp the code is so nice and how simple the ruby [DSL](https://en.wikipedia.org/wiki/Domain-specific_language) is.

I have started to write tiny little services that are made in ruby using sinatra, most notably [my](https://github.com/smtcs/cdn) [CDN](http://cdn.smtcs.rocks) which I went all out for, even wrote some [tests](http://cdn.smtcs.rocks/test).

#### Organization

Once you start writing medium sized sinatra applications, you usually want to split up the routes into separate files, which is sort of a problem.

The way I have done it is creating a `routes` directory with a basic template of

{% highlight ruby %}
module Module
  module RouteGroup
    def self.included(app)
      app.get '/route' do
        "Hello World!"
      end
    end
  end
end
{% endhighlight %}

and in the main file, which I usually name `app.rb`

{% highlight ruby %}
require_relative 'routes/route'

module Module
  module Main
    include CDN::RouteGroup
  end
end
{% endhighlight %}

I’m sure there are better ways to accomplish what I have done but mine works (well) so I will stick with it.

#### Templating

I don’t really have a personal preference when it comes to templating libraries, I like erb and I like [HAML](http://haml.info) and I can use both, it just doesn’t really matter. I like haml slightly better than erb mainly because of how you don’t have to close the tags you open but then the one big drawback is having to use the %’s to declare the beginning of the tags.

### CDN

As I mentioned before I am working on a CDN (Content Delivery Network) for my schools elective program called expeditions which I will tell you about it a bit.

I have written over 100 tests for my cdn that are very simple tests using [capybara](https://github.com/jnicklas/capybara) to visit the page and ask if the status code is a 200.

Quite simply the CDN is just a resource for the other students to use so they all are using the same version of the library so there aren’t any breaking API changes. This ensures easy debugging.

There are a few libraries that I am serving. Here is the list of them.

- Skeleton
- Bootstrap
- Materialize
- Simple.css
- jQuery
- Highlight.js
- Polymer
- Photoswipe
- Font Awesome

### Rake

I personally think `rake` is one of, if not the best ruby tool there is.

I say this because it is so easy to write tasks for, and it can do pretty much anything you want, heck you could probably write a webserver using rake.

The point is, you can orchestrate rake to do anything you want which enables you to write custom tasks that do cool things.

#### Rspec

Rspec is also one of the great ruby tools, it is the best (with bias) testing framework for ruby that I have found so far.

The great thing about `rspec` is its simplicity which is from, what I have seen, unparalleled. Here is a simple test using rspec:
{% highlight ruby %}
describe 'Addition' do
  it '1 + 1 should equal 2' do
    1 + 1 == 2
  end
end
{% endhighlight %}

The test test above would pass since `1 + 1 = 2` is true.
