remote-adaptive-images
======================

Adaptive images using a remote source, e.g. Flickr

This was predominately inspired by [Responsive Images](https://github.com/filamentgroup/Responsive-Images) by The Filament Group. Their system is certainly more robust, but it wasn't quickly and easily allowing me to pull from Flickr with minimal effort.

There's probably a better way to do this, and a good reason not to. The fact that I haven't seen a solution like this implies that I've missed some horrible reason that makes this approach utter garbage. Please correct me if I've done something silly.

How To Use
----------
1. Copy the rules from the .htaccess file into your own.
2. Add the javascript from below into the <head> of your page. Adjust breakpoints as necessary.
3. Use the image url for embedding the photo, dropping the http://
4. Use folder names "large" and "regular" to differentiate specific sizes (again, for lightboxes)
5. Profit.

Javascript
----------
```javascript
if (screen.width <= 480) {
  document.cookie = "res=480;";
}
else {
  document.cookie = "res=960;";
}
```

HTML Example
------------
```html
<a href="large/farm8.staticflickr.com/7225/6899206864_0d038b821c.jpg" rel="lightbox">
	<img src="regular/farm8.staticflickr.com/7225/6899206864_0d038b821c.jpg" alt="2012-03-19_20-06-06_770">
</a>
```

Known issues
------------
Images are cached using the same file name, so testing at multiple sizes can be troublesome. In practice, I don't see this being much of an issue, however.

Potential violation of ToS for image hosting services. My aim is to continue to use Flickr as my repository of images. I looked through their various terms and didn't find anything that would preclude a trick such as this. However, they do have limits to the number of images you can have on one page (max 30, as of this writing). If you're using another service, YMMV.

License
-------
copyright 2012, Nathanael Phillips
Released under the MIT License