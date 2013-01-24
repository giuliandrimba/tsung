Tsung
=====

Util method to get the properties of a class in the stylesheet.

Example:
--------

If you have in your stylesheet something like:

<pre>
.change_opacity
{
  opacity:0
}

.header .margin
{
  margin-top:"10px";
  margin-left:"10px";
}
</pre>

You could get the class properties using the "tsung" function.

<pre>
tsung("change_opacity"); //return {"opacity":"0"}
tsung(".header .margin"); //return {"margin-top":"10px", "margin-left":"10px"}
</pre>

Use case:
--------
This could be useful for animations using JS libraries like jQuery and TweenLite.

_This way, you can separate all the settings of the animations in the CSS file, eg:_

You can set the states of the animations in the CSS:

<pre>
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
</pre>

And in your JS code, you can get these properties and pass them as parameters to the animations libraries.

(using jQuery animate)
<pre>
$(".item").css( tsung(".item .after")) //set the properties before animating
$(".item").animate( tsung(".item .after"), 500 ) //animate getting the properties of the class 'after'
</pre>

(using TweenLite)
<pre>
TweenLite.to($(".item")
$(".item").css( tsung(".item .after")) //set the properties before animating
TweenLite.to($(".item"),{css:tsung(".item .after")}) //animate getting the properties of the class 'after'
</pre>

Tested in the following browsers
---------------
IE7+
Chrome 24+
Firefox 14+
Firefox 5+
