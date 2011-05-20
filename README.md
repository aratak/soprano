# Capone

Capone is the set of Capistrano recipes that help me to deploy my
applications.

Capone by default uses Mongrel cluster (or Passenger) as an application
server, nginx as a web server, MySQL as a database server and git as a SCM.

The latest version of Capone was inspired by Rubaidh's
[Rubaidhstrano](http://github.com/rubaidh/rubaidhstrano) and some code has
been borrowed from its sources.

## Installation

Capone could be installed either as a gem or as Rails plugin.

### Gem (preferred)

Add to the end of your `config/environments/development.rb` file:

    config.gem 'capone', :lib => false, :version => '>= 0.1.0'

### Rails plugin

    ./script/plugin install git://github.com/denis/capone.git

## Example usage

To start using Capone you just need to add `require "capone"` to your
`config/deploy.rb` file (only if Capone is installed as a gem) and set some
variables:

    require "capone"

    set :application, "set your application name here"
    set :repository,  "set your repository location here"
    set :host,        "set your host here"

    # See capone/recipes/defaults.rb for defaults

## Features

### Whenever

Using [whenever](https://github.com/javan/whenever) is as easy as `set`ing `:whenever` to `true`. Just like this:

    set :whenever, true

Whenever will use your application deploy path as crontab identifier.

You may wish to override the command, used to invoke whenever, e.g., to use Bundler:

    set :whenever_command, 'bundle exec whenever'

Other features in process...

## Thanks

- Jamis Buck for [Capistrano](http://github.com/jamis/capistrano),
- Rubaidh Ltd for their awesome
  [Rubaidhstrano](http://github.com/rubaidh/rubaidhstrano).

## Copyright

Copyright (c) 2009 Denis Barushev. See LICENSE for details.
