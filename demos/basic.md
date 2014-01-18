title: Basic Example
menu-locgroup: hidden

Basic Example
------------

This example shows the most basic implementation available, that is,
by copying the code provided using the publish button:

<div id="ORClientContainer"></div>
<script>
  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer',
    alwaysShow: true
  };
  var ORScript = document.createElement('script');
  ORScript.async = true;
  ORScript.src = '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);
</script>

The uncompressed and simplified version of the code to generate this survey is:

<code><pre>
&lt;div id=&quot;ORClientContainer&quot;&gt;&lt;/div&gt;
&lt;script&gt;
  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer'
  };
  var ORScript = document.createElement('script');
  ORScript.async = true;
  ORScript.src = '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);
&lt;/script&gt;
</pre></code>

Please note the default height for surveys is 300px. 
