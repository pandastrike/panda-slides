# Panda Slides

This is a template for authoring HTML5 slide decks. Based on
[IO 2012 Slides](https://code.google.com/p/io-2012-slides/), but Panda-flavored.

## Getting Started

1. Install [Harp][harp], if you don't already have it:

        npm install -g harp
       
2. Create a new slide deck:

        harp init [name] -b pandastrike/panda-slides
   
   **NOTE**: If `name` is ommited, slides will be created in the current directory.
    
3. Start a server for live preview:

        harp server
        
   Open your browser and go to [http://localhost:9000/slides.html](http://localhost:9000/slides.html)
   
That's it! Now you can open `slides.jade` in your `$EDITOR` and start hacking away.

[harp]: http://harpjs.com

## Configuring the slides

You can customize basic settings in [`slide_config.js`](slide_config.js).
This includes the presentation title, Analytics tracking ID, speaker
information (name, social urls, blog), web fonts to load, themes, and other general behavior.

## Editing CSS

The stylesheet is currently written in [SASS][sass], althought there are plans to port it to [Stylus][styl]. Stylesheets are compiled on-the-fly when using the editing preview, thanks to [Harp][harp]. All you have to is make some changes and reload the page in your browser. Easy peasy.

[sass]: http://sass-lang.com/
[styl]: http://learnboost.github.io/stylus/

## Running the slides

You can run the slides either by using a local server (recommended for development) or by producing a static HTML version (for uploading to your website). 

### Running from a web server

Make sure you have Harp installed (see "Getting Started"), then just navigate to your slides directory and run `harp server`.  Open your browser and go to [http://localhost:9000/slides.html](http://localhost:9000/slides.html). Done!

### Compiling to static HTML

Again, make sure you have Harp installed. Navigate to your slide directory and run `harp compile [outputDir]`. Your compiled slide deck will be found in `outputDir` (or `./www` if you did not specify one).

## Presenter mode

The slides contain a presenter mode feature (beta) to view + control the slides
from a popup window.

To enable presenter mode, add `presentme=true` to the URL: [http://localhost:1337/slides.html?presentme=true](http://localhost:1337/slides.html?presentme=true)

To disable presenter mode, hit [http://localhost:1337/slides.html?presentme=false](http://localhost:1337/slides.html?presentme=false)

Presenter mode is sticky, so refreshing the page will persist your settings.

## Credits

Credits go to the original authors of the Google slide template, [Eric Bidelman](mailto:ebidel@gmail.com)
and [Luke Mahé](mailto:lukem@google.com). Without their work this would not be possible.
