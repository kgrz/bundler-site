---
title: Using Bundler with Sinatra
---

## Using Bundler with Sinatra

To use bundler with a Sinatra application, you only need to do two things.
First, create a `Gemfile` and declare the `sinatra` gem as a dependency.

~~~ ruby
gem 'sinatra'
~~~

Then, set up your `config.ru` file to load the bundle before it loads your Sinatra app.

~~~ ruby
require 'rubygems'
require 'bundler'

Bundler.require

require './my_sinatra_app'
run MySinatraApp
~~~

Start your development server with rackup, and Sinatra will be loaded via Bundler.

~~~
$ bundle exec rackup
~~~