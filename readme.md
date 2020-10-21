# Local HTTPS Nginx Reverse Proxy
This project runs a local Nginx reverse proxy with the [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) image using docker-compose. It proxies to a single Node app running on internal port 8080.

You'll need [Docker](https://www.docker.com/products/docker-desktop) and [mkcert](https://github.com/FiloSottile/mkcert) to make it go - and don't forget to add "127.0.0.1 app.test" to your /etc/hosts file!

```sh
# create a trusted root CA
mkcert -install

# create a cert for app.test
mkcert app.test -cert-file ./certs/app.test.crt -key-file ./certs/app.test.key

# spin up the app
docker-compose up -d

# navigate to https://app.test or run
curl https://app.test
```
