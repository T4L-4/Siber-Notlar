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

### Birden fazla hedefi tarama:

    nmap 10.0.2.5 10.0.2.2 192.168.1.173

    nmap examplesite.com anothersite.com

### Bir ip aralığını tarama:

CIDR gösterimi ile bir aralık tarama (Aşağıdaki örnekte 192.168.1.0 ip adresinden 192.168.1.255 ip adresine kadar taranır.)

    nmap 192.168.1.0/24

Bir aralık belirterek tarama (Aşağıdaki örnekte 192.168.0.1 ip adresinden 192.168.0.25 ip adresine kadar taranır.)

    nmap 192.168.0.1-25
    
### Verilen bir dosyadaki hedefleri taramak için "-iL" parametresi kullanılır.

    nmap -iL targets.txt

### Taramanın hızını belirlemek için "-T" parametresi kullanılır.

T0 en yavaş, T5 en hızlıdır. T5 yapınca hedef sistem sizi banlayabilir.

    nmap 192.168.1.13  -T4

### Sadece TCP portlarını taramak için "-sT" parametresi kullanılır.

    nmap 192.168.1.13 -sT

### Sadece UDP portlarını taramak için "-sU" parametresi kullanılır.

    nmap 192.168.1.13 -sU

### SYN taraması yapmak için "-sS" parametresi kullanılır.

    nmap 10.10.0.2 -sS

### İşletim sistemini (OS) tespit etmek için "-O" parametresi kullanılır.

    nmap 192.168.1.13 -O

### Çalışan servislerin versiyonlarını bulmak için "-sV" parametresi kullanılır.

    nmap 192.168.1.13 -sV

### Sadece belirli portları taramak için "-p" parametresi kullanılır.

Aşağıdaki örnekte port 22'den port 154'e kadar olan tüm TCP portları tarar.

    nmap 192.168.1.13 -p 22-154

Aşağıdaki örnekte port 22'den port 154'e kadar olan tüm UDP portları tarar.

    nmap 192.168.1.13 -p U:22-154

Aşağıdaki örnekte port 22'den port 154'e kadar olan tüm TCP ve UDP portlarını tarar.

    nmap 192.168.1.13 -p U:22-154,T:22-154

### Tüm portları taramak için "-p-" parametresi kullanılır.

65535 portun tamamı taranır.

    nmap 192.168.1.13 -p-

### Agrasif tarama yapmak için "-A" parametresi kullanılır.

OS tespiti, versiyon kontrolü, script taraması'nı kapsar.

    nmap 192.168.1.13 -A

### Script taraması yapmak için "--script" parametresi kullanılır.

Verilen scripti çalıştırır ve scriptin hedef aldığı portlar ile ilgili daha fazla detay çıkartmaya çalışır.

    nmap 192.168.1.13 --script SCRIPT_NAME 

    nmap 192.168.1.13 --script SCRIPT_NAME --script=http-enum.nse 





nmap 192.168.1.13 --script vuln -sC -sV -Pn -sS  //  Zafiyetli portları exploit etmeye çalışır.

nmap 192.168.1.13 -sC <veya> --script default  // Default scriptleri (Yaygın scriptler) çalıştırır.
nmap 192.168.1.13 -oN result.txt  // Sonuçları verilen dosyaya kaydeder.

nmap -sS -sV -sC -Pn -O 192.168.1.13  //  Ping atmadan detaylı tarama, script çalıştırma ve os tespiti






nmap alternatifleri: nessus (Ücretli bir tool) 


---
[ Tools ](../tools.md) | [ Ana Sayfa ](../README.md)
