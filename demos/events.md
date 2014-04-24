title: Events
menu-locgroup: hidden

Events Example
------------

One of the advantages of OverResponse is that you can listen to what is
going on with the survey. For instance, you could call your own API when
the user completes the survey. 

Next example shows how you can do this by sending callbacks
along the `ORSettings` object:

<div id="ORClientContainer"></div>
<script>

  function appendContentToLogger(content) {
    // Be aware your user could send anything... it is unprocessed, unescaped and unencoded
    $('#LoggerExample').append('<div>' + content + '</div>');
  }

  var ORSettings = {
    surveyId: '51870fd5f6664b9314000011',
    containerId: 'ORClientContainer',
    alwaysShow: true,
    onFirstItemChange: function(event) {
      appendContentToLogger('First item was answered with ' + event.response.value);
    },
    onItemChange: function(event) {
      appendContentToLogger('An item was answered with ' + event.response.value);
    },
    onSurveyFinish: function(event) {
      appendContentToLogger('Survey was finished');
    }
  };

  var ORScript = document.createElement('script');
  ORScript.async = true;
  ORScript.src = '//overresponse.com/scripts/respondant/respondant.js';
  document.getElementsByTagName('head')[0].appendChild(ORScript);

</script>
<div id="LoggerExample" class=""><div class="label label-default">Logger</div></div>

As the note in the code indicates, there is no processing on the what the user submits
to an item. So, if you plan to send the data to your server, please make sure you clean it.


