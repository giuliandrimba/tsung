Tsung
=====

Util method to get the properties of a class in the stylesheet.

Example:

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

You couldn get the class properties using the "tsung" function.

<pre.
tsung("change_opacity"); //return {"opacity":"0"}
tsung(".header .margin"); //return {"margin-top":"10px", "margin-left":"10px"}
</pre>
