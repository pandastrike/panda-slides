# Panda Slides

This is a simple tool for writing slides using HTML5, based on Google's
[IO 2012 Slides](https://code.google.com/p/io-2012-slides/).

## Configuring the slides

Much of the deck is customized by changing the settings in [`slide_config.js`](slide_config.js).
Some of the customizations include the title, Analytics tracking ID, speaker
information (name, social urls, blog), web fonts to load, themes, and other
general behavior.

## Editing CSS

[Compass](http://compass-style.org/install/) is a CSS preprocessor used to compile
SCSS/SASS into CSS. The original slide deck uses this, and even though I sunk several
hours into this, I was unable to get rid of it, or replaces it with an NPM module.

The problem is that compass isn't JUST a preprocessor, it also ships with a large
library of mixins, of which the stylesheet makes liberal use. Even though they are
available [in the form of a node module][cm], I was unable getting them to compile using
[node-sass][ns]. This is something I'm hoping to fix in the future.

That said, if you are not comfortable working with SCSS or don't want to learn something
new, not a problem. The generated .css files can already be found in
(see [`/theme/css`](theme/css)). You can just edit those and bypass SCSS altogether.
However, our recommendation is to use Compass. It's super easy to install and use.

[cm]: https://github.com/Igosuki/compass-mixins
[ns]: https://github.com/sass/node-sass

### Installing Compass and making changes

First, install compass:

    sudo gem update --system
    sudo gem install compass

Next, you'll want to watch for changes to the exiting .scss files in [`/theme/scss`](theme/scss)
and any new one you add:

    $ cd panda-slides
    $ compass watch

This command automatically recompiles the .scss file when you make a change.
Its corresponding .css file is output to [`/theme/css`](theme/css). Slick.

By default, [`config.rb`](config.rb) in the main project folder outputs minified
.css. It's a best practice after all! However, if you want unminified files,
run watch with the style output flag:

    compass watch -s expanded

*Note:* You should not need to edit [`_base.scss`](theme/scss/_base.scss).

## Running the slides

The slides can be run locally from `file://` making development easy :)

### Running from a web server

If at some point you should need a web server, use [`bin/serve.sh`](bin/serve.sh). It will
launch a simple one and point your default browser to [`http://localhost:1337/slides.html`](http://localhost:1337/slides.html):

    $ cd panda-slides
    $ ./bin/serve.sh

You can also specify a custom port:

    $ ./bin/serve.sh 8080

### Presenter mode

The slides contain a presenter mode feature (beta) to view + control the slides
from a popup window.

To enable presenter mode, add `presentme=true` to the URL: [http://localhost:1337/slides.html?presentme=true](http://localhost:1337/slides.html?presentme=true)

To disable presenter mode, hit [http://localhost:1337/slides.html?presentme=false](http://localhost:1337/slides.html?presentme=false)

Presenter mode is sticky, so refreshing the page will persist your settings.

## Known issues

Currently requires `compass` to build the stylesheets when modifications are done to the SCSS files.
Compass requires a working Ruby installation (which *should* be no issue on a Mac, unless – well,
unless you have been doing a lot of Ruby development, in which case `rvm` has probably messed it up
by now). Try as I might, I could not find a way around this, so that's how it is for now. 

## Credits

Credits go to the original authors, [Eric Bidelman](mailto:ebidel@gmail.com)
and [Luke Mahé](mailto:lukem@google.com). Without their work this would not be possible.
