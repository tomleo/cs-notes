REST API Design
===============

"The Web is a client-server based system, in which clients and servers have
distinct parts to play. They may be implemented and deployed independently,
using any language or technology, so long as they conform to the Web’s uniform
interface." pg3

"Interaction between Web components depend on the uniformity of their
interfaces...Each distinct Web-based concept is known as a resource and may be
addressed by a unique identifier, such as a URI." pg4

"The same exact resource can be represented to different clients in different
ways...representation is a way to interact with the resource but it is
not the resource itself." pg4

A constraint of the web is that it is stateless. "each client must include all
of the contextual information that it considers relevant in each interaction
with the web server. Web servers ask clients to manage the complexity of
communicating their application state so that the web server can service a much
larger number of clients." pg4

REST stands for Representational State Transfer

URL Format
----------

"URI = scheme "://" authority "/" path [ "?" query ] [ "#" fragment ]" - pg 11

"
Forward slash separator (/) must be used to indicate a hierarchical
relationship i.e. http://api.canvas.restapi.org/shapes/polygons/quadrilaterals/squares

To make your URIs easy for people to scan and interpret, use the hyphen
(-) character to improve the readability of names in long path segments.
Anywhere you would use a space or hyphen in English, you should use a
hyphen in a URI

Underscores (_) should not be used in URIs
" - pg 12

scheme and host components of URI should be case-insensitive, while the rest
of the path should be in lowercase.

"
File extensions should not be included in URIs instead they should rely
on the media type, as communicated through the Content-Type header, to
determine how to process the body’s content" - pg 13

"Consistent subdomain names should be used for your client developer
portal " - pg 14

LEFT OFF @ pg 14


REST API Design Rulebook by Mark Massé

