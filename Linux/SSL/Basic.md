# Basic SSL

## Certificate Types

### PEM

> `.pem` stands for PEM, Privacy Enhanced Mail; it simply indicates a base64 encoding with header and footer lines. Mail traditionally only handles text, not binary which most cryptographic data is, so some kind of encoding is required to make the contents part of a mail message itself (rather than an encoded attachment). The contents of the PEM are detailed in the header and footer line - PEM itself doesn't specify a data type (just like XML or HTML doesn't, it just specifies a specific encoding structure);

### KEY

> `.key` can be any kind of key, but usually it is the private key - OpenSSL can wrap private keys for all algorithms (RSA, DSA, EC) in a generic and standard PKCS#8 structure, but it also supports a separate 'legacy' structure for each algorithm, and both are still widely used even though the documentation has marked PKCS#8 as superior for almost 20 years; both can be stored as DER (binary) or PEM encoded, and both PEM and PKCS#8 DER can protect the key with password-based encryption or be left unencrypted;

### CSR

> `.csr` stands for Certificate Signing Request, it is what you send to a third party when you require a certificate to be signed (by a third party), the encoding could be PEM or DER (which is a binary encoding of an ASN.1 specified structure);

### CRT

> `.crt` stands simply for certificate, usually an X509v3 certificate, again the encoding could be PEM or DER; a certificate contains the public key, but it contains much more information (most importantly the signature by the Certificate Authority over the data and public key, of course).


