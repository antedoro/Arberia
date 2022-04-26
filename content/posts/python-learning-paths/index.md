---
weight: 0
title: "Hosting a Django Project on Heroku"
subtitle: "In this step-by-step project, you'll learn about hosting Django projects in the cloud using Heroku, which is the favorite cloud platform provider of many startups and developers."
date: 2021-09-29T20:58:53+02:00
lastmod: 2021-09-29T20:58:53+02:00
draft: false
author: "Bartosz Zaczyński "
authorLink: "https://realpython.com/django-hosting-on-heroku/#author"
description: "Abbiamo selezionato alcuni accesori indispensabili se decidi di acquistare un portabici per automobile"

tags: [django, intermediate, projects]
categories: [web-dev]

hiddenFromHomePage: false
hiddenFromSearch: false

resources:
- name: "featured-image"
  src: "Project-based-How-to-Host-Your-Django-Project-on-Heroku_Watermarked.webp"
- name: "featured-image-preview"
  src: "Project-based-How-to-Host-Your-Django-Project-on-Heroku_Watermarked.webp"

toc:
  enable: true
math:
  enable: false
lightgallery: false
license: ""
---


As a novice web developer, you’ve built your portfolio app and shared your code on GitHub. Perhaps, you’re hoping to attract technical recruiters to land your first programming job. Many coding bootcamp graduates are likely doing the same thing. To differentiate yourself from the crowd and boost your chances of getting noticed, you can start hosting your Django project online.

For a hobby Django project, you’ll want a hosting service that’s free of charge, quick to set up, user-friendly, and well-integrated with your existing technology stack. While GitHub Pages is perfect for hosting static websites and websites with JavaScript, you’ll need a web server to run your Flask or Django project.

There are a few major cloud platform providers operating in different models, but you’re going to explore Heroku in this tutorial. It ticks all the boxes—it’s free, quick to set up, user-friendly, and well-integrated with Django—and is the favorite cloud platform provider of many startups.

In this tutorial, you’ll learn how to:

    Take your Django project online in minutes
    Deploy your project to Heroku using Git
    Use a Django-Heroku integration library
    Hook your Django project up to a standalone relational database
    Manage the configuration along with sensitive data

To follow along, you can download the code and other resources by clicking the link below:

Get Source Code: Click here to get the companion Django project as well as snapshots of the individual steps followed in this tutorial.
Demo: What You’ll Build

You’re going to create a bare-bones Django project and deploy it to the cloud straight from the terminal. By the end, you’ll have a public and shareable link to your first Heroku app.

Here’s a one-minute video demonstrating the necessary steps, from initializing an empty Git repository to viewing your finished project in the browser. Hang on and watch till the end for a quick preview of what you’re about to find in this tutorial:

In addition to the steps shown in the screencast above, you’ll find a few more later on, but this should be enough to give you a general idea about how you’ll be working with Heroku in this tutorial.
Remove ads
Project Overview

This tutorial isn’t so much about building any particular project, but rather hosting one in the cloud using Heroku. While Heroku supports various languages and web frameworks, you’ll stick to Python and Django. Don’t worry if you don’t have any Django projects on hand. The first step will walk you through scaffolding a new Django project to get you started quickly. Alternatively, you can use a ready-made sample project that you’ll find later.

Once you have your Django project ready, you’re going to sign up for a free Heroku account. Next, you’ll download a convenient command-line tool that will help you manage your apps online. As demonstrated in the screencast above, the command line is a quick way of working with Heroku. Finally, you’ll finish off with a deployed Django project hosted on your newly-configured Heroku instance. You can think of your final result as a placeholder for your future project ideas.
Prerequisites

Before jumping ahead, make sure that you’re familiar with the basics of the Django web framework and that you’re comfortable using it to set up a bare-bones project.

Note: If you’re more experienced with Flask than Django, then you can check out a similar tutorial about Deploying a Python Flask Example Application Using Heroku.

You should also have a Git client installed and configured so that you can interact conveniently with the Heroku platform from the command line. Finally, you should seriously consider using a virtual environment for your project. If you don’t already have a specific virtual environment tool in mind, you’ll find some options in this tutorial soon.
Step 1: Scaffold a Django Project for Hosting

To host a Django web application in the cloud, you need a working Django project. For the purposes of this tutorial, it doesn’t have to be elaborate. Feel free to use one of your hobby projects or to build a sample portfolio app if you’re short on time, and then skip ahead to creating your local Git repository. Otherwise, stick around to make a brand new project from scratch.
Create a Virtual Environment

It’s a good habit to start every project by creating an isolated virtual environment that won’t be shared with other projects. This can keep your dependencies organized and help avoid package version conflicts. Some dependency managers and packaging tools like Pipenv or poetry automatically create and manage virtual environments for you to follow best practices. Many IDEs like PyCharm do this by default, too, when you’re starting a new project.

However, the most reliable and portable way of creating a Python virtual environment is to do it manually from the command line. You can use an external tool such as virtualenvwrapper or call the built-in venv module directly. While virtualenvwrapper keeps all environments in a predefined parent folder, venv expects you to specify a folder for every environment separately.

You’ll be using the standard venv module in this tutorial. It’s customary to place the virtual environment in the project root folder, so let’s make one first and change the working directory to it:

$ mkdir portfolio-project
$ cd portfolio-project/

You’re now in the portfolio-project folder, which will be the home for your project. To create a virtual environment here, just run the venv module and provide a path for your new environment. By default, the folder name will become the environment’s name. If you want to, you can instead give it a custom name with the optional --prompt argument:

$ python3 -m venv ./venv --prompt portfolio

A path starting with a leading dot (.) indicates that it’s relative to the current working directory. While not mandatory, this dot clearly shows your intent. Either way, this command should create a venv subdirectory in your portfolio-project root directory:

portfolio-project/
│
└── venv/

This new subdirectory contains a copy of the Python interpreter along with a few management scripts. You’re now ready to install project dependencies into it.
Install Project Dependencies

Most real-life projects depend on external libraries. Django is a third-party web framework and doesn’t ship with Python out-of-the-box. You must install it along with its own dependencies in your project’s virtual environment.

Don’t forget to activate your virtual environment if you haven’t already. To do so, you’ll need to execute the commands in one of the shell scripts available in the virtual environment’s bin/ subfolder. For example, if you’re using Bash, then source the activate script:

$ source venv/bin/activate

The shell prompt should now display a prefix with your virtual environment’s name to indicate it’s activated. You can double-check which executables the specific commands are pointing to:

(portfolio) $ which python
/home/jdoe/portfolio-project/venv/bin/python

The above output confirms that running python will execute the corresponding file located in your virtual environment. Now, let’s install the dependencies for your Django project.

You’ll need a fairly recent version of Django. Depending on when you’re reading this, there might be a newer version available. To avoid potential compatibility problems, you may want to specify the same version as the one used at the time of writing this tutorial:

(portfolio) $ python -m pip install django==3.2.5

This will install the 3.2.5 release of Django. Package names are case insensitive, so it doesn’t matter whether you type django or Django, for example.

Note: Sometimes, you’ll see a warning about a newer version of pip being available. It’s usually harmless to ignore this warning, but you’ll need to consider upgrading for security reasons if you’re in a production environment:

(portfolio) $ python -m pip install --upgrade pip

Alternatively, you can disable the version check in the configuration file if it’s bothering you and you’re aware of the possible consequences.

Installing Django brings a few additional transitive dependencies, which you can reveal by listing them: