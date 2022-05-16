---
title: "Esempio1"
subtitle: "Insert a subtitle here"
date: 2022-05-10T23:07:28+02:00
lastmod: 2022-05-10T23:07:28+02:00
coverimage: "featured-image.png"
draft: true
weight: 

author: "author"
authorLink: ""
description: "Descrizione da rivedere se è un doppione subtitle"

tags: [tag1, tag2, tag3, tag4]
categories: [category]

hiddenFromHomePage: false
hiddenFromSearch: false

resources:
- name: "featured-image"
  src: "Real-Python-Learning-Paths_Watermarked.webp"
- name: "featured-image-preview"
  src: "Real-Python-Learning-Paths_Watermarked.webp"

type:  # Nothing for default, or video 
featured: false
sidebar: true
toc: true 
math:
  enable: false
lightgallery: false
license: ""
---

The following is a code sample using the "highlight" shortcode provided in Hugo. This is server side highlighting and requires Python and Pygments to be installed.

{{< highlight javascript >}}
    var num1, num2, sum
    num1 = prompt("Enter first number")
    num2 = prompt("Enter second number")
    sum = parseInt(num1) + parseInt(num2) // "+" means "add"
    alert("Sum = " + sum)  // "+" means combine into a string
{{</ highlight >}}