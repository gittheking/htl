# HTL Quiz 

## Explain the difference between `http` and `https`.

- The Added 's' at the end stands for 'secure'. HTTPS is considered much more secure than HTTP as it creates an encrypted connection through the use of SSL certificates. This is the preferred connection for any site where sensitive inforamtion is being passed.

## What is the difference between a `GET` and a `POST` request?

- A 'GET' request is simply sending a request to a server over http asking for some information in return - an example of this would be sending an API request to recieve some JSON data back. A 'POST' request is when you are sending data to a server to be processed for something - an example of a 'POST' request would be any time you are submitting information in a form. 

## What is the difference between 2xx and 4xx HTTP status codes?

- A 2xx HTTP status code indicates that your request went through successfully. a 4xx status indicates that the client made a bad request, such as attempting to visit a path that does not exist (404 - page not found).

## What is AJAX? Describe a situation where it is useful.

- AJAX stands for Asynchronous JavaScipt and XML. AJAX is useful for making API calls as it allows for non-blocking(asynchronoius) behavior despite JavaScript's single threaded nature while waiting for your data return successfully - which then fires off a callback. 

## What is responsive design 

- Responsive Desgin is an approach to making the client's viewing experience optimized across several devices. An example of this would be having a webpage that is easily navigated and still looks great whether you're on your laptop, tablet, or your phone (of course this may mean that the layout could be different between devices).

## What is the difference between these three CSS rules?
```css
div {
  background: #FFF;
}
#div {
  background: #FFF;
}
.div {
  backgkound: #FFF;
}
```
- The first rule apllies to _all_ divs, the second rule applies to every element with an `id` of `"div"`, and the 3rd rule applies for all elements with a `class` of `"div"`.

## What is the difference between these 2 uses of the `<script>` tag?
```html
<script src-"http://example.com/whatever.js"></script>
<script>var whatever = true</script>
```
- The first script is linked to the HTML through the use of some sort of CDN(Content Delivery Network), and the second script is inline scripting where you can write executable JavaScript.

## What is the difference between these two JavaScript snippets?
```javascript
var x = function() {
  return 1 + 1;
}()

var y = function() {
  return 1 + 1;
}
```
- `x` is a self-invoking function, meaning that you can call x by writing `x;`, whereas `y` is only being defined and will still need the parantheses when invoking it - `y();`. 

## Write HTML/CSS to draw the following scene:
  - One red box 200x200 pixels 
  - One blue box 200x200 pixels 
  - One Green box 100x100 pixels
  - The green should be centered inside of the red box
  - The red and blue boxes should not overlap
    * [HTML](index.html)
    * [CSS](style.css)

## Caching and Analytics

#### Why is caching a problem for the analytics company?
- Caching allows the browser to temporarily store the image in memory, meaning that the client won't have to send a request to the analytic company's servers to load the image. This will cause the number of times the pixel has been loaded to be innacurate. 

#### How can you prevent browser caching?
- You can prevent browser caching by adding HTTP headers (which can be done many ways). Here is an example of how to accomplish this using meta tags in the `head` of your HTML:
```html
<meta http-equiv="Cache-Control" content="no-cache", no-store, must-revalidate />
<meta http-equiv="Pragma" content="no-cache" />
<meta http-equiv="Expires" content="0" />
```

#### List some information a tracking company could collect.
- Likely location of user (from the IP address)
- User Agent: Shows Operating system and the type of web client being used
- Cookies allow for the site currently being accessed to see what other pages on it's own site the user has visited - this is great for suggesting related pages and increases user retention.

#### List additional tracking techniques that could be collected with the use of a `<script>` tag instead of an `<img>` tag.
- Script tags will allow a tracking company to quite literally track a user's every movement with event listeners. Event listeners could tell tracking companies how many times a user moused over their ad and for how long, how long it took from load time for a user to click the [x]/'close' button when a pop up advertisement comes up, every link that is clicked on the page, etc. All of these events can be sent back to a trackign companies servers for analysis of user behavior which results in targetted ads. 

## Checking if image is viewable every 2 seconds
Using JQuery:
```javascript
window.setInterval(function(){
  var windowTop = $(window).scrollTop();
  var windowBottom = windowTop + window.innerHeight;
  var imgTop = $('#myImage').position().top;
  var imgBottom = imgTop + $('#myImage').height(); 
  if(windowTop < imgTop && imgTop < windowBottom || windowTop < imgBottom && imgBottom < windowBottom){
    console.log('visible');
  }
},2000);
```