Ajax - Asynchronous JavaScript and XML

Ajax is a combination of technologies that involve:
* HTML and CSS
* the DOM
* A method for exchanging data asynchronously between browser and server, avoiding page reloads. The XMLHttpRequest (XHR) object is usually used
but sometimes an IFrame object or a dynamically added tag is used instead.
* A format for data sent to the browser. Common formats include: JSON, XML, pre-formatted HTML, and plain text.

jQuery Ajax Syntax
`$.ajax('url', {settings})` where

**url** is a String and contains the url of where the request is sent.
**settings** is a PlainObject type, can be considered a set of key/value pairs that configure the Ajax request.

```JavaScript
  $.ajax('file.html',
  { 
    success: function() { /* do something if file.html is reach successfully */ },
    type: 'GET'
  })
