Enable https in Firewall:
```bash
firewall-cmd --permanent --zone=public  --add-service=https
```
Reloade filewall:
```bash
firewall-cmd --reload
```
Nginx config file path in redhat: 
```bash
 /etc/nginx/nginx.conf
```
Edit config and set your ssl certificate file path like mention in step one: 
```bash
 nano /etc/nginx/nginx.conf
```
Upload the certificates on the server where your website is hosted.

Step One: 
```bash
sudo 
    server {
        listen 443;
        #ssl on;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
        server_name  appuat.mysite.com.bd;

        #listen       80 default_server;
        #listen       [::]:80 default_server;
        #server_name  _;
        root         /usr/share/nginx/html;

        # Load configuration files for the default server block.
        include /etc/nginx/default.d/*.conf;

        location / {
        }

        error_page 404 /404.html;
            location = /40x.html {
        }

        error_page 500 502 503 504 /50x.html;
            location = /50x.html {
        }
}
      ssl on;
      ssl_certificate /home/appuser/ssl/file.pem;
      ssl_certificate_key /home/appuser/ssl/star_com.key;
      
```

Step Two:
```bash
 systemctl restart nginx
```



