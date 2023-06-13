---
title: "How to inspect extension `chrome.storage` in Chrome DevTools"
date: 2023-06-11
tags: [git]
type: note
url: "/html/2023-06-13-chrome-extension-inspect-storage.html"
---

The extension storage is not displayed under "Application" tab in Chrome DevTools, but
it is possible to access the extension storage using javascript console, here is how:

How to inspect extension `chrome.storage` in Chrome DevTools

it is possible to access it via javascript console:

* Open some web page, open Chrome DevTools
* In the javascript console, select the extension context (the drop down with "top" in it)
* Use `chrome.storage.local` to access the localstorage

The `chrome.storage.local` is a [StorageArea](https://developer.chrome.com/docs/extensions/reference/storage/#type-StorageArea) 
object and it has methods to get and set values.

We can also print the entire storage by passing `null` to `get` method
with `chrome.storage.local.get(null).then((data) => console.log(data))`.

<!-- more -->

![extension storage access](/2023-06-13-chrome-extnension-storage.png)

The demo:

![extension storage demo](/2023-06-13-chrome-extension-storage.mp4)
