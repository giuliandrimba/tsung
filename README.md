Tsung
=====

Util method to get the properties of a class in the stylesheet.

Example:

<pre>

<style>

.change_opacity
{
  opacity:0
}

.header .margin
{
  margin-top:"10px";
  margin-left:"10px";
}

</style>

<script type="text/javascript">
tsung("change_opacity"); //return {"opacity":"0"}
tsung(".header .margin"); //return {"margin-top":"10px", "margin-left":"10px"}
</script>

</pre>
