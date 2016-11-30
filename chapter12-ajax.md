## XMLHttpRequest
The moment you click a link on a web page your browser immediately fires of an ````HTTP```` request. While its waiting for the HTML from the server you might be presented with a blank screen. Nowadays, this blank screen is only visible for a couple of milliseconds. [Try](https://github.com/IT2805/curriculum/blob/master/chapter12-ajax.md) for yourself.

### Ajax
However, not all websites require the user to load the entire page when a link is clicked. In fact, you could argue that the most popular websites today are loaded dynamically with ````XMLHttpRequests````. This means that the content you see in your browser is loaded *after* the initial payload. You have probably noticed this behaviour while scrolling down your Facebook feed, or clicked on an e-mail in Gmail.

### Example
````XMLHttpRequest```` is an API that enables Javascript to send ````HTTP```` requests. Here is an example of how a web page would load a "newsfeed":

````javascript
var request = new XMLHttpRequest();
request.open('GET', '/newsfeed', true);

request.onload = function() {
  if (request.status === 200) {
    alert(request.responseText);
  }
};

request.send();
````

On the first line we instantiate a new ````XMLHttpRequest```` and assign it to the ````request```` variable. We proceed by instructing the request to use the ````HTTP```` ````GET```` verb to fetch the ````/newsfeed```` path. The last argument is a flag that determines if the request should be handled asynchronously or not.

The ````onload```` function is only executed when the server has responded to the request. In the example above we alert the response text, but we could have manipulated the document to update the page dynamically.

Finally we fire the request by calling ````send()```` on it.

### JSONP
Up until now we have only been concerned with loading content dynamically from the same server as the initial page load. However, sometimes you will want to load content from a completely different server. An example could be loading cute pictures of cats from Flickr on your blog.

Unfortunately for you, there's a restriction called ````Same-origin policy```` in the web development world. Due to security reasons, a page on one server can not simply load content of another. This means that your blog on ````cute-kittens.wordpress.com```` can not load content with an ````XMLHttpRequest```` from ````flickr.com````.

To circumvent this restriction you can use a technique called ````JSONP````. In short, ````JSONP```` *exploits* the lack of ````Same-origin policy```` when loading Javascript from one server of another. This technique requires however that the other server provides a so called ````callback```` parameter.

### Example
Without going too much into detail, here is an example of loading cute cats from a different server than ````api.flickr.com````.

````javascript
window.catsCallback = function(data) {
    alert(data);
};

var scriptElement = document.createElement('script');
scriptElement.setAttribute('src',
    'http://api.flickr.com/services/feeds/photos_public.gne' +
    '?tags=cats&format=json&jsoncallback=catsCallback'
);

document.body.appendChild(scriptElement);
````
