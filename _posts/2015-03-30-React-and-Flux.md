---
layout: post
title: 'React and Flux (alt)'
---

![React Logo](https://i.imgur.com/xKBOIT5.png)

I have recently learned how to use [React](https://facebook.github.io/react) and [flux (alt)][alt] to make some applications such as [a realtime  chat](https://github.com/ZucchiniZe/react-chat) and [flux people](https://github.com/ZucchiniZe/flux-people).

Even though I say this for most frameworks that I start to learn and use; React is one of the best libraries on the web.

# React

First of all lets talk about react and how awesome it is and how it works.

In my opinion, the reason why so many people love using react is how fast it is. The reason it is so fast is its **Virtual DOM** and **component architecture**.

## The Virtual DOM

The way that react uses the Virtual DOM is that once you make a change to the state of the component it diffs (compares it) the Virtual DOM against the real DOM and determines what has changed and only replaces/adds that to the real DOM which makes it incredibly fast to update.

## Component architecture

Personally I believe the best and easiest way to organize applications is using a component style architecture alongside with **flux** (Which we will be talking about later on).

The reason I believe that this is the best way to organize applications is because of how easy it is to duplicate things and just pick it up and work on it without getting briefed on what goes where and how everything works.

# Flux (alt)

Since flux is just an idea and not a bunch of code there are many different implementations. The implementation of my choice is [alt][alt].

Secondly lets talk about flux and how it's many benefits can be useful to many projects nowadays.

Here is a basic diagram of how flux works.

```
┌───────────┐   ┌──────────┐   ┌─────────┐
│  Actions  │==>│  Stores  │==>│  Views  │
└───────────┘   └──────────┘   │ (react) │
      ▲                        └─────────┘
      └─────────────────────────────┘
```

## Actions

Actions are the thing that trigger the whole chain to update. They also can do preliminary data transformation.

Since with [alt][alt] you can only pass one parameter to the store with any action you could either manipulate the data so it goes into an object or you could even put it in an array so the store could easily access it.

Another reason you would have custom actions is that you could have a custom alerter or have some analytics event fire when the action gets triggered and before the store does the data processing.

## Stores

Stores are the meat of an application. They are where most things get sent off to the database.

For example you could have your client side database library send an array of things that have amassed over time in the store.

## Views

Views are pretty self explanatory, they are the thing that the user sees that usually are listening to the store for changes in the data and re-render the entire component using react's virtual DOM.

[alt]: https://github.com/goatslacker/alt