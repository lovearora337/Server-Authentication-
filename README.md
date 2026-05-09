#############################################################################################

# Server-Authentication-
Creating and setup server authentication 

**ECC/ECDSA certificate (Elliptic Curve Cryptography certificate), not a normal RSA certificate.
ECC certificates are modern SSL/TLS certificates that:**

use smaller keys
provide stronger security
improve TLS handshake performance
are widely used in production systems

**Create ECC Private Key**
Generate ECC private key using OpenSSL:
> openssl ecparam -genkey -name prime256v1 -out server.key

**Verify ECC Key**
> openssl ec -in server.key -text -noout

**Create CSR**
> openssl req -new -key server.key -out server.cs

**Create Self-Signed ECC Certificate**
> openssl x509 -req -days 2 -in server.csr -signkey server.key -out server.crt

###################################################################################################
