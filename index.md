
<div class="jumbotron">
	<h1>OverResponse DOCS</h1>
	<p class="lead">
		Want to know how to implement OverResponse in your site? This is 
		the place to get started.
	</p>
</div>

[title: Overresponse Documentation]: /

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
			containerId
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
			Number of milliseconds
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
			When true, the survey will have some features that assume the survey is the only (or at least, the main) item on page. For instance, the listener to the scroll will be enabled in all the <code>body<body>, versus the default behavior that only handles scroll in the survey container.
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
		<td>
			templates
		</td>
		<td>	
			Object
		</td>
		<td>
			Object composed of user templates. Each template only has one element. For instance, OverResponse default templates are defined as:
			
			<code>
			{
		Simple: {
			html: &#39;&#39;
				+ &#39;&lt;div class=&quot;ORSimpleContainer&quot;&gt;&#39;
				+ &#39;	&lt;div class=&quot;ORLayoutLeft Rounded5px NonSelectable&quot;&gt;&amp;lsaquo;&lt;/div&gt;&#39;
				+ &#39;	&lt;div class=&quot;ORLayoutCenter&quot;&gt;&lt;/div&gt;&#39;
				+ &#39;	&lt;div class=&quot;ORLayoutRight Rounded5px NonSelectable&quot;&gt;&amp;raquo;&lt;/div&gt;&#39;
				+ &#39;&lt;/div&gt;&#39;
		},
		ButtonLess: {
			html: &#39;&#39;
				+ &#39;&lt;div class=&quot;ORButtonLessContainer&quot;&gt;&#39;
				+ &#39;	&lt;div class=&quot;ORLayoutCenter&quot;&gt;&lt;/div&gt;&#39;
				+ &#39;&lt;/div&gt;&#39;
		},
		Slim: {
			html: &#39;&#39;
				+ &#39;&lt;div class=&quot;ORSlimContainer&quot;&gt;&#39;
				+ &#39;	&lt;div class=&quot;ORLayoutCenter&quot;&gt;&lt;/div&gt;&#39;
				+ &#39;	&lt;div class=&quot;ORLayoutButtons&quot;&gt;&#39;
				+ &#39;  &lt;div class=&quot;ORLayoutLeft Rounded5px NonSelectable&quot;&gt;&amp;lsaquo;&lt;/div&gt;&#39;
				+ &#39;  &lt;div class=&quot;ORLayoutRight Rounded5px NonSelectable&quot;&gt;&amp;raquo;&lt;/div&gt;&#39;
				+ &#39;	&lt;/div&gt;&#39;
				+ &#39;&lt;/div&gt;&#39;
		}
	}
			
			</code>
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
</table>

# Events

OverResponse provides facility to handle almost all events related to the survey displaying and user interaction with the user. For instance, you can handle events to:

- Adjust your website content based on a response (e.g. Redirect respondant that says 'yes' to participate in a experiment)
- Use your own data store for responses
- Integrate with your favorite JS Framework
- Handle special events (such as bounces)


