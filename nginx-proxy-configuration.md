The exact location of the directory may vary depending on operating system and installation method. 
In this example, we'll assume the configuration file is located at /etc/nginx/nginx.conf.

## Configuration Process
Install my-project with npm

Script: 

Step One: 
```bash
sudo nano /etc/nginx/nginx.conf
```

Step Two: 
```bash
server {
listen 7443;
    server_name  uat.applicationname.com;
    location / {
        proxy_pass http://localhost:7444/;
        access_log /var/log/nginx/api_logging.log;
        error_log /var/log/nginx/api_error_logging.log;
    }
    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   /usr/share/nginx/html;
    }

# ;     listen 443 ssl; # managed by Certbot
# ;     ssl_certificate /etc/nginx/conf.d/root-ssl-app-net/edesk.cer; # managed by Certbot
# ;     ssl_certificate_key /etc/nginx/conf.d/root-ssl-app-net/edesk.key; # managed by Certbot
# ;     include /etc/nginx/conf.d/root-ssl-edesk-net/options-ssl-nginx.conf; # managed by Certbot
# ;     ssl_dhparam /etc/nginx/conf.d/root-ssl-edesk-net/ssl-dhparams.pem; # managed by Certbot

}
```
