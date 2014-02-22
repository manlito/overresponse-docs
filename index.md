
<div class="jumbotron">
	<h1>OverResponse DOCS</h1>
	<p class="lead">
		Want to know how to implement OverResponse in your site? This is 
		the place to get started.
	</p>
</div>

[title: Developers @ OverResponse]: /

<div class="alert alert-warning">
	This documentation is still under development.
</div>

# Survey Configuration

By default, OverResponse requires a global variable called `ORSettings` with following attributes:

<table class="table table-striped">
	<tr>
		<th>
			Attribute
		</th>
		<th>
			Possible Values
		</th>
		<th>
			Notes
		</th>
	</tr>
	<tr>
		<td>
			surveyId (required)
		</td>
		<td>	
		Unique survey ID 
		</td>
		<td>	
		</td>
	</tr>
	<tr>
		<td>
			containerId (required)
		</td>
		<td>	
			The ID of the <code>div</code> element where the survey will be inserted 
		</td>
		<td>
			Code provided in Publish page on the survey editor will create this container where the code is placed.
		</td>
	</tr>
	<tr>
		<td>
			minimalSize
		</td>
		<td>	
			<code>true</code> or <code>false</code>
		</td>
		<td>
			When true, the survey will set its size to the minimum size, determined by the item with the item with the biggest height.
		</td>
	</tr>
	<tr>
		<td>
			height
		</td>
		<td>	
			A string with desired height for the survey 
		</td>
		<td>
			This number is important when used in conjuction with <strong>expandable</strong> option, since the size of the container is established after the user clicks the first question. In other cases, you may set a height directly to the provided container, using your favorite method.
		</td>
	</tr>
	<tr>
		<td>
			expandable
		</td>
		<td>	
			<code>true</code> or <code>false</code>
		</td>
		<td>
			When true, after the user answers the first item, the survey will set to the height specified in height parameter.
		</td>
	</tr>
	<tr>
		<td>
			alwaysShow
		</td>
		<td>	
			<code>true</code> or <code>false</code>
		</td>
		<td>
			By default, if users starts filling a survey, they will not be able to see the same survey again (unless cookies are cleared). Use this flag to force the display of a survey.
		</td>
	</tr>
	<tr>
		<td>
			showDelay
		</td>
		<td>	
			<code>int</code> (milliseconds)
		</td>
		<td>
			If desired, a fixed delay for the survey can be specified. This delay starts after the respondant.js file has been loaded.
		</td>
	</tr>
	<tr>
		<td>
			autoHide
		</td>
		<td>	
			<code>true</code> or <code>false</code>
		</td>
		<td>
			When using the default behavior, this setting will make the survey container to disappear after the user finishes the survey.
		</td>
	</tr>
	<tr>
		<td>
			fullScreen
		</td>
		<td>	
			<code>true</code> or <code>false</code>
		</td>
		<td>
			When true, the survey will have some features that assume the survey is the only (or at least, the main) item on page. For instance, the listener to the scroll will be enabled in all the <code>body</code>, versus the default behavior that only handles scroll in the survey container.
		</td>
	</tr>
	<tr>
		<td><a name="ignoreF"></a>
			ignoreFirstMouseScroll
		</td>
		<td>	
			<code>true</code> or <code>false</code>
		</td>
		<td>
			When true, survey will not capture mouse scroll unless the survey is activated by the user. When the flag is not set, default value will depend on <code>fullScreen</code> setting: if <code>fullScreen</code> is true, the this flag will default to false, and viceversa.
		</td>
	</tr>
	<tr>
		<td>
			template
		</td>
		<td>	
			Object name from array of templates
		</td>
		<td>
			The template to use, from the templates array. If using OverResponse default templates, possible values are: <code>Slim</code>, <code>ButtonLess</code> and <code>Simple</code>.
		</td>
	</tr>
	<tr>
		<td><a name="templates"></a>
			templates
		</td>
		<td>	
			Object
		</td>
		<td>
			Object composed of user templates. Each template only has one element. For instance, an object with a single template would be defined as:
			
			<pre><code>
{
  Slim: {
    html: ''
    + '&lt;div class=&quot;ORSlimContainer&quot;&gt;'
    + '	 &lt;div class=&quot;ORLayoutCenter&quot;&gt;'
    + '	   &lt;div class=&quot;ORSurveyContent&quot;&gt;&lt;/div&gt;'
    + '	 &lt;/div&gt;'
    + '	 &lt;div class=&quot;ORLayoutButtons&quot;&gt;'
    + '	   &lt;div class=&quot;ORLayoutButtonRow&quot;&gt;'
    + '      &lt;div class=&quot;ORLayoutLeft ORLeft Rounded5px NonSelectable&quot;&gt;&amp;lsaquo;&lt;/div&gt;'
    + '      &lt;div class=&quot;ORLayoutRight ORRight Rounded5px NonSelectable&quot;&gt;&amp;raquo;&lt;/div&gt;'
    + '	   &lt;/div&gt;'
    + '	 &lt;/div&gt;'
    + '&lt;/div&gt;'
  }
}
			</code></pre>
		</td>
	</tr>
	<tr>
		<td>
			controlClass
		</td>
		<td>	
			String with CSS class name
		</td>
		<td>
			If provided, this class will be added to all form controls that are system controls (only textboxes and textareas at the moment). Please note that checkboxes and radio elements are rendered using images.
		</td>
	</tr>
	<tr>
		<td>
			events
		</td>
		<td>	
			Object
		</td>
		<td>
			Each element must be named as the corresponding handler. For instance, the following code displays an alert box when the user answers the first question of a survey:
			
			<pre><code>
var ORSettings = {
  ... some other settings ...
  events: {
    onFirstItemChange: afterUserClickFirstItem
  }
};

function afterUserClickFirstItem(event) {
  alert('Hello world');
}
			</code></pre>
			
			Please read more on events bellow.
		</td>
	</tr>
</table>

# Events

OverResponse provides facility to handle almost all events related to the survey displaying and user interaction with the user. For instance, you can handle events to:

- Adjust your website content based on a response (e.g. Redirect respondant that says 'yes' to participate in a experiment)
- Use your own data store for responses
- Integrate with your favorite JS Framework
- Handle special events (such as bounces)

Event handlers are also assigned using the  `ORSettings` object. 

<table class="table table-striped">
	<tr>
		<th>
			Event
		</th>
		<th>
			Fired when
		</th>
		<th>
			Notes
		</th>
	</tr>
	<tr>
		<td>
			onFirstItemChange
		</td>
		<td>	
			User submits it first response 
		</td>
		<td>
			The event is fired even if the item is not the first item in the survey (for instance, when user skips questions).
		</td>
	</tr>
	<tr>
		<td>
			onItemChange
		</td>
		<td>	
			User submits or changes a response 
		</td>
		<td>
			The event is fires always the user submits a new response, or if a new value is sumitted.
		</td>
	</tr>
</table>

All event handlers receive an object with the event data. This object contains the following objects:

<table class="table table-striped">
	<tr>
		<th>
			Element
		</th>
		<th>
			Type
		</th>
		<th>
			Notes
		</th>
	</tr>
	<tr>
		<td>
			survey.reject
		</td>
		<td>	
			Function
		</td>
		<td>
			Call this method to hide the survey, and register it as a bounce.
		</td>
	</tr>
	<tr>
		<td>
			survey.container
		</td>
		<td>	
			jQuery element
		</td>
		<td>
			The main container for the survey.
		</td>
	</tr>
	<tr>
		<td>
			response.value
		</td>
		<td>	
			String
		</td>
		<td>
			The new string value for the related item.
		</td>
	</tr>
</table>
