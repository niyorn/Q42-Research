# Q42-Research
Q42 is a beautifull site that used a lot of the latest techniques. This is a research to find out how they do it.

## Fade technique:
![Scroll technique](''/assets-readme/scroll-fade.gif")

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
