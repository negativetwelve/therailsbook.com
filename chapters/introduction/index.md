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
the Model, the View, and the Controller.

Model: Our interface with our data.  It contains and changes its state.
Think about this like objects.

View:  The part the user sees and interacts with.  Think about this as the
HTML that is being rendered.

Controller:  Takes in commands and interacts with the model to update
the view.

## Solution

Export the functionality in the following manner:

{% highlight coffeescript %}

# simpleMath.coffee

# these methods are private
add = (a, b) ->
  a + b

subtract = (a, b) ->
  a - b

square = (x) ->
  x * x

# create a namespace to export our public methods
SimpleMath = exports? and exports or @SimpleMath = {}

# items attached to our namespace are available in Node.js as well as client browsers
class SimpleMath.Calculator
  add: add
  subtract: subtract
  square: square

{% endhighlight %}

## Discussion

In the above example, we create a new namespace called SimpleMath.  If `export` is available, our class is exported as a Node.js module.  If `export` is *not* available, then SimpleMath is added to the global namespace and available to our web page.

In Node.js, we can include our module using the `require` command.

{% highlight console %}

$ node

> var SimpleMath = require('./simpleMath');
undefined
> var Calc = new SimpleMath.Calculator();
undefined
> console.log("5 + 6 = ", Calc.add(5, 6));
5 + 6 =  11
undefined
> 

{% endhighlight %}

In our web page, we can include our module using by including it as a script.

{% highlight html %}

<!DOCTYPE HTML>
<html lang="en-US">
<head>
  <meta charset="UTF-8">
  <title>SimpleMath Module Example</title>
  <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
  <script src="simpleMath.js"></script>
  <script>
    jQuery(document).ready(function (){
      var Calculator = new SimpleMath.Calculator();
      var result = $('<li>').html("5 + 6 = " + Calculator.add(5, 6));
      $('#SampleResults').append(result); 
    });
  </script>
</head>
<body>
  <h1>A SimpleMath Example</h1>
  <ul id="SampleResults"></ul>
</body>
</html>

{% endhighlight %}

Result:

#A SimpleMath Example
* 5 + 6 = 11