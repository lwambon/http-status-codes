# Information responses

## 100 continue

The HTTP 100 Continue status tells the client that the initial part of a request was received, and the server is ready for the rest. It’s useful when sending large data, avoiding unnecessary uploads if the server might reject the request.

## 101 Switching Protocols
The HTTP 101 Switching Protocols status code indicates that the server is changing to a different protocol as requested by the client, typically used to switch from HTTP/1.1 to a protocol like WebSockets.
## 102 Processing protocol
The HTTP 102 Processing status code is used in WebDAV (an extension of HTTP). It indicates that the server has received and is processing the request, but no final response is yet available. It helps prevent client timeouts during long operations.
## 103 Early Hints
The HTTP 103 Early Hints status allows a server to send preliminary information about resources (like links) before the full response is ready. This helps browsers preload resources or preconnect to sites early, improving page load performance. It’s mainly used with the Link header.

# Successful Responses

## 200 OK
The HTTP 200 OK status code indicates that a request has been successfully received, understood, and processed by the server. It is the standard response for successful HTTP requests, meaning the server has returned the requested resource or performed the requested action without errors. The response can vary depending on the method used (e.g., GET, POST) but typically includes content in the body.
## 201 created
The HTTP 201 Created status code indicates that a request has successfully led to the creation of a resource. It usually follows POST requests, confirming that the resource has been generated and providing its location via a `Location` header.

## 202 Accepted
The HTTP 202 Accepted status code indicates that a request has been received but is still being processed. The server acknowledges the request but doesn't guarantee immediate completion. It's often used for tasks that may take some time to complete.

## 203 Non-Authoritative Information

The HTTP 203 Non-Authoritative Information status code indicates that the request was successful, but the returned response might have been modified from the origin server's version. The content returned is from a transforming proxy or another source, rather than directly from the original server.
## 204 No Content
The HTTP 204 No Content status code means the request was successful, but the server did not return any content in the response body. The client doesn't need to navigate away from its current page.

## 205 Reset Content
Indicates that the request has been successfully processed and the client should reset the document view.

## 206 Partial Content
The HTTP 206 Partial Content status code indicates that the server successfully fulfilled a range request for the target resource, only delivering part of the requested data. This is commonly used for resuming interrupted downloads.

## 207 Multi-Status
Indicates a mixture of responses. This response is used exclusively in the context of Web Distributed Authoring and Versioning 

## 208 Already Reported
The HTTP 208 Already Reported indicates that the server has already included the specified resources in a previous response, typically used with WebDAV to avoid sending duplicate information about a set of resources.

## 226 IM Used
Indicates that the server is returning a delta in response to a GET request. It is used in the context of HTTP delta encodings.
IM stands for instance manipulation, which refers to the algorithm generating a delta.

# Redirection messages

## 300 Multiple Choices
The HTTP 300 Multiple Choices redirection response status code indicates that the request has more than one possible response. The user-agent or the user should choose one of them.

## 301 Moved Permanently
Indicates that the requested resource has been permanently moved to the URL in the Location header.
A browser receiving this status will automatically request the resource at the URL in the Location header, redirecting the user to the new page.

## 302 Found
Indicates that the requested resource has been temporarily moved to the URL in the Location header.
A browser receiving this status will automatically request the resource at the URL in the Location header, redirecting the user to the new page.

## 303 See Other
indicates that the browser should redirect to the URL in the Location header instead of rendering the requested resource.Often sent back as a result of PUT or POST methods so the client may retrieve a confirmation.

## 304 Not Modified
Indicates that there is no need to retransmit the requested resources.
This response code is sent when the request is a conditional GET or HEAD request with an If-None-Match or an If-Modified-Since header and the condition evaluates to 'false'.

## 307 Temporary Redirect
Indicates that the resource requested has been temporarily moved to the URL in the Location header.
A browser receiving this status will automatically request the resource at the URL in the Location header, redirecting the user to the new page.

## 308 Permanent Redirect
Indicates that the requested resource has been permanently moved to the URL given by the Location header.
A browser receiving this status will automatically request the resource at the URL in the Location header, redirecting the user to the new page.

# Client error responses

## 400 Bad Request
Indicates that the server would not process the request due to something the server considered to be a client error. The reason for a 400 response is typically due to malformed request syntax, invalid request message framing, or deceptive request routing.

## 401 Unauthorized
Indicates that a request was not successful because it lacks valid authentication credentials for the requested resource.

## 402 Payment Required
This status code was created to enable digital cash or (micro) payment systems and would indicate that requested content is not available until the client makes a payment.

## 403 Forbidden
Indicates that the server understood the request but refused to process it.

## 404 Not Found

Indicates that the server cannot find the requested resource.A 404 status code only indicates that the resource is missing without indicating if this is temporary or permanent.

## 405 Method Not Allowed
Indicates that the server knows the request method, but the target resource doesn't support this method. The server must generate an Allow header in a 405 response with a list of methods that the target resource currently supports.

## 406 Not Acceptable
Indicates that the server could not produce a response matching the list of acceptable values defined in the request.

## 407 Proxy Authentication Required
Indicates that the request did not succeed because it lacks valid authentication credentials for the proxy server that sits between the client and the server with access to the requested resource.

## 408 Request Timeout
Indicates that the server would like to shut down this unused connection. A 408 is sent on an idle connection by some servers, even without any previous request by the client.

## 409 Conflict
The status code indicates that the request could not be completed due to a conflict with the current state of the resource.
They are errors sent to the client so that a user might be able to resolve a conflict and resubmit the request.

## 410 Gone
It indicates that the target resource is no longer available at the origin server and that this condition is likely to be permanent. A 410 response is cacheable by default.

## 411 Length Required
It indicates that the server refused to accept the request without a defined Content-Length header.

## 412 Precondition Failed
It indicates that access to the target resource was denied.

## 413 Content Too Large
It indicates that the request entity was larger than limits defined by server. The server might close the connection or return a Retry-After header field.
## 414 URI Too Long
This indicates that a URI requested by the client was longer than the server is willing to interpret.
## 415 Unsupported Media Type
This indicates that the server refused to accept the request because the message content format is not supported.
The format problem might be due to the request's indicated Content-Type or Content-Encoding, or as a result of processing the request message content.
## 416 Range Not Satisfiable
This indicates that a server could not serve the requested ranges. The most likely reason for this response is that the document doesn't contain such ranges, or that the Range header value, though syntactically correct, doesn't make sense.
## 417 Expectation Failed
Indicates that the expectation given in the request's Expect header could not be met. After receiving a 417 response, a client should repeat the request without an Expect request header, including the file in the request body without waiting for a 100 response.
## 418 I'm a teapot
Indicates that the server refuses to brew coffee because it is, permanently, a teapot. A combined coffee/tea pot that is temporarily out of coffee should instead return 503.
## 421 Misdirected Request
 Indicates that the request was directed to a server that is not able to produce a response. This can be sent by a server that is not configured to produce responses for the combination of scheme and authority that are included in the request URI.
 ## 422 Unprocessable Content
 Indicates that the server understood the content type of the request content, and the syntax of the request content was correct, but it was unable to process the contained instructions.
 ## 423 Locked
 This indicates that a resource is locked, meaning it can't be accessed. Its response body should contain information in WebDAV's XML format.
 ## 424 Failed Dependency
 Indicates that the method could not be performed on the resource because the requested action depended on another action, and that action failed.

 ## 425 Too Early
 Indicates that the server was unwilling to risk processing a request that might be replayed to avoid potential replay attacks.
 ## 426 Upgrade Required
  Indicates that the server refused to perform the request using the current protocol but might be willing to do so after the client upgrades to a different protocol.
  ## 428 Precondition Required
  This status indicates that the server requires the request to be conditional.
 Typically, a 428 response means that a required precondition header such as If-Match is missing.
 ## 429 Too Many Requests
 The status indicates the client has sent too many requests in a given amount of time. This mechanism of asking the client to slow down the rate of requests is commonly called "rate limiting".
 ## 431 Request Header Fields Too Large
 The status code indicates that the server refuses to process the request because the request's HTTP headers are too long. The request may be resubmitted after reducing the size of the request headers.
 ## 451 Unavailable For Legal Reasons
 This indicates that the user requested a resource that is not available due to legal reasons, such as a web page for which a legal action has been issued.

 # Server Error Response
 ## 500 Internal Server Error
 Indicates that the server encountered an unexpected condition that prevented it from fulfilling the request. This error is a generic "catch-all" response to server issues, indicating that the server cannot find a more appropriate 5XX error to respond with.
 ## 501 Not Implemented
 The status code means that the server does not support the functionality required to fulfill the request.
A response with this status may also include a Retry-After header, telling the client that they can retry the request after the specified time has elapsed.
## 502 Bad Gateway
 Indicates that a server was acting as a gateway or proxy and that it received an invalid response from the upstream server.
 ## 503 Service Unavailable
 Indicates that the server is not ready to handle the request.
Common causes are that a server is down for maintenance or overloaded
## 504 Gateway Timeout
Indicates that the server, while acting as a gateway or proxy, did not get a response in time from the upstream server in order to complete the request.
## 505 HTTP Version Not Supported
Indicates that the HTTP version used in the request is not supported by the server.
It's common to see this error when a request line is improperly formed such as GET /path to resource HTTP/1.1 or with \n terminating the request line instead of \r\n.
## 506 Variant Also Negotiates
The status code is returned during content negotiation when there is recursive loop in the process of selecting a resource.
## 507 Insufficient Storage
 Indicates that an action could not be performed because the server does not have enough available storage to successfully complete the request.
 ## 508 Loop Detected
 Indicates that the entire operation failed because it encountered an infinite loop while processing a request with Depth: infinity.
The status may be given in the context of the Web Distributed Authoring and Versioning (WebDAV).
## 510 Not Extended
The status code is sent when the client request declares an HTTP Extension (RFC 2774) that should be used to process the request, but the extension is not supported.
## 511 Network Authentication Required
 Indicates that the client needs to authenticate to gain network access. This status is not generated by origin servers, but by intercepting proxies that control access to a network.