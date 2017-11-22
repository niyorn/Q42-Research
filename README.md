# Q42-Research
Q42 is a beautifull site that used a lot of the latest techniques. This is a research to find out how they do it.

## Fade technique:
![Scroll technique](assets-readme/scroll-fade.gif)

Every div got a class fading
```javascript
.fading{
    transition: opacity .6s ease;
}
```
There is also a extra selector that put the opacity to 0
```javascript
.fading:not(.visible) {
    opacity: 0;
}
```
After scrolling and the div is above a certain tresshold they added a class: visible to the div
```html
<div class="fading visible"></div>
```
Because the div have the selector *visible* , the selector *.fading:not(.visible)* doesn't apply anymore.

For the checking if the element is in view I don't know for certain how they did, but I think they used Jquery. The user __annalarson__ from stack overflow showed an example how to do it. You can find it [here](https://codepen.io/annalarson/pen/GesqK)
*javascript example*
```javascript
$(document).ready(function() {
    /* Every time the window is scrolled ... */
    $(window).scroll( function(){

        /* Check the location of each desired element */
        $('.hideme').each( function(i){

            var bottom_of_object = $(this).position().top + $(this).outerHeight();
            var bottom_of_window = $(window).scrollTop() + $(window).height();

            /* If the object is completely visible in the window, fade it it */
            if( bottom_of_window > bottom_of_object ){

                $(this).animate({'opacity':'1'},1500);            
            }    
        });
    });
});
```
