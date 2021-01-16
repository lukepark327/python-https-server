# python-https-server
How to create &amp; run https server via python coding

# OpenSSL

## Create Private Key

```
openssl genrsa -des3 -out server.key 2048
```

## Create CSR
```
openssl req -new -key server.key -out server.csr
```

Press Enter to skip.

## Remove Password at Private Key

```
cp server.key server.key.origin
openssl rsa -in server.key.origin -out server.key
```

## Create CRT
```
openssl x509 -req -days 3650 -in server.csr -signkey server.key -out server.crt
```

3650 days = 10 years

# Run HTTPS Server
```
python web.py
```
