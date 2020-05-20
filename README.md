traefik reverse proxy configuration
===================================
This repo contains a small example for configuring traefik as a simple reverse proxy.

## checkout
```
git clone git@github.com:binxio/blog-traefik-reverse-proxy-configuration.git
cd blog-traefik-reverse-proxy-configuration
```

## run
```
docker run -d  \
	-p 8080:8080 -p 80:80 \
	-v $PWD/traefik.toml:/etc/traefik/traefik.toml \
	-v $PWD/router.toml:/config/router.toml \
	traefik:v2.0
```

## test
```
curl http://localhost/api/get
curl -X POST --form hello=world http://localhost/api/post
```
