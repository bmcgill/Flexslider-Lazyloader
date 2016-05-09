** incomplete **

# LazyLoader for FlexSlider 2

Add lazy loading for your FlexSlider 2 slideshow images. There are a couple other implementations but they either didn't work or were overly complicated.

##Usage
- Install [FlexSlider 2](http://flexslider.woothemes.com/) and confirgure as desired.
- Include jquery.flexslider.LazyLoader.min.js
- For slides that should lazy load, add a class of *lazy* and change the *src* to *data-src* to prevent loading. The first slide should not be changed.

```
<ul class="slides">
  <li><a href="/page1"><img height="300" width="400" src="/image1.jpg" alt="" /></a></li>
  <li><a href="/page2"><img class="lazy" height="300" width="400" data-src="/image2.jpg" alt="" /></a></li>
  <li><a href="/page3"><img class="lazy" height="300" width="400" data-src="/image3.jpg" alt="" /></a></li>
  <li><a href="/page4"><img class="lazy" height="300" width="400" data-src="/image4.jpg" alt="" /></a></li>
</ul> 
```

- Add the *start* and *before* attributes to the slider init
 * *start* fires when the first slide loads
 * *before* fires when a new slide is loaded
```
$(".slider").flexslider({
  // Lazy loading
  start: function(slider) { flexsliderLazyloaderInit(slider) },
  before: function(slider) { flexsliderLazyloaderLoad(slider) }
});
```
