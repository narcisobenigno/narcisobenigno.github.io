---
layout: post
title:  "Restful web clients: Enabling Reuse Through Hypermedia"
date:   2019-05-21 13:16:33 +1000
last_update: 2019-05-27 13:12:33 +1000
comments: true
categories: learning
---

## Disclaimer

This is not meant to be a fully comprehensive text and I wont review it either.
Even then, I will try to keep it as understandable as possible for later recall.

## About the book

2017-02-06: First Release. Kindle version of Mike Amundsen

## Unsolved questions:

. There are few things that I could describe in terms of actions, but I would
have to always create a media type or at least a new one which supports those
kind of things.
  . One of those things that comes to my mind is: lets say one menu item has to
  subscribe for a push notification or even pulling some url for retrive some
  info;


## I did not understand, visit later on:

Not yet

## Chapter 1: Our HTML Roots and Simple Web API

## Chapter 2: JSON clients

## Chapter 3: The Representor Pattern

## Chapter 4: HAL Clients

## Chapter 7: Versioning and the WEB

. How to solve the problem of delivery new things which potentially break
things?  Lets study how the internet changed thing thoughout the years

* **TCP/IP** Builtin with robustness principle (Postel's Law):
  - Be concervative what it do and liberal in what it takes
* From webclient perspective that means that outgoing messages must be really
  strict and ingoing, like responses from API, should handle with sensible
  defaults in case something is wrong (like one data is missing).

* **HTTP** clients should still processing even when the server is not strict
  valid: deviant servers.
  * directive **MUST IGNORE**, like if the client does not understand a headers
    that should not break or there is a field inside response payload, i.e.,
    ignores what you don't undestand without halt the process.
  * That folows the **Postel's Law** where the client does not break if
    something not recognized by the client works eventhen.
