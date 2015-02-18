---
layout: post
category: blog
title:  "404 and other Status Codes"
img: "/images/http.jpg"
excerpt: "Google says 'Aw, Snap!' or 'He's dead Jim' but for us web developers, HTML status codes can provide much more information behind the scenes."
date:   2014-10-22
---
<!---image provided by dhester at http://cdn.morguefile.com/imageData/public/files/p/ppdigital/preview/fldr_2004_08_31/file000132267159.jpg --->

We have all heard of the common 404 code that means that the URL you typed does not exist or that the webpage is not active anymore. Google also adds its own messages such as "Aw, Snap!" when a website unexpectedly crashes or "He's dead Jim" when a webpage response times out. However, there is a lot more out there, and as web developers, these HTML status codes can provide much more information.

###Status Codes 300s and below

These are more or less positive codes. The 100s are informational codes sent during experimental conditions when testing out requests, so you may not see them too much browsing the internet. The 200s give the status of actions taken such as HTTP requests and GET requests. The common, happy status code is a "200 OK", which means your webpage has received and processed the information given successfully. The 300s will tell you more about redirects. For example, the "301 Moved Permanently" will inform you that the site that is being redirected to is going to be the permanent home of the webpage, so please note the URL change for future requests. If you refresh a webpage, sometimes it will say "304 Not Modified" meaning that some content was already stored in your cache and so the browser did not retransmit the information. This is common for images on webpages, which are not likely to change.

### Status Codes 400s and above

Now we are hitting errors. The 400s general indicate client errors while 500s indicate possible server issues. For example, "401 Unauthorized" means that a server will require authentication before accessing the site which is different from "403 Forbidden" in which the server refuses to allow access regardless of authentication status. You may have also see the "511 Network Authentication Required" which is common statement when users need to accept Terms and Service agreements before joining a public WIFI hotspot.
