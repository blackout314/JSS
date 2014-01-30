JSS
===

Json Simple Syndication

## example

```javascript
{
	"channel" : {
		"title": "title",
		"description": "description",
		"link": "link",
		"lastBuildDate": "timestamp",
		"pubDate": "timestamp",
		"ttl": 1800,
		"items": [
			{
			"title" : "title",
			"description" : "description",
			"link" : "link",
			"guid" : "unique string",
			"pubDate" : "timestamp"
			},
			{
			"title" : "title",
			"description" : "description",
			"link" : "link",
			"guid" : "unique string",
			"pubDate" : "timestamp"
			}
		]
	}
}
```

## jquery example

```javascript
$.getJSON( "jss.json", function( data ) {
	var items = [];
	$.each( data, function( key, val ) {
		debugger;
		$.each( val.items, function( ikey, ival ) {
			items.push( "<li id='" + ival.guid + "'>" + ival.title + "</li>" );
		});
	});
	$( "<ul/>", {
		"class": "my-new-list",
		html: items.join( "" )
	}).appendTo( "body" );
});
```
