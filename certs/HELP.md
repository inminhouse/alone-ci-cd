# NOTICE
Generate self signed certificate and private key with the below command
```bash
    $ openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout domain.key -out domain.crt
```
or Add your TLS certificate in this directory.
Name them as domain.crt and domain.key or change the name of files in the docker-compose.yml