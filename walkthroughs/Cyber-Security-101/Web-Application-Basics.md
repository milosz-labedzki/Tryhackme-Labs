* `Front End` - The client-side layer of a software application responsible for user interfaces, visual design, interactive elements, and direct user interaction.

* `Back End` - The server-side layer of an application responsible for core business logic, database interactions, authentication, and API handling.

* `Scheme` - The initial segment of a URL that specifies the protocol or communication mechanism used to access a resource (e.g., http, https, ftp).

* `User` - An optional credentials parameter inside a URL structure specifying userinfo authentication data prior to the host identifier.

* `Host/Domain` - The structural component of a URL identifying the network host server or IP address serving the requested resource.

* `Port` - An optional numeric network endpoint in a URL specifying the target socket or service process on the destination server.

* `Path` - The structural segment of a URL indicating the specific location or logical route of a resource on the web server.

* `Query String` - The portion of a URL following a question mark (?) containing key-value parameters passed to the server for processing.

* `Fragment` - The final segment of a URL preceded by a hash symbol (#) referencing a specific internal anchor or element within the resource.

* `HTTP Requests` - Client-initiated network messages sent to a web server to request data, trigger operations, or submit state changes.

* `HTTP Responses` - Server-to-client messages generated in response to HTTP requests, delivering status information, headers, and payload data.

* `Start Line` - The initial line of an HTTP message, formatted as a Request-Line (method, URI, version) for requests or a Status-Line (version, status code) for responses.

* `Headers` - Key-value metadata fields included in HTTP messages to define operating parameters, payload attributes, authentication, and caching rules.

* `Empty line` - A required CRLF delimiter separating HTTP headers from the message body, signaling the end of metadata parsing.

* `Body` - The optional payload container of an HTTP message carrying the primary content, such as HTML documents, JSON, or uploaded files.

* `HTTP Method` - A standardized request parameter defining the specific action to be executed on a target server resource.

* `GET` - An HTTP method used to retrieve data from a target server without modifying resource or server state.

* `POST` - An HTTP method used to transmit payload data to a server for resource creation, processing, or state modification.

* `PUT` - An HTTP method used to upload a complete representation of a resource, replacing the target at the specified URI entirely.

* `DELETE` - An HTTP method used to request the permanent or logical removal of a target resource from the server.

* `PATCH` - An HTTP method used to apply partial, incremental updates to an existing resource without replacing it completely.

* `HEAD` - An HTTP method identical to GET that fetches only HTTP response headers without returning the payload body.

* `OPTIONS` - An HTTP method used to query the allowed communication methods and capabilities supported by a server for a given URI.

* `TRACE` - An HTTP method used to perform a message loop-back test along the path to the target resource for network diagnostics.

* `CONNECT` - An HTTP method used to establish a transparent, two-way TCP tunnel with a remote server, commonly used for TLS over proxies.

* `URL Path` - The path component located between the host/port and query string that identifies the target resource route on a server.

* `HTTP/0.9` - The primitive initial version of HTTP, supporting only the GET method and returning unformatted HTML without header metadata.

* `HTTP/1.0` - The first official HTTP standard, introducing response status codes, header fields, content types, and additional request methods over short-lived TCP connections.

* `HTTP/1.1` - The widely adopted HTTP version introducing persistent TCP connections (keep-alive), chunked transfer encoding, pipelining, and mandatory Host headers.

* `HTTP/2` - A major HTTP revision featuring binary framing protocol, multiplexing over a single connection, header compression (HPACK), and server push capabilities.

* `HTTP/3` - The modern generation of HTTP operating over the UDP-based QUIC protocol, eliminating TCP head-of-line blocking and speeding up TLS handshakes.
