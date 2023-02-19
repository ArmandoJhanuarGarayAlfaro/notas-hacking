# Retos Bandit

# Level 15 → Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso al nivel
- bandit15
- jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
```bash
bandit14@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 10 11:24:06 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 10 11:24:06 2023 GMT
verify return:1
---
Certificate chain
0 s:CN = localhost
i:CN = localhost
a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
v:NotBefore: Feb 10 11:23:06 2023 GMT; NotAfter: Feb 10 11:24:06
2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEJiAX8TANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjEwMTEyMzA2WhcNMjMwMjEwMTEyNDA2WjAUMRIwEAYD
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| Comando | descripcion |

## Referencias
- []()