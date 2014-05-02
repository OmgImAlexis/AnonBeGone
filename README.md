Anon Be Gone
=========

Add this before the < /head> tag

```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script><script>window.jQuery || document.write('<script src="http://code.jquery.com/jquery-2.0.3.min.js">\x3C/script>')</script>
<meta name="if:AnonBeGone" content="0" />
{block:IfAnonBeGone}
<script type="text/javascript">
$(document).ready(function() {
  var ask_box = $('iframe#ask_form');
  ask_box.attr('src', 'https://googledrive.com/host/0BweSwiVcpvLUdGZWOE9mSzVBN28');
});
</script>
{/block:IfAnonBeGone}
```
<br>
If you want people to be forced to login to use your ask use this code instead.
```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script><script>window.jQuery || document.write('<script src="http://code.jquery.com/jquery-2.0.3.min.js">\x3C/script>')</script>
<meta name="if:AnonBeGone" content="0" />
<script type="text/javascript">
    var is_logged_in = function(){
      {block:IfAnonBeGone}
      $(document).ready(function() {
        var ask_box = $('iframe#ask_form');
        ask_box.attr('src', 'https://googledrive.com/host/0BweSwiVcpvLUdGZWOE9mSzVBN28');
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
<br>

Make a new page called /anon and put this on it.
Make sure to use custom layout and enter your URL where it says YOUR_URL.
```html
<html>
<head>
<script type="text/javascript" src="http://code.jquery.com/jquery-1.7.2.min.js"></script>
<style type="text/css">
html, body { margin: 0; padding: 0; }
#abg_box { height: 46px; position: absolute; bottom: 0; left: 0; overflow: hidden; }
#abg_box iframe { position: absolute; bottom: 0; left: 0; }
#abg_box #inner { position: relative; overflow: hidden; width: 100%; height: 100%; }
</style>
<script type="text/javascript">
  var _gaq = _gaq || [];
  _gaq.push(['_setAccount', 'UA-12807423-42']);
  _gaq.push(['_trackPageview']);
  (function() {
    var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
    ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
    var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
  })();
</script>
</head>
<body>
    <iframe width="500px" height="190" scrolling="no" frameborder="0" src="http://www.tumblr.com/ask_form/YOUR_URL.tumblr.com" id="not_abg"></iframe>
  <div id="abg_box">
      <div id="inner">
        <iframe height="190" scrolling="no" frameborder="0" src="http://www.tumblr.com/ask_form/YOUR_URL.tumblr.com"></iframe>
        </div>
    </div>
    
    <script type="text/javascript">
      var frame_width = $(document).width();
    var ask_button_width = 90;
    var abg_width = frame_width - ask_button_width;
    function abg() {
      $('#abg_box iframe').width(frame_width);
      $('#abg_box').width(abg_width);
      $('#not_abg').width(frame_width);
    }
    abg()
    $(window).resize(function() {
      abg();
    });
    $('#not_abg').load(function() {
      $('#not_abg').load(function() {
        $('#abg_box').hide();
      })
    });
    </script>
</body>
</html>
```
