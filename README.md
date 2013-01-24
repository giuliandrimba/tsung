Tsung
=====

Util method to get the properties of a class in the stylesheet.

Example:
--------

If you have in your stylesheet something like:

````css
.change_opacity
{
  opacity:0
}

.header .margin
{
  margin-top:"10px";
  margin-left:"10px";
}
````

You could get the class properties using the "tsung" function.

````javascript
tsung("change_opacity"); //return {"opacity":"0"}
tsung(".header .margin"); //return {margin-top:"10px", margin-left:"10px"}
````

Use case:
--------
This could be useful for animations using JS libraries like jQuery and TweenLite.

__This way, you can separate all the settings of the animations in the CSS file, eg:__

You can set the states of the animations in the CSS:

````css
.item .before
{
   top:10px;
   left:"10px";
   opacity:0;
}

.item .after
{
  top:0;
  left:"0";
  opacity:1;
}
````

And in your JS code, you can get these properties and pass them as parameters to the animations libraries.

> using jQuery animate

````javascript
$(".item").css( tsung(".item .before")) //set the properties before animating
$(".item").animate( tsung(".item .after"), 500 ) //animate getting the properties of the class 'after'
````

> using TweenLite

````javascript
$(".item").css( tsung(".item .before")) //set the properties before animating
TweenLite.to($(".item"), 0.5,{css:tsung(".item .after")}) //animate getting the properties of the class 'after'
````

Tested in the following browsers
---------------

* IE7+
* Firefox 14+
* Safari 5+
* Chrome 24+
