# OpenSSL-Essentials
OpenSSL Essentials commands for linux

**Generate a Private Key**

    openssl genrsa -out <private_key_name> <key_length>

**Generate a Private Key and a CSR**

    openssl req -newkey rsa:2048 -nodes -keyout domain.key -out domain.csr

**Generate a CSR from an Existing Private Key**

    openssl req -key domain.key -new -out domain.csr

**Generate a CSR from an Existing Certificate and Private Key**

    openssl x509 -in domain.crt -signkey domain.key -x509toreq -out domain.csr

**Generate a Self-Signed Certificate**

    openssl req -newkey rsa:2048 -nodes -keyout domain.key -x509 -days 365 -out domain.crt

**Generate a Self-Signed Certificate from an Existing Private Key**

    openssl req -key domain.key -new -x509 -days 365 -out domain.crt

**Generate a Self-Signed Certificate from an Existing Private Key and CSR**

    openssl x509 -signkey domain.key -in domain.csr -req -days 365 -out domain.crt

**View Certificate Entries**

    openssl x509 -text -noout -in domain.crt

***Reference***
[1] https://www.digitalocean.com/community/tutorials/openssl-essentials-working-with-ssl-certificates-private-keys-and-csrs
