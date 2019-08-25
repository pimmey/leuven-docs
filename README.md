# Leuven theme documentation

## Introduction
This theme is built using [Materialize](http://materializecss.com/), a modern responsive front-end framework based on Material Design. Make sure you visit their web-site to learn more about it. Feel free to use all of the elements that framework provides.

## File structure
```
├── css/
├── fonts/
├── images/
├── js/
├── index.html
├── docs.pdf
```

### `css`
Where your styles are located, including libraries like Materielize and Linea fonts stylesheet & of course the theme custom stylesheet.

### `fonts`
Contains font files, Linea icons in particular.

### `images`
All images are located under this directory. You can also find various favicons located under `images/icons` directory.

### `js`
Various JavaScript files are found here, 3rd party and local theme scripts.

### `index.html`
The main HTML file that gathers everything together to produce the masterpiece of a theme :-)

## Code structure
The theme is using the following structure:
```html
<!DOCTYPE html>
<html>
  <head>
    <!-- meta information, stylesheets, icons, title -->
  </head>
  <body>
    <!-- priority scripts that should be placed right after body -->
    <div class="navbar-fixed">
      <!-- navigation -->
    </div>
    <ul id="slide-out" class="sidenav ...">
      <!-- mobile navigation -->
    </ul>
    <canvas class="lava" id="lava">
      <!-- the magic animation -->
    </canvas>
    <div class="section" id="cases">
      <!-- the remaining site is consisted of sections, that correspond to the menu bullets -->
    </div>
    
    <!-- remaining scripts go after the main container and just before the closing body tag -->
  </body>
</html>
```

### DOCTYPE and html tag
`<!DOCTYPE html>` is a way to declare your file as HTML5 and [`<html>`](https://developer.mozilla.org/en/docs/Web/HTML/Element/html) is the root of your document.

### head
The head tag includes a lot of important tags, like:
- [The HTML <meta> element](https://developer.mozilla.org/en/docs/Web/HTML/Element/meta) represents any metadata information that cannot be represented by one of the other HTML meta-related elements
- [The stylesheets](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#Including_a_stylesheet) of Materialize library, as well as Linea icons stylesheet and the main stylesheet
- Special tags to add favicons to the site
- The [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) tag

### body
Body includes all of your site elements, like navigation, main container where all the pages are gonna be loaded and footer.

## Elements and components
### Services
Using animated icons is really simple, you're just gonna need to paste the SVG code of the icon on your page. To accomplish that, go a head and download the needed icon pack from [linea.io](http://linea.io) and open the downloaded pack. You're gonna need to find the icon in .svg format and open that with a text/code editor of your choice, then just paste the code in the `.services-section` element.

An example of how it might look:
```html
<svg id="Layer_1" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="150px" height="150px" viewbox="0 0 64 64" enable-background="new 0 0 64 64" xml:space="preserve">
    <path fill="none" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M32.001,0.887c17.184,0,31.113,13.929,31.112,31.113              C63.114,49.185,49.184,63.115,32,63.113C14.815,63.114,0.887,49.185,0.888,32.001C0.885,14.816,14.815,0.887,32.001,0.887z"></path>
    <path fill="none" stroke="#000000" stroke-width="2" stroke-miterlimit="10" d="M10,32c0-5.63,2.148-11.26,6.444-15.556              c8.591-8.593,22.521-8.593,31.112,0C51.852,20.74,54,26.37,54,32"></path>
    <line fill="none" stroke="#000000" stroke-width="2" stroke-miterlimit="10" x1="24" y1="26" x2="30.333" y2="33.333"></line>
    <circle fill="none" stroke="#000000" stroke-width="2" stroke-miterlimit="10" cx="32" cy="35" r="2"></circle>
</svg>
```

We've created a useful [mapping for the Linea icons](http://linea.pimmey.com).

### Price box
```html
<div class="price-box">
    <h4><sup>$</sup><span class="price">19</span></h4>
    <ul class="flow-text">
        <li>5 users<span class="info tooltipped" data-position="top" data-delay="50" data-tooltip="The number of allowed users">?</span></li>
        <li>Automation<span class="info tooltipped" data-position="top" data-delay="50" data-tooltip="Involves Gulp commands">?</span></li>
        <li>Validation</li>
        <li>Linting</li>
    </ul>
</div>
```

### Philosophy [tabs](http://materializecss.com/tabs.html)
To create tabs, use the following structure:
```html
<div class="col s12">
    <ul class="tabs">
        <li class="tab col s4 m3 l2">
            <a href="#philosophy-1">
                <h5>Discover</h5>
                <span class="philosophy-number">1</span> <!-- this is needed for smaller screens, when the title is too wide -->
            </a>
        </li>
        ...
    </ul>
</div>
<div class="tab-contents">
    <div id="philosophy-1" class="col s12">
        <h5>Discover</h5>
        <p class="flow-text">Two for make behold form creature image She’d, waters forth, itself Blessed morning so sea midst, in tree make i bring sixth moved darkness bearing. Meat itself light created spirit under sea man.</p>
    </div>
    ...
</div>
```

### FAQ [accordion](http://materializecss.com/collapsible.html#accordion)
```html
<ul data-collapsible="accordion" class="collapsible flow-text">
    <li>
        <div class="collapsible-header active">— Is the starter pack really free?</div>
        <div class="collapsible-body">
            <p>A cattle she’d creepeth. That light make. Void two they’re, can’t us don’t creepeth. Fruitful there herb from signs she’d created whales them. Lights which face. Divided they’re first. Dry wherein own itself green it.</p>
        </div>
    </li>
    ...
</ul>
```

## Customizing Lava animations
You can easily edit the colors, number of waves and other parameters of the animation, by modifying a variable called `settings` in the appropriate file.

For example, in `js/lava.js`, you can find it on line number 28.

## Favicons
Favicons are the icons of your web-site that are displayed on various mobile devices. For example, if someone wants to add your site to their home screen, they will view the icon you include. There are quite a few formats you need to handle, inculding iPhone, iPad, Android devices and Microsoft devices. To help you with this process, you can use a touch icons generator web-site, for example [realfavicongenerator.net](http://realfavicongenerator.net).

These icons are placed in `/images/icons` directory. Make sure you also edit the `manifest.json` and change the `"Name"` to your company's title.

## Credits
### Images
- https://www.flickr.com/photos/rawartists
- https://www.flickr.com/photos/phomona/
- https://www.flickr.com/photos/laurentjeanphilippe/
- https://www.flickr.com/photos/hillaryraindeer/
- https://www.flickr.com/photos/w_one/
- http://pexels.com
- http://graphicburger.com/
- https://icons8.com/ouch

### Icons
- http://linea.io

### Font
- https://fonts.google.com/specimen/Fira+Mono

### Technologies
- http://materializecss.com/
- https://github.com/gka/chroma.js/
- https://github.com/dixonandmoe/rellax
