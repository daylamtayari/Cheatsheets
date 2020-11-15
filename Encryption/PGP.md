# PGP Cheatsheet

## GPG Cheatsheet:
### Generate keys:
```
gpg --full-generate-key
```
### List all your keys:
```
gpg --list-keys
```
### List your secret keys:
```
gpg --list-secret-keys --keyid-format LONG
```
### Export public key:
#### Print public key in ASCII form:
```
gpg --armor --export [Key ID]
```
#### Export public key in ASCII form:
```
gpg --output [filename].asc --armor --export [Key ID]
```
#### Export public key in PGP form:
```
gpg --output [filename].pgp --armor --export [Key ID]
```
### Create revocation certificate:
```
gpg --output [filename].asc --gen-revoke [Key ID]
```