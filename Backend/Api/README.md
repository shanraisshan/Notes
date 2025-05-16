
# API

| API Type     | Description                                                                | Key Characteristics                                                            | Use Cases                           |
|--------------|----------------------------------------------------------------------------|--------------------------------------------------------------------------------|-------------------------------------|
| [RESTful](Restful)      | Uses HTTP methods for CRUD operations, typically with JSON/XML.            | Stateless, resource-based, multiple endpoints, HTTP status codes.              | Web apps, mobile apps, public APIs. |
| [GraphQL](GraphQL)      | Query language for precise data fetching via a single endpoint.            | Single endpoint, flexible queries, strongly typed schema, JSON response.       | Complex apps, mobile/web with dynamic data. |
| [SOAP](SOAP)         | XML-based protocol for structured messaging, often over HTTP/SMTP.        | Strict standards, XML-based, supports WS-Security, reliable messaging.         | Enterprise systems, banking, legacy apps. |
| [gRPC](gRPC)         | High-performance RPC framework using HTTP/2 and Protocol Buffers.         | Binary data, HTTP/2, bidirectional streaming, code generation.                 | Microservices, low-latency systems. |
| [WebSocket](WebSocket)    | Persistent, bidirectional communication over a single TCP connection.      | Real-time, full-duplex, event-driven, not strictly an API.                     | Chat apps, gaming, live updates. |
| [Webhook](Webhook)      | Event-driven HTTP callbacks triggered by specific events.                  | Event-based, server pushes data to predefined URL.                             | Notifications, automation, integrations. |
| [XML-RPC](XML-RPC)      | Simple RPC protocol using XML over HTTP.                                  | Lightweight, executes predefined functions, XML-based.                        | Legacy systems, simple integrations. |

### Http Requests
Method|Defination|[Idempotent](https://restfulapi.net/idempotent-rest-apis/)
:-:|:-:|:-:
GET|read/retrieve data from server, 200 (OK)|YES
POST|send data to server, 201|[NO](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent)
PUT|modify the data on server. Replaces the entire content, if there are no resources that match the request, it will generate one|[NO](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent)
PATCH|similar to PUT, but it only replace the content that you want to update|YES
DELETE|delete the data on server, 200 (OK) or 204 (No Content)|YES
HEAD|asks for response identical to GET, but without the response body|YES
CONNECT|establishes a tunnel to the server identified by the target resource|[NO](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent)
OPTION|describes the communication options for the target resource|YES
TRACE|performs a message loop-back test along the path to the target resource|YES

### CRUD vs HTTP vs SIUD
CRUD|HTTP Methods|SUID
:-:|:-:|:-:|
CREATE|POST/PUT|INSERT
READ|GET|SELECT
UPDATE|PUT/POST/PATCH|UPDATE
DELETE|DELETE|DELETE


### Mock Apis for testing

[Fake Store Api](https://fakestoreapi.com) ■ [reference](https://www.youtube.com/watch?v=sfjK21cPUds&list=PLRKyZvuMYSIPwjYw1bt_7u7nEwe6vATQd&t=74)
