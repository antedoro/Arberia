---
title: Esempio1
subtitle: Insert a subtitle here
date: 2022-05-10T23:07:28+02:00
lastmod: 2022-05-10T23:07:28+02:00
draft: true
weight: null
type: null

author: author
authorLink: ""
description: Descrizione da rivedere se è un doppione subtitle

tags:
  - tag1
  - tag2
  - tag3
  - tag4
categories:
  - category

hiddenFromHomePage: false
hiddenFromSearch: false

resources:
  - name: featured-image
    src: featured-image.png

featured: false
sidebar: true
toc: false
math:
  enable: false
lightgallery: false
license: ""
slug: esempio1
---

The following is a code sample using the "highlight" shortcode provided in Hugo. This is server side highlighting and requires Python and Pygments to be installed.

{{< highlight javascript >}}
    var num1, num2, sum
    num1 = prompt("Enter first number")
    num2 = prompt("Enter second number")
    sum = parseInt(num1) + parseInt(num2) // "+" means "add"
    alert("Sum = " + sum)  // "+" means combine into a string
{{</ highlight >}}