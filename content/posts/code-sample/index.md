---
title: "Code Sample"
subtitle: "Insert a subtitle here"
date: 2022-04-26T18:28:32+02:00
lastmod: 2022-04-26T18:28:32+02:00
coverimage: "featured-image.png"
draft: true
author: "author"
authorLink: ""
description: "Descrizione da rivedere se è un doppione subtitle"
weight: 

tags: [tag1, tag2, tag3, tag4]
categories: [category]

hiddenFromHomePage: false
hiddenFromSearch: false

resources:
- name: "featured-image"
  src: "Real-Python-Learning-Paths_Watermarked.webp"
- name: "featured-image-preview"
  src: "Real-Python-Learning-Paths_Watermarked.webp"

featured: false
sidebar: true
toc: true 
math:
  enable: false
lightgallery: false
license: ""
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
