# Commands Base Ubuntu

- Thoát chương trình: exit
- Đổi loại RSA private key -> private key
  openssl pkcs8 -topk8 -inform pem -in private_pkcs1.pem -outform pem -nocrypt -out private_pkcs8.pem

Dịch chuyển sites-available -> sites-enable:

**sudo ln -s ../sites-available/be.client.developer-blog.space .**

Config Nginx:


server {

    listen 80;

    listen [::]:80;

  server_name developer-blog.space;

  location / {

    proxy_pass                          http://localhost:4444;

    proxy_set_header  Host              $http_host;   # required for docker client's sake

    proxy_set_header  X-Real-IP         $remote_addr; # pass on real client's IP

    proxy_set_header  X-Forwarded-For   $proxy_add_x_forwarded_for;

    proxy_set_header  X-Forwarded-Proto $scheme;

    proxy_read_timeout                  900;

  }

}

sudo ln -s /etc/nginx/sites-available/developer-blog.space /etc/nginx/sites-enabled/

sudo ln -s /etc/nginx/sites-available/registry.developer-blog.space /etc/nginx/sites-enabled/

sudo ln -s /etc/nginx/sites-available/be.admin.developer-blog.space /etc/nginx/sites-enabled/

sudo ln -s /etc/nginx/sites-available/be.client.developer-blog.space /etc/nginx/sites-enabled/

sudo ln -s /etc/nginx/sites-available/admin.developer-blog.space /etc/nginx/sites-enabled/
