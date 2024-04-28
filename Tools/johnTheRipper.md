Usage:

    john --wordlist=[path to wordlist] [path to file]

    john --wordlist=[path to wordlist] --format=[format] [path to file]

Basic usage:

    john --wordlist="/usr/share/wordlists/rockyou.txt" hashFile.txt

    john --show hashFile.txt

Bazen format girmen gerekebiliyor.

Formatı kontrol etmek için:

    john --list=formats | grep -iF "md5"

Format ile hash kırmak için

    john --wordlist="/usr/share/wordlists/rockyou.txt" hash1.txt --format=raw-md5

    john --show hash1.txt --format=raw-md5

Some formats:

    ntlm: nt

    md5: raw-md5
    
    sha256: raw-sha256
    
    whirlpool: whirlpool

    sha512crypt: sha512crypt

passwd & shadow: Linux'ta kullanıcı şifrelerini kırmak için passwd ve shadow dosyalarını `unshadow` komutu ile birleştirip sonra kırmanız gerekir:

    unshadow /etc/passwd /etc/shadow > mypasswd.txt 

    john --wordlist="/usr/share/wordlists/rockyou.txt" mypasswd.txt --format=sha512crypt

Kullanıcı adına özel deneme yapılacaksa:

Note: Hash şu formatta olmalı: USER_NAME:HASH

    Ör: Joker:7bf6d9bb82bed1302f331fc6b816aada

    john --single --format=FORMAT HASH_FILE

zip şifre kırma:

    zip2john ZIP_FILE > OUTPUT

    john --wordlist="/usr/share/wordlists/rockyou.txt" OUTPUT

rar:

    rar2john RAR_FILE > OUTPUT

    john --wordlist="/usr/share/wordlists/rockyou.txt" OUTPUT

ssh:

    ssh2john SSH_ID_RSA_FILE > OUTPUT

    john --wordlist="/usr/share/wordlists/rockyou.txt" OUTPUT