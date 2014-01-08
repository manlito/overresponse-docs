
<div class="container">
	<div class="jumbotron">
			<h1>OverReponse DOCS</h1>
			<p class="lead">
				Want to know how to implement OverResponse in your site? This is 
				the place to get started.
			</p>
	</div>
</div>

[title: Overresponse Documentation]: /

<div class="alert alert-danger">
	<strong>Be carefull!</strong> This documentation may change until we leave the beta phase. See more at: <a href="http://blog.overresponse.com/about">http://blog.overresponse.com/about</a>.
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
			height
		</td>
		<td>	
			A string with desired height for the survey 
		</td>
		<td>
			This number is important when used in conjuction with **expandable** option, since the size of the container is established after the user clicks the first question. In other cases, you may set a height directly to the provided container, using your favorite mathod.
		</td>
	</tr>
</table>

# Events

OverResponse provides facility to handle almost all events related to the survey displaying and user interaction with the user. For instance, you can handle events to:

- Adjust your website content based on a response (e.g. Redirect respondant that says 'yes' to participate in a experiment)
- Use your own data store for responses
- Integrate with your favorite JS Framework
- Handle special events (such as bounces)


