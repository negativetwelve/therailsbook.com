---
layout: chapter
title: Introduction
chapter: Introduction
---
## What is Rails?

Ruby on Rails is a Model-View-Controller (MVC) framework written in Ruby,
a programming language that is similar to Python in terms of syntax.
The Rails aspect of Ruby on Rails is the framework that allows us to
create web applications and APIs.  The framework uses paradigms such as
convention over configuration (CoC) and don't repeat yourself (DRY).

## What is Model-View-Controller (MVC)?
MVC is an architechture for software that consists of three components,
the Model, the View, and the Controller.  It allows an isolation between
what the users interact with and the logic that goes in the background.

### 1. Model
In Rails, models are objects that are used to interact with the data that is stored in the database.  Most of the logic goes into the model.

### 2. View
What the user interacts with.  Consists of the HTML, CSS, and javascript to display the data.

### 3. Controller
The connection between the models and the views.  It usually takes the model's data and populates the views with it.

### 4. MVC Image
![mvc-image](http://railstutorial.org/images/figures/mvc_detailed-full.png)

## What is Convention over Configuration (CoC)?
Ruby on Rails follows the CoC paradigm, which means it will make assumptions about what the user is doing rather than
configuring everything youself.  Rails makes a lot of inferences on what you are trying to do and thus it seems
like Rails works like magic.

## Why Rails?

You can get a webapp up really fast, there is a large community, and it is open source.
A lot of startups use Rails for these reasons.

