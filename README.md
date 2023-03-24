npm install
npm run start


## Important
This is a Nginx Reverse Proxy server setup, YOU NEED TO ADD THE FOLLOWING TO YOUR NGINX.CONF file under the domain. Without the following configuration, it will not work.

```html
   location /proxy {  
  	add_header 'Access-Control-Allow-Origin' * always;
  	proxy_pass http://localhost:7777;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
      }
```
