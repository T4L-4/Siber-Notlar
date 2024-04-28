Usage:

-W responseu bekler.

-t paralel tret çalıştırır.

http-post-form: the type of the form is POST

<path>: the login page URL, for example, login.php

<login_credentials>: the username and password used to log in, for example, username=^USER^&password=^PASS^

<invalid_response>: part of the response when the login fails

-V: verbose output for every attempt

---

-x MIN:MAX:CHARSET :

    -x 3:5:a  generate passwords from length 3 to 5 with all lowercase letters

    -x 5:8:A1 generate passwords from length 5 to 8 with uppercase and numbers

    -x 1:3:/  generate passwords from length 1 to 3 containing only slashes

    -x 5:5:/%,.-  generate passwords with length 5 which consists only of /%,.-

---

    hydra -l user -P passlist.txt ftp://10.10.151.249

---    

    hydra -l USER_NAME -P /usr/share/wordlists/rockyou.txt ssh://10.10.10.21 -VV

---

    hydra -l root -P passwords.txt ssh://10.10.151.249 -t 4

---   

    sudo hydra <username> <wordlist> MACHINE_IP http-post-form "<path>:<login_credentials>:<invalid_response>" -V

---

    hydra -l <username> -P <wordlist> MACHINE_IP http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V

---
[Tools](../tools.md) | [Ana Sayfa](../README.md)
