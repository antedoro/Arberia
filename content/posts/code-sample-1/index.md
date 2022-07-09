---
title: Code Sample 1
subtitle: Insert a subtitle here
date: 2022-06-24T18:28:32+02:00
lastmod: 2022-06-24T18:28:32+02:00
draft: true
author: author
authorLink: ""
description: Descrizione da rivedere se è un doppione subtitle
weight: null

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
slug: code-sample
---

The following are two code samples using syntax highlighting.

<!--more-->

The following is a code sample using triple backticks ( ``` ) code fencing provided in Hugo. This is client side highlighting and does not require any special installation.

```javascript
    var num1, num2, sum
    num1 = prompt("Enter first number")
    num2 = prompt("Enter second number")
    sum = parseInt(num1) + parseInt(num2) // "+" means "add"
    alert("Sum = " + sum)  // "+" means combine into a string
```

The following is a code sample using the "highlight" shortcode provided in Hugo. This is server side highlighting and requires Python and Pygments to be installed.

{{< highlight javascript >}}
    var num1, num2, sum
    num1 = prompt("Enter first number")
    num2 = prompt("Enter second number")
    sum = parseInt(num1) + parseInt(num2) // "+" means "add"
    alert("Sum = " + sum)  // "+" means combine into a string
{{</ highlight >}}

And here is the same code with line numbers:

{{< highlight javascript "linenos=inline">}}
    var num1, num2, sum
    num1 = prompt("Enter first number")
    num2 = prompt("Enter second number")
    sum = parseInt(num1) + parseInt(num2) // "+" means "add"
    alert("Sum = " + sum)  // "+" means combine into a string
{{</ highlight >}}