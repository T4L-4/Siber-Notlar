# GOBUSTER

## Nedir ve Ne İçin Kullanılır ?

Gobuster bir web içerik tarayıcısıdır. Hedefte bulunan dosya, dizin, subdomain ve aynı server'daki farklı web sitelerini bulmamıza yarar. 

## Kurulumu :

    sudo apt install gobuster

## Temel Kullanımı :

    gobuster dir -u TARGET -w WORDLIST

    gobuster dns -d TARGET -w WORDLIST

    gobuster vhost -u TARGET -w WORDLIST

<hr>

## "dir" modu

Gobuster bu modu hedef web sitesi altındaki dizinleri ve dosyaları bulmak için kullanır.
    
### Örnek Kullanımları :

### Yalın kullanımı :

    gobuster dir -u http://example.com -w /usr/share/wordlists/dirb/small.txt

### Çıktıyı full path olarak almak için "-e" parametresi kullanılır.

    gobuster dir -e -u 10.10.94.250 -w /usr/share/wordlists/dirb/common.txt

### Hedef web sitesine HTTPS ile bir tarama yapılacaksa "-k" parametresi kullanılır. 

Kullanılmazsa hata verir.

    gobuster dir -u https://example.com -w /usr/share/wordlists/dirb/common.txt -k

### Çıktıda olmasını istediğimiz uzantılar (extensions) için "-x" parametresi kullanılır.

    gobuster dir -u 10.10.94.250 -w /usr/share/wordlists/dirb/common.txt -x txt

    gobuster dir -u 10.10.94.250 -w /usr/share/wordlists/dirb/common.txt -x txt,html,js,php,py,cof,config

### Kaç thread kullanılacağını belirlemek için "-t" parametresi kullanılır. 

Default thread sayısı 10'dur. Sisteminizin limitleri dahilinde artırmanız tavsiye ederim.

    gobuster dir -e -u 10.10.94.250 -w /usr/share/wordlists/dirb/common.txt -t 64

### Çıktıyı kaydetmek için "-o" parametresi kullanılır.

    gobuster dir -u 10.10.94.250 -w /usr/share/wordlists/dirb/common.txt -o ./out.txt

### Taramaya cookie eklemek için "-" parametresi kullanılır.

    gobuster dir -u http://example.com -w /usr/share/wordlists/dirb/small.txt -c COOKIE

### Taramada header kısmına ekleme yapmak için "-H" parametresi kullanılır.

    gobuster dir -u machine_ip_address -w /usr/share/wordlists/dirb/small.txt -H 'Header1: val1'

    gobuster dir -u machine_ip_address -w /usr/share/wordlists/dirb/small.txt -H 'Header1: val1' -H 'Header2: val2'

<hr>

## "dns" modu

Gobuster bu modu hedef web sitesindeki subdomain'leri bulmak için kullanır.

### Örnek Kullanımları :

### Yalın kullanımı :

    gobuster dns -d mydomain.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt

### CNAME kayıtlarını da çıktıda almak için "-c" parametresi kullanılır.

`NOT:` "-i" parametresi ile beraber kullanılamaz.

    gobuster dns -d mydomain.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -c

### Çıktıda IP adreslerini de almak için "-i" parametresi kullanılır.

    gobuster dns -d mydomain.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -i

### İstediğiniz bir DNS sunucusunu kullanmak için "-r" parametresi kullanılır.

    gobuster dns -d mydomain.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -r server.com 

    gobuster dns -d mydomain.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -r server.com:port 

<hr>

## "vhost" modu

Gobuster bu modu hedef web sitesinin içinde bulunduğu sunucudaki diğer web sitelerini bulmak için kullanır.

### Örnek Kullanımları :

### Yalın kullanımı :

    gobuster vhost -u http://example.com -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt


##### Bazı kullanışlı wordlist'ler:

```
/usr/share/wordlists/dirbuster/directory-list-2.3-*.txt

/usr/share/wordlists/dirbuster/directory-list-1.0.txt

/usr/share/wordlists/dirb/big.txt

/usr/share/wordlists/dirb/common.txt

/usr/share/wordlists/dirb/small.txt

/usr/share/wordlists/dirb/extensions_common.txt  /* Useful for when fuzzing for files! */
```

#### Default gelmeyen wordlisteler:

Seclist : `sudo apt install seclists `


---
[ Tools ](../tools.md) | [ Ana Sayfa ](../README.md)
