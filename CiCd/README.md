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

1. copy rtx.tar.xz in folder and extract
2. open terminal at that folder
```ssh -i rtx dxxxxt@192.xxx.xx.xxx```
3. ```ls```
> Documents  dealflow Desktop   Downloads  Public
5. ```cd /etc/nginx/sites-enabled/```
6. ```ls```
> default
7. ```sudo nano default```
>
    #Engineering Excellence
    location /engr-excellence/ {
        proxy_pass http://127.0.0.1:8571/;  # Frontend on port 8571
        proxy_http_version 1.1;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }

    # API route (if accessed via /api/)
    location /engr-excellence/api/ {
        proxy_pass http://127.0.0.1:8570/;  # Backend on port 8570
        proxy_http_version 1.1;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }

8. now allow server to communicate with github account, generate ssh on server and add to github
9. ```git clone git@github.com:shayangd/engr-excellence.git```
10. ```cd engr-excellence```
11. ```create 3 .env in root,frontend and backend (paste .env.server content in these .env)```
12. ```docker compose up --build```
13. ```docker compose up -d```  (docker will keep on running on background)


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


