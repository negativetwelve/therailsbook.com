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
In Rails, models are objects that are used to interact with the data that is
stored in the database.  Most of the logic goes into the model.

### 2. View
What the user interacts with.  Consists of the HTML, CSS, and javascript to
display the data.

### 3. Controller
The connection between the models and the views.  It usually takes the model's
data and populates the views with it.

### 4. MVC Image
![mvc-image]({{site.url}}/assets/mvc_detailed.png)

## What is Convention over Configuration (CoC)?
Ruby on Rails follows the CoC paradigm, which means it will make assumptions
about what the user is doing rather than configuring everything youself.
Rails makes a lot of inferences on what you are trying to do and thus it seems
like Rails works like magic.

## Why Rails?

You can get a webapp up really fast, there is a large community, and it is open
source. A lot of startups use Rails for these reasons.

### About this Book

In this book we are going to use Git for version control, Ruby version 2.2.0 and
Rails 4.1.5.

## Mac and Linux Installation

### Before

If you have Linux run in your console

{% highlight console %}

sudo apt-get update

{% endhighlight %}

If you have OSX run in your console

{% highlight console %}

brew update

{% endhighlight %}

### Installing Git

If you have Linux run in your console

{% highlight console %}

sudo apt-get install git

{% endhighlight %}

If you have OSX run in your console

{% highlight console %}

brew install git

{% endhighlight %}

### Install RVM

If you have Linux run in your console

{% highlight console %}

sudo apt-get install libyaml-dev

{% endhighlight %}

If you have OSX run in your console

{% highlight console %}

brew install libtool libxslt libksba openssl libyaml

{% endhighlight %}

Next, for both Linux and OSX run

{% highlight console %}

\curl -sSL https://get.rvm.io | bash -s stable --ruby=2.2.0

{% endhighlight %}

to get RVM in order to manage your ruby versions.

Now you should be able to run without error

{% highlight console %}

ruby -v # Print Ruby version.  It should be 2.2.0
which rbuy #Should have /.rvm/ somewhere in the path

{% endhighlight %}

### Install Rails

Run in your console

{% highlight console %}

gem install rails -v 4.1.5
rails -v # Should show Rails 4.1.5

{% endhighlight %}

### Create a Rails App

After installing you can now create a Rails App by typing in your console

{% highlight console %}

rails new the-rails-book
cd the-rails-book
bundle install
rails server

{% endhighlight %}

and when you visit [http://localhost:3000]("http:/localhost:3000") you should
see this

![welcome-image]({{site.url}}/assets/rails_welcome.png)

## Windows Installation

For Windows we are going to go over how to install Rails through a virtual
machine because Windows just isn't as well supported as linux and OSX for rails.

First download and install
[VirtualBox]("https://www.virtualbox.org/wiki/Downloads") and
[Vagrant]("https://www.vagrantup.com/downloads.html").  Then install
[Git]("http://git-scm.com/book/en/v2/Getting-Started-Installing-Git").

### Setting up Vagrant

To setup your VM run the following commands in your console

{% highlight console %}

git clone https://github.com/rails-decal/rails-dev-box
cd rails-dev-box
vagrant up

vagrant ssh

vagrant@rails-dev-box:~$ cd /vagrant/
vagrant@rails-dev-box:/vagrant$ gem install rails -v 4.1.5
vagrant@rails-dev-box:/vagrant$ rails new week-1-lecture
vagrant@rails-dev-box:/vagrant$ cd week-1-lecture
vagrant@rails-dev-box:/vagrant$ bundle install
vagrant@rails-dev-box:/vagrant$ rails server

{% endhighlight %}

Visit [http://localhost:3000] to see your app! It should look like
![welcome-image]({{site.url}}/assets/rails_welcome.png)
