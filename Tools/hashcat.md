Usage:

-m değeri verilmezse hash oto belirlenir ama işlem yapmaz

    hashcat  pass.txt wordlist.txt

Temel kullanım

    hashcat  HASHLER_FILE_PATH WORDLIST_PATH -m HASH_CODE

    hashcat  pass.txt /usr/share/wordlists/rockyou.txt -m 3200  

Hash kırıldıktan sonra aynı kodun sonuna `--show` konulup sonuçlar görülebilir.

    hashcat  pass.txt /usr/share/wordlists/rockyou.txt -m 3200  --show



Note: Salt varsa ve biliniyorsa hash'in en sonuna iki nokta (:) ile yazılır. (Ör: e5d8870e5bdd26602cab8dbe07a942c8669e56d6:tryhackme)

Note: Bazen ise hash'in içinde salt değeri direkt geçer. Ve ayrıca en sona yazılmaz. (Ör:  $6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.)

---
[Tools](../tools.md) | [Ana Sayfa](../README.md)
