# Rails Behaviors

Rails Behaviors implements the `data-*` behaviors generated by Rails 3.x.

This is an alternative to [jquery-ujs](https://github.com/rails/jquery-ujs). Firstly, it is all Coffee goodness. Well, thats mostly good for me. Second, it is written in a modular fashion. This makes it possible to cherry pick the components you need and replace specific functionaly without rewriting the whole thing. Third, it uses built in global ajax events rather than adding its own. O, one more thing, **Zepto**.


## Dependencies

**jQuery 1.7.2+** or **Zepto 0.8+**

You'll need [Sprockets 2](github.com/sstephenson/sprockets/) if you want to use the gem version. Otherwise you can download the standalone file from the [Downloads](https://github.com/sstephenson/sprockets/downloads) section.


## Installation

Theres a couple ways to get setup.

If you're using Rails 3.1, the best way is to use the gem. Add `gem 'rails-behaviors'` to your `Gemfile` and add `//= require rails` to your `application.js`.

Other versions of Rails or even Sinatra can still use the gem as long as you're using [Sprockets](https://github.com/sstephenson/sprockets/). Add `rails-behaviors` to your `Gemfile`. Depending on your setup, add `Rails::Behaviors.path` to your Sprockets environment.

``` ruby
env = Sprockets::Environment.new
env.append_path Rails::Behaviors.path
```

An alternative option is just to download the compiled single JS file under [Downloads](https://github.com/josh/rails-behaviors/downloads). This will be compatable with any generic JS setup. So if you're using something else, like [Jammit](http://documentcloud.github.com/jammit/), this way is your best bet.


## Migrating from jquery-ujs

This library handles all the `data-*` behaviors defined in Rails. So its roughly feature for feature identicial with respect to the HTML.

The differences are in the JS interface.

1. There are no `ajax:*` events. jQuery already has global ajax events built in, so there is no point in duplicating that functionality. Doing a find and replace for `"ajax:"` events should give you a good start. You're looking to replace `ajax:success` with `ajaxSuccess`, `ajax:error` with `ajaxError`, etc.
2. There are no global configuration options. Theres no equivalent for `$.rails`. Your probably should have never used that in the first place.

**NOTE** You **can not** use rails-behaviors and jquery-ujs at the same time.


## Reference

See [http://josh.github.com/rails-behaviors/](http://josh.github.com/rails-behaviors/) for a markup and event reference.

## Contributing

    $ git clone git://github.com/josh/rails-behaviors.git
    $ cd rails-behaviors/
    $ bundle install

Run tests

    $ bundle exec rake test

## License

Copyright &copy; 2011 Joshua Peek <<josh@joshpeek.com>>

Rails Behaviors is distributed under an MIT-style license. See LICENSE for details.
