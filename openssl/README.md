# OpenSSL

## Make a self-signed cert
 + `openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365`

## Make a self-signed cert with no passphrase
  + `openssl req -nodes -new -x509 -keyout server.key -out server.cert`
