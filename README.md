canvas-to-bmp
=============

Client side HTML5 Canvas to BMP file format converter with support for 
alpha channel.

Virtually all browsers can read BMP files, but not all browsers supports 
BMP with canvas' toDataURL().

The **canvas-to-bmp** plugin solves this when you need your canvas 
graphics as BMP.


Features
--------

- Fast and small!
- All operations are asynchronous and non-blocking
- Supports alpha channel
- Can convert Canvas to BMP as ArrayBuffer
- Can convert Canvas to BMP as Blob
- Can convert Canvas to BMP as Data-URI
- No dependencies
- Documented source incl. HTML version (see docs/ folder)


Install
-------

**canvas-to-bmp** can be installed in various ways:

- Bower: `bower install canvas-to-bmp`
- Git using HTTPS: `git clone https://github.com/epistemex/canvas-to-bmp.git`
- Git using SSH: `git clone git@github.com:epistemex/canvas-to-bmp.git`
- Download [zip archive](https://github.com/epistemex/canvas-to-bmp/archive/master.zip) and extract.
- [canvastobmp.min.js](https://raw.githubusercontent.com/epistemex/canvas-to-bmp/master/canvastobmp.min.js)


Usage
-----

**canvas-to-bmp** is very easy to use. Just include the script in header 
or before the script section in your HTML file.

To convert the canvas to a BMP file, call:

    CanvasToBMP.toDataURL(canvas, function(uri) {
        // uri is a Data-URI that can be used as source for images etc.
        // uri = "data:image/bmp;base64, ...etc...";
    });

A faster option to Data-URIs is using Blobs:

    CanvasToBMP.toBlob(canvas, function(blob) {
        // blob object can be converted to an objectURL and then
        // set as source for images, or as download target:
        var url = URL.createObjectURL(blob);
    });

For convenience a direct Canvas to ObjectURL method is included:

    CanvasToBMP.toObjectURL(canvas, function(url) {
        // can be used as source for image or download target
    });

Convert to an ArrayBuffer that can be sent over the net:

    CanvasToBMP.toArrayBuffer(canvas, function(buffer) {
        // buffer is ArrayBuffer with the BMP file
    });

IMPORTANT: As with with ordinary canvas, cross-origin resource sharing 
(CORS) requirements must be fulfilled (see link below).


Issues
------

Feel free to report any issues you find.

Go to [issue tracker](https://github.com/epistemex/canvas-to-bmp/issues).

**Please note (these are not related to canvas-to-bmp):**

- Using large data-URIs can block the browser when it decodes them (use Blobs and ObjectURL instead) 
- Firefox (incl. v39) ignores the alpha channel in BMP files when reading them
- [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) is a security mechanism in the browser.


License
-------

Released under [MIT license](http://choosealicense.com/licenses/mit/). You may use this class in both commercial and non-commercial projects provided that full header (minified and developer versions) is included.


*&copy; Epistemex 2015*
 
![Epistemex](http://i.imgur.com/wZSsyt8.png)
