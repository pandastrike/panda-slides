# Panda Slides

This is a simple tool for writing slides using HTML5, based on Google's
[IO 2012 Slides](https://code.google.com/p/io-2012-slides/).

## Configuring the slides

Much of the deck is customized by changing the settings in [`slide_config.js`](slide_config.js).
Some of the customizations include the title, Analytics tracking ID, speaker
information (name, social urls, blog), web fonts to load, themes, and other
general behavior.

## Editing CSS

Panda Slides uses [SASS][1] for its stylesheets. Styles are found in the `styles` directory and can
be edited directly. Thanks to `harp` we don't need to mess with intermediate CSS files anymore.

[1]: http://sass-lang.com/

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

## Credits

Credits go to the original authors, [Eric Bidelman](mailto:ebidel@gmail.com)
and [Luke Mahé](mailto:lukem@google.com). Without their work this would not be possible.
