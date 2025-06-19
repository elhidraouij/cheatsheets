# Certificates

## Introduction

### 1. Composition

A certificate is composed of :
- Identity informations, ie `/C=FR/ST=Occitanie/L=Carcassonne/O=Inc/CN=Elhidraouij`
    - `C`  =  Country
    - `ST` =  State
    - `L`  =  Locality
    - `O`  =  Organization
    - `CN` =  Common Name
- Public key, it will be use to verify the signatures
- Validity date
- Serial number, ie `1000`
- Signature algorithm, ie `sha256WithRSAEncryption`
- Signature


The signature correspond of the cyphered hash of the signature content using the private key.
