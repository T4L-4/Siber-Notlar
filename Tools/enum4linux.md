# DIRB

## Nedir ve Ne İçin Kullanılır ?

SMB servislerini enumarate (Bilgi çıkarmak) etmek için kullanılır. Windows'ta smb, linux'ta samba olarak geçer.

## Kurulumu :

    sudo apt install enum4linux

## Temel Kullanımı :

    enum4linux -a TARGET

### Örnek Kullanımları :

### Yalın kullanımı :

    enum4linux examplesite.com

    enum4linux 10.10.24.251

### Kullanıcı adlarını bulmak için "-U" parametresi kullanılır.

    enum4linux -U examplesite.com

### SMB'ye bağlı makineleri bulmak için "-M" parametresi kullanılır.

    enum4linux -M examplesite.com

### İsim listesi bulmak için "-N" parametresi kullanılır. (-U, -M haricinde)

    enum4linux -N examplesite.com

### Sharelist bulmak için "-S" parametresi kullanılır.

    enum4linux -S examplesite.com

### Parola policy hakkında bilgi almak için "-P" parametresi kullanılır.

    enum4linux -P examplesite.com

### Grup ve üye bilgilerini bulmak için "-G" parametresi kullanılır.

    enum4linux -G examplesite.com

### Yukardakilerin hepsini yapmak için "-a" parametresi kullanılır.

    enum4linux -a examplesite.com


---
[ Tools ](../tools.md) | [ Ana Sayfa ](../README.md)
