Anon Be Gone
=========

This will force all anons to show their username instead of ```"Anonymous"```<br>
The new update doesn't require the /anon page and should work will all blogs.

Add this before the ```</head>``` tag
```html
<script>window.jQuery || document.write('<script src="http://code.jquery.com/jquery-2.0.3.min.js">\x3C/script>')</script>
<meta name="if:AnonBeGone" content="0" />
{block:IfAnonBeGone}
<script type="text/javascript">
$(document).ready(function() {
  var ask_box = $('iframe#ask_form');
  ask_box.attr('src', 'http://omgimalexis.github.io/AnonBeGone/');
});
</script>
{/block:IfAnonBeGone}
```
<br>
If you want people to be forced to login to use your ask use this code instead.
```html
<script>window.jQuery || document.write('<script src="http://code.jquery.com/jquery-2.0.3.min.js">\x3C/script>')</script>
<meta name="if:AnonBeGone" content="0" />
<script type="text/javascript">
    var is_logged_in = function(){
      {block:IfAnonBeGone}
      $(document).ready(function() {
        var ask_box = $('iframe#ask_form');
        ask_box.attr('src', 'http://omgimalexis.github.io/AnonBeGone/');
      });
      {/block:IfAnonBeGone}
    }

    var is_logged_out = function(){
        if ($('iframe#ask_form').length){
           window.location.href = "http://tumblr.com/login"; 
        }
    }
</script>
<!--
Tumblr Logged In Checker by apandhi
http://github.com/apandhi/Tumblr-Logged-In-Checker
-->
<script type="text/javascript" src="http://static.tumblr.com/3pomgja/LEEn32y7z/script.js"></script>
```
