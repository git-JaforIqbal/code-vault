    
    ```bash
    server {
        listen 443;
        #ssl on;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
        server_name  clpuat.nccbank.com.bd;

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
      ssl_certificate_key /home/appuser/ssl/star_nccbank_com_bd.key;
      
```
