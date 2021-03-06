##Setup and Configuration

###Prerequisites

Your DNAS version must have JSON support, if it does not then you will not be able to use this plugin.

###Setup

Download the plugin and store jquery.shoutcast.easy.min.js somewhere on your server.

Add the following line of code just before the `</body>` tag:

```html 
<script>window.jQuery || document.write('<script src="https://ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"><\/script>')</script>
<script src="jquery.shoutcast.easy.min.js?host=example.com&port=8000"></script>
```

###Configuration

In the second script tag you need to edit example.com to be your host and also edit the port if necessary, this is the minimum configration that is required by the plugin, there are more options which can be found here

###Usage
Once you have configured the plugin you will need to add various elements to your page.

####Showing Stats

To show any statistics from your stream you simply need to add an element with adata-shoutcast-value="" attribute, for example, if I wanted to show the currently playing song this is what you would have:

```html
<p data-shoutcast-value="songtitle"></p>
```

Or current listeners:

```html
<span data-shoutcast-value="currentlisteners"></span>
```

All of the available values can be found here

####Showing played tracks

To show played tracks you need to an an ul element with an id of played to your page:

```html
<ul id="played"></ul>
```

With the above element on the page the names of the recently played tracks will be displayed in order.

####Example HTML

```html
<!DOCTYPE html>
   <html>
   <head>
      <title>My Radio Station</title>
   </head>
   <body>
      
      <h1 data-shoutcast-value="servertitle"></h1>
      
      <p>Now Playing: <span data-shoutcast-value="songtitle"></span></p>
      <p>Listeners: <span data-shoutcast-value="currentlisteners"></span>/<span data-shoutcast-value="maxlisteners"></span></p>
      
      <h2>You just missed</h2>
      <ul id="played"></ul>
      
      
      <script src="//ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
      <script src="jquery.shoutcast.easy.min.js?host=example.com&port=8000"></script>
   </body>
   </html>
```

The above HTML will display the server title, the current song, the current listeners, the maximum listeners and a list of all of the recently played tracks.