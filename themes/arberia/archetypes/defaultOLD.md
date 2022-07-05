---
title: "{{ replace .Name "-" " " | title }}"
subtitle: "Insert a subtitle here"
date: {{ .Date }}
lastmod: {{ .Date }}
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

