# Commands Base Ubuntu

- Thoát chương trình: exit
- Đổi loại RSA private key -> private key
  openssl pkcs8 -topk8 -inform pem -in private_pkcs1.pem -outform pem -nocrypt -out private_pkcs8.pem

Dịch chuyển sites-available -> sites-enable:

**sudo ln -s ../sites-available/be.client.developer-blog.space .**
