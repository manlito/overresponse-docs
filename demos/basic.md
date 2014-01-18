title: Basic
menu-locgroup: hidden

Basic Example
------------

This example shows the most basic implementation available, that is,
by copying the code provided using the publish button:


<div class="container">

<div id="ORClientContainer"></div>
<script>
  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer'
  };
  var ORScript = document.createElement('script');
  ORScript.async=1;
  ORScript.src= '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);}
</script>

</div>

The uncompressed and simplified version of the code to generate this survey is:

<pre><code>
<div id="ORClientContainer"></div>
<script>
  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer'
  };
  var ORScript = document.createElement('script');
  ORScript.async=1;
  ORScript.src= '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);}
</script>
</code></pre>

