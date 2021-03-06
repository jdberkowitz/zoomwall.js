zoomwall.js
===========
zoomwall.js is a content-focused photo gallery using a horizontal masonry layout that scales up in lightbox mode. This variation adds support for CSS overlay information including a link for SEO optimization. 

##TODO
```
-Debug Firefox and IE Edge support (line breaking perhaps due to box-resizing)
```
-Add mobile support for overlay
```
-Move overlay to bottom caption on enlarge
```
-Debug height fit issues on image sets with large differences in image dimensions
```
-Prevent enlarge method on link click
```
-Add support for emtpy overlay information
```
-Add support for other overlay animations
```
-Add image Schema generation 



Visit [ericleong.github.io/zoomwall.js](http://ericleong.github.io/zoomwall.js) for a demo of the orignal.

Visit [https://codepen.io/JBerkowitzDesigns/pen/dEooQR](https://codepen.io/JBerkowitzDesigns/pen/dEooQR) for a demo pen of this fork.

[![CircleCI](https://circleci.com/gh/ericleong/zoomwall.js/tree/master.svg?style=svg)](https://circleci.com/gh/ericleong/zoomwall.js/tree/master)

install
-------
For those using [bower](http://bower.io/)
```bash
$ bower install zoomwall
```

For those using [npm](https://www.npmjs.com/)
```bash
$ npm install zoomwall.js
```

usage
-----

### html

First, add a reference to `zoomwall.js` and `zoomwall.css` in your HTML file, like this:
```html
<link rel="stylesheet" type="text/css" href="zoomwall.css" />
<script type="text/javascript" src="zoomwall.js"></script>
```

Add the `zoomwall` class to the container element. Include high resolution photos using the `data-highres` attribute of each `<img>` tag. 

```html
<div id="zoomwall" class="zoomwall">
<figure class="view view-tenth" >
    <img class="gallery-image" src="./image_1_small.jpg" data-highres="./image_1.jpg" alt="#">
    <div class="mask"><h2>TitleS</h2>
    <p>Description</p>
    <a href="#" class="info">LEARN MORE</a></div>
</figure>
<figure class="view view-tenth" >
    <img class="gallery-image" src="./image_2_small.jpg" data-highres="./image_2.jpg" alt="#">
    <div class="mask"><h2>TitleS</h2>
    <p>Description</p>
    <a href="#" class="info">LEARN MORE</a></div>
</figure>    
</div>
```

### javascript

Run `zoomwall.create()` on the container element (`#zoomwall` in this example), after they have loaded.

```javascript
window.onload = function() {
    zoomwall.create(document.getElementById('zoomwall'), true);
};
```

Enable support for paging through photos with the left and right arrow keys by setting the second argument to `true`, like this: `zoomwall.create(<element>, true)`.

If there are multiple galleries, call `zoomwall.keys()` after loading the last gallery.

```javascript
zoomwall.create(document.getElementById('first-gallery'));
zoomwall.create(document.getElementById('second-gallery'));
zoomwall.keys();
```
