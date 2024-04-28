# DIRB

## Nedir ve Ne İçin Kullanılır ?

Dirb bir web içerik tarayıcısıdır. Hedef web adresinde bulunan dosya ve dizinleri bulmamıza yarar. 

## Kurulumu :

Dirb Kali Linux'ta yüklü olarak gelmektedir.

Eğer sisteminizde yüklü değilse :

    sudo apt install dirb

komutu ile yükleyebilirsiniz.

## Temel Kullanımı :

    dirb TARGET

### Örnek Kullanımları :

### Yalın kullanımı :

    dirb http://examplesite.com

### Belirli bir port ile kullanımı :

    dirb http://examplesite.com:8080

### Wordlist ile kullanımı :

    dirb http://192.168.1.224 /usr/share/wordlists/dirb/common.txt

    dirb https://webscan.com /usr/share/dirb/wordlists/big.txt

    dirb https://webscan.com /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

`NOT:` Wordlist hedef adres'ten (TARGET) hemen sonra gelmelidir. Araya her hangi bir parametre girmemelidir.

### Çıktıyı kaydetmek için "-o" parametresi kullanılır.

    dirb http://examplesite.com -o result.txt

    dirb http://10.10.12.123 -o result.txt

    dirb http://examplesite.com -o /home/myuser/result.txt

### Çıktıda olmasını istediğimiz uzantılar (extensions) için "-X" parametresi kullanılır.

    dirb http://example.com -X .php

    dirb http://10.10.12.123 -X .php,.html,.js


---
[ Tools ](../tools.md) | [ Ana Sayfa ](../README.md)
