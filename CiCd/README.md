# CI/CD (Deployment)
Continuous integration Continuous Development

## [Bitbucket Pipelines](https://support.atlassian.com/bitbucket-cloud/docs/get-started-with-bitbucket-pipelines/) 
- bitbucket-pipelines.yml

## Web Servers
Nginx, Apache, and Tomcat are software components commonly used in web application deployment.

### Deployment step by step
Prompt
```
i want to deploy my single repo (frontend nextjs and backend fastapi) app on server. i have server ssh ip and password.
tell me step by step process of deployment.
```

# Ports

|Port|Service|
|-|-|
| 22|SSH|
| 53|DNS|
| 80 or 8000 or 8080| HTTP|
| 443 or 8443| HTTPS|
| 3000|Dev Server (commonly React/Node.js)|
| 3306|MySQL|
| 5432|PostgreSQL|
| 27017|MongoDB|
| 6379|Redis|

- localhost and 127.0.0.1 are essentially interchangeable for accessing the local machine, but localhost is a name, while 127.0.0.1 is the actual IP address.
- 0.0.0.0 is not an address you connect to; it’s used by servers to bind to all interfaces. Connecting to 0.0.0.0 directly is invalid.


