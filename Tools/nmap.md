# NMAP 

## Nedir ve Ne İçin Kullanılır ?

Nmap (Network Mapper) verilen ağ veya ağları tarar. Verilen ağlardaki açık portarı, portlarda çalışan servisleri, bu servislerin versiyonlarını, eğer bu servislerde bir zaafiyet varsa onu tespit etmemizi ve daha nice işler yapmamızı sağlar.

`Not:` Root olarak çalışmak zorunlu değil ama root önerilir.

## Kurulumu :

    sudo apt install nmap

## Temel Kullanımı :

    nmap TARGET

### Örnek Kullanımları :

### Yalın kullanımı :

    nmap 10.10.0.121

    nmap examplesite.com




nmap 192.168.1.0/24  // Verilen IP aralığı taranır (Cidr gösterimi ile.)
nmap 192.168.0.1-25  // Verilen IP aralığı taranır.
nmap 10.0.2.5 10.0.2.2 192.168.1.173  // Verilen IP'ler taranır.

Parametreli sorgular:
nmap -iL targets.txt  // Verilen dosyadaki IP'ler taranır.
nmap 192.168.1.13  -T4  // T4 hızında tarar (T0 en yavaş, T5 en hızlı, T3 default hızdır.)
nmap 192.168.1.13 -sU -T5  // UDP'ler T5 hızında taranır.
nmap -sU -T5 192.168.1.13  // Yukardakiyle aynı. (Parametrelerin başta veya sonda olması farketmez.)
nmap 192.168.1.13 -sT -T5  // TCP'ler T5 hızında taranır.
nmap 192.168.1.13 -O  // İşletim sistemini (OS) bulmaya çalışır.
nmap 192.168.1.13 -sV // Çalışan servislerin versiyonlarını bulmaya çalışır.
nmap 192.168.1.13 -A // Enables OS detection, version detection, script scanning, and traceroute.
nmap 192.168.1.13 -p 22-154  // Verilen aralıktaki portları tarar.
nmap 192.168.1.13 -p-  // Tüm portları tarar (65535 tane port var.)
nmap 192.168.1.13 --script http-enum.nse <veya> --script=http-enum.nse  // Verilen scripti çalıştırır ve scriptin hedef aldığı portlar ile ilgili daha fazla detay çıkartmaya çalışır.

nmap 192.168.1.13 --script vuln -sC -sV -Pn -sS  //  Zafiyetli portları exploit etmeye çalışır.

nmap 192.168.1.13 -sC <veya> --script default  // Default scriptleri (Yaygın scriptler) çalıştırır.
nmap 192.168.1.13 -oN result.txt  // Sonuçları verilen dosyaya kaydeder.

nmap -sS -sV -sC -Pn -O 192.168.1.13  //  Ping atmadan detaylı tarama, script çalıştırma ve os tespiti


### SYN taraması yapmak için "-sS" parametresi kullanılır.

    nmap 10.10.0.2 -sS




nmap alternatifleri: nessus (Ücretli bir tool) 


---
[ Tools ](../tools.md) | [ Ana Sayfa ](../README.md)
