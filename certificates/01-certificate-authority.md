# Certificate

## Certificate Authority (CA)

### 1. Files structures

A certificate authority can be structure like this :
```bash
ca/
├── certs/       # emitted known certificates
├── crl/         # revocated certificates
├── newcerts/    # automatically generated certificates
├── private/     # CA private key
├── index.txt    # emitted certificate registry
└── serial       # next certificate number
```

### 2. Create a certificate authority on Debian / Ubuntu based OS

To create a certificate authority :
```bash
mkdir -p ca/{certs,crl,newcerts,private}
chmod 700 ca/private
touch ca/index.txt
touch ca/serial
echo 1000 > ca/serial 
```

To generate a private key :
```bash
openssl genrsa -out ca/private/ca.key.pem 8192
chmod 400 ca/private/ca.key.pem
```

Create an auto-signed certificate :
```bash
openssl req -x509 -new -key ca/private/ca.key.pem \
  -days 3650 -sha256 \
  -out ca/certs/ca.cert.pem \
  -subj "/C=FR/ST=Occitanie/L=Carca/O=Inc/CN=elhidraouij"
```

