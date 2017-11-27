# OpenSSL

## Make a self-signed cert
 + `openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365`

## Make a self-signed cert with no passphrase
  + `openssl req -nodes -new -x509 -keyout server.key -out server.cert`

## Make a self-signed cert with no passphrase or prompts
  + `openssl req -x509 -newkey rsa:4096 -days 365 -nodes -out public.pem -keyout private.pem -subj "/C=US/ST=Missouri/L=St. Louis/O=SomeOrg/CN=Some great organization"`