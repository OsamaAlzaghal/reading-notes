# Authentication, Authorization, Cookies
## What is an HTTP cookie?


One of the biggest issues in the early days of the web was how to manage state. In short, the server had no way of knowing if two requests came from the same browser. The easiest approach, at the time, was to insert some token into the page when it was requested and get that token passed back with the next request. This required either using a form with a hidden field containing the token or to pass the token as part of the URL’s query string. Both solutions were intensely manual operations and prone to errors.

An HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to a user's web browser. The browser may store the cookie and send it back to the same server with later requests. Typically, an HTTP cookie is used to tell if two requests come from the same browser—keeping a user logged in.

## What are the main uses for cookies?
+ Session management: Logins, shopping carts, game scores, or anything else the server should remember.
+ Personalization: User preferences, themes, and other settings.
+ Tracking: Recording and analyzing user behavior.



## Creating cookies
After receiving an HTTP request, a server can send one or more Set-Cookie headers with the response. The browser usually stores the cookie and sends it with requests made to the same server inside a Cookie HTTP header. You can specify an expiration date or time period after which the cookie shouldn't be sent. You can also set additional restrictions to a specific domain and path to limit where the cookie is sent. For details about the header attributes mentioned below, refer to the Set-Cookie reference article.

**Note:** click on [this](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies) link to view the whole document.

**Note:** click on [this](https://humanwhocodes.com/blog/2009/05/05/http-cookies-explained/) link to view more info about cookies.






















