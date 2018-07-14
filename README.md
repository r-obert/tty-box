# TTY::Box [![Gitter](https://badges.gitter.im/Join%20Chat.svg)][gitter]

[![Gem Version](https://badge.fury.io/rb/tty-box.svg)][gem]
[![Build Status](https://secure.travis-ci.org/piotrmurach/tty-box.svg?branch=master)][travis]
[![Build status](https://ci.appveyor.com/api/projects/status/h9b88fk5xpya3fh1?svg=true)][appveyor]
[![Maintainability](https://api.codeclimate.com/v1/badges/dfac05073e1549e9dbb6/maintainability)][codeclimate]
[![Coverage Status](https://coveralls.io/repos/github/piotrmurach/tty-box/badge.svg)][coverage]
[![Inline docs](http://inch-ci.org/github/piotrmurach/tty-box.svg?branch=master)][inchpages]

[gitter]: https://gitter.im/piotrmurach/tty
[gem]: http://badge.fury.io/rb/tty-box
[travis]: http://travis-ci.org/piotrmurach/tty-box
[appveyor]: https://ci.appveyor.com/project/piotrmurach/tty-box
[codeclimate]: https://codeclimate.com/github/piotrmurach/tty-box/maintainability
[coverage]: https://coveralls.io/github/piotrmurach/tty-box
[inchpages]: http://inch-ci.org/github/piotrmurach/tty-box

> Draw various frames and boxes in your terminal interface.

**TTY::Box** provides box drawing component for [TTY](https://github.com/piotrmurach/tty) toolkit.

![Box drawing](https://cdn.rawgit.com/piotrmurach/tty-box/master/assets/tty-box-drawing.png)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'tty-box'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install tty-box

## Contents

* [1. Usage](#1-usage)
* [2. Interface](#2-interface)
  * [2.1 frame](#21-frame)
  * [2.2 position](#22-position)
  * [2.3 dimension](#23-dimension)
  * [2.4 :style](#24-style)

## 1. Usage

Using the `frame` method, you can draw a box in a terminal emulator at a specified location and dimensions:

```ruby
box = TTY::Box.frame(
  top: 2,
  left: 10,
  width: 30,
  height: 10,
  border: :thick,
  align: :center
) do
  "Drawing a box in terminal emulator"
end

print box
```

## 2. Interface

### 2.1 frame

Use block to provide content for the box:

```ruby
box = TTY::Box.frame(width: 30, height: 10) do
  "Drawin a box in terminal emulator"
end
```

### 2.2 position

By default a box will be positioned in the top left corner of the terminal emulator. Use `:top` and `:left` keyword arguments to change this:

```ruby
TTY::Box.frame(top: 5, left: 10)
```

If you wish to center your box then consider using [tty-screen](https://github.com/piotrmurach/tty-screen) for gathering terminal screne size information.

### 2.3 dimension

At the very minimum a box requires two keyword arguments `:width` and `:height`:

```ruby
TTY::Box.frame(width: 30, height: 10)
```

### 2.4 `:style`

By default drawing a box doesn't apply any styling. You can change this using the `:style` keyword with foreground `:fg` and background `:bg` keys for both the main content and the border:

```ruby
style: {
  fg: :bright_yellow,
  bg: :blue,
  border: {
    fg: :bright_yellow,
    bg: :blue
  }
}
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/piotrmurach/tty-box. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the TTY::Box project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/piotrmurach/tty-box/blob/master/CODE_OF_CONDUCT.md).

## Copyright

Copyright (c) 2018 Piotr Murach. See LICENSE for further details.