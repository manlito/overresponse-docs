title: Disabling SmartScrolling
menu-locgroup: hidden

Basic Example
------------

Suppose you want to serve a survey with so many text input fields. In this case, the use of automatic scrolling can be uncomfortable. But no worries yet, because you can get our sample survey as follows:


<div class="container">

<div id="ORClientContainer"></div>
<script>
  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer',
    scrollingMode: 'Classic',
    alwaysShow: true
  };
  var ORScript = document.createElement('script');
  ORScript.async = true;
  ORScript.src = '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);
</script>

</div>

You can get that result with the following code:

<code><pre>
&lt;div id=&quot;ORClientContainer&quot;&gt;&lt;/div&gt;
&lt;script&gt;
  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer',
    scrollingMode: 'Classic'
  };
  var ORScript = document.createElement('script');
  ORScript.async = true;
  ORScript.src = '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);
&lt;/script&gt;
</pre></code>

The only difference with the basic example is the <code>ScrollingMode</code> flag. This can be: <code>Smart</code>, <code>Manual</code> or <code>Classic</code>. In the manual mode survey, survey will not scroll by itself, but user scroll will continue to work in the *by block* style.



