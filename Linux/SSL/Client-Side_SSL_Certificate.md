# Client-Side SSL Certificate

## Get Certificate

### Self-signed certificate

#### 1

```sh
openssl req \
	-x509 \
	-nodes \
	-days 365 \
	-newkey rsa:2048 \
	-keyout client.key \
	-out client.crt
```

#### 2

```sh
openssl genrsa -des3 -out server.key 2048
openssl req -new -key server.key -out server.csr
# remove key phrase
cp server.key server.key.orig
openssl rsa -in server.key.orig -out server.key
```



### AWS API Gateway

1. Generate a key (PEM)
2. Setup Nginx

    ```
# Client auth via certs
ssl_client_certificate /etc/nginx/ssl/cert.pem;
ssl_trusted_certificate /etc/nginx/ssl/cert.pem;
ssl_verify_client on;
```

3. se


