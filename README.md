##zGallery :: Native Javascript Gallery (ALPHA v.)
* [Demo](#demo)
* [About](#about)
* [Basic usage](#basic-usage)
* [Advanced usage](#advanced-usage)
  * [Plugin options](#plugin-options)
  * [Several galleries on page](#several-galleries-on-page)
* [Use mouse and keyboard](#use-mouse-and-keyboard)
* [Compatibility with browsers](#compatibility-with-browsers)
* [Change history](#change-history)

## Demo

zGallery demo is [here](http://linnas.github.io/zGallery)

## About

zGallery is lightweight, fast gallery based in pure Javascript+СSS3. Plugin **doesn't need for Jquery** or other similar framework.

Its size just **14 kb** (*with icons*). He is really **small**. Your page will load instantly!

## Basic usage

* Create new folder for your project. Create inside 3 new folders - *css*, *js*, *img*. Copy *zg-style.min.css* in *css* folder, *zgallery.min.js* in *js* folder and all images in *img* folder. 

You must have something like: 

- mysite/
    - css/
      - zg-style.min.css
    - js/
      - zgallery.min.js
    - img/
      - arrows.png
      - ...
- index.html

Then create basic HTML file in the root project directory with next markup:

```html
<!DOCTYPE html>
<html>
<head>
  <title>zGallery work test</title>
  <meta charset='utf-8'>
</head>
<body>
</body>
</html>
```

Then inside ```<head>``` tag include zGallery JS file

```html
<script src='js/zgallery.min.js'></script>
```

* Create div inside ```<body>``` tag with images

```html
<div id='my-gallery'>
  <img src="image1.jpg"  alt=''>
  <img src="image2.jpg" alt=''>
</div>
```


* Init zGallery, using event **DOMContentLoaded**, pass to the function ID of element with images *(by example my-gallery)*

```html
document.addEventListener("DOMContentLoaded", function () {
  zGallery.init('my-gallery');
});
```
* That's all! ;)

### Advanced usage

You can pass in a function your options to change the functional of zGallery.

### Plugin options

```JS
document.addEventListener("DOMContentLoaded", function () {
  var options = {
      //height of thumbnails
      previewHeight: 50,
      //Color of image wrapper
      background: '#000',
      //Enable preload images?
      autoPreload: true,
      //The key which will be added to the image ID
      prefix: 'zg-img',
      //Enable animations?
      animation: true,
      //Start slideshow immediately, after clicks by thumbnail
      slideshow: false,
      //Language of gallery menu
      lang: 'eng',
      //Path to the css file
      cssPath: 'css/zg-style.min.css',
      //Enable async stylesheet load
      loadCssAsync: true
  };
  
  zGallery.init('my-gallery', options);
});

```
*The available values for options*

* ```previewHeight: ``` {Boolean}
* ```autoPreload: ``` {Boolean}
* ```prefix: ``` {String}
* ```animation: ``` {Boolean}
* ```slideshow: ``` {Boolean}
* ```lang: ``` {String} eng (English), esp (Spanish), ua (Ukrainian), ru (Russian)
* ```cssPath: ``` {String}
* ```loadCssAsync: ``` {Boolean}

### Several galleries on page

You can create as many galleries as you need. You can do so:

Pattern: First parametr - *element(s)*, second - *options* for this element(s) and etc.

```JS
document.addEventListener("DOMContentLoaded", function () {
 var options = {
  previewHeight: 100,
  autoPreload: false
 };
 
 zGallery.init('my-gallery1, mygallery2', options, 'my-gallery3, my-gallery4', 'my-gallery5, my-gallery6, mygallery7');
});
```

### Use mouse and keyboard

**Keyboard control:**

* Right arrow - show next image
* Left arrow - show previous image
* Up arrow - show first image
* Down arrow - show last image
* Esc - close image gallery
* Enter - toggle fullscreen
* Space - start (stop) slideshow

**Mouse control:**

* Click on the right side of the screen - to show the next image
* Click on the left side of the screen - to show the previous image
* Using the mouse and gallery menu you can repeat the functionality of the keyboard

## Compatibility with browsers

zGallery works well in all browsers newer version.

Tested in:

* Mozilla Firefox 30
* Google Chrome 35
* IE 11
* Opera 12.16

## Change history

**1.7.2014**:
- Change slideshow logic
- Slideshows now possible run from the keyboard (Space button)
- Changed README.md

This is my first project at github so do not judge strictly. Thant you :)