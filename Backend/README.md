# Backend
api, rest, soap

# API

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

### CRUD vs HTTP vs SUID
CRUD|HTTP Methods|SUID
:-:|:-:|:-:|
CREATE|POST/PUT|INSERT
READ|GET|SELECT
UPDATE|PUT/POST/PATCH|UPDATE
DELETE|DELETE|DELETE


### Mock Apis for testing

[Fake Store Api](fakestoreapi.com) ■ [reference](https://www.youtube.com/watch?v=sfjK21cPUds&list=PLRKyZvuMYSIPwjYw1bt_7u7nEwe6vATQd&t=74)
