<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/LAN.png">

# LAN (Local Area Network) Nedir?

LAN, yani Yerel Alan Ağı, sınırlı bir coğrafi alanda (ev, ofis, bina gibi) bulunan cihazların birbirine bağlanarak oluşturduğu ağdır. LAN sayesinde bilgisayarlar, yazıcılar, sunucular gibi cihazlar veri paylaşabilir, dosya transferi yapabilir ve ortak kaynakları kullanabilir.

## LAN Özellikleri:

    1 - Küçük coğrafi alanı kapsar.

    2 - Yüksek veri aktarım hızı (genellikle 100 Mbps – 10 Gbps arası).

    3 - Düşük gecikme (latency).

    4 - Kablolu (Ethernet) veya kablosuz (Wi-Fi) bağlantı olabilir.

    5 - Cihazlar genellikle aynı ağ protokolünü kullanır (çoğunlukla TCP/IP).

## LAN’ın Temel Bileşenleri:

    1 - Switch (Anahtar): Cihazlar arasında veri çerçevelerini yönlendirir.

    2 - Router (Yönlendirici): LAN’ları birbirine veya internete bağlar.

    3 - NIC (Network Interface Card): Her cihazın ağa bağlanmasını sağlar.

    4 - Kablolar: Ethernet kablosu (Cat5e, Cat6), fiber optik kablo vb.

    5 - IP Adresi: Ağdaki cihazların adreslenmesi için gereklidir.

---

## Router0

|Komut|Açıklama|
|-|-|
|`Router0> enable`|Kullanıcı modundan (user EXEC mode) privileged EXEC mode’a geçiş yapar.|
|`Router0# configure terminal`|Privileged EXEC moddan global configuration mode’a geçiş sağlar.|
|`Router0(config)# interface fastEthernet 0/0`|Konfigürasyon modunda, FastEthernet 0/0 arayüzüne girer.|
|`Router0(config-if)# ip address 192.168.10.1 255.255.255.0`|Seçilen arayüze IP adresi ve alt ağ maskesi atanır.|
|`Router0(config-if)# no shutdown`|Arayüzü aktif hale getirir (varsayılan olarak router arayüzleri kapalıdır).|
|`Router0(config-if)# exit`|Arayüz konfigürasyon modundan çıkar, global konfigürasyon moduna geri döner.|
|`Router0(config)# do write`|Yapılan LAN yapılandırmasını kalıcı belleğe kaydeder.|


## Router1

|Komut|Açıklama|
|-|-|
|`Router1> enable`|Kullanıcı modundan (user EXEC mode) privileged EXEC mode’a geçiş yapar.|
|`Router1# configure terminal`|Privileged EXEC moddan global configuration mode’a geçiş sağlar.|
|`Router1(config)# interface fastEthernet 1/0`|Konfigürasyon modunda, FastEthernet 1/0 arayüzüne girer.|
|`Router1(config-if)# ip address 192.168.20.1 255.255.255.0`|Seçilen arayüze IP adresi ve alt ağ maskesi atanır.|
|`Router1(config-if)# no shutdown`|Arayüzü aktif hale getirir (varsayılan olarak router arayüzleri kapalıdır).|
|`Router1(config-if)# exit`|Arayüz konfigürasyon modundan çıkar, global konfigürasyon moduna geri döner.|
|`Router1(config)# do write`|Yapılan LAN yapılandırmasını kalıcı belleğe kaydeder.|


## Router2

|Komut|Açıklama|
|-|-|
|`Router2> enable`|Kullanıcı modundan (user EXEC mode) privileged EXEC mode’a geçiş yapar.|
|`Router2# configure terminal`|Privileged EXEC moddan global configuration mode’a geçiş sağlar.|
|`Router2(config)# interface fastEthernet 2/0`|Konfigürasyon modunda, FastEthernet 2/0 arayüzüne girer.|
|`Router2(config-if)# ip address 192.168.30.1 255.255.255.0`|Seçilen arayüze IP adresi ve alt ağ maskesi atanır.|
|`Router2(config-if)# no shutdown`|Arayüzü aktif hale getirir (varsayılan olarak router arayüzleri kapalıdır).|
|`Router2(config-if)# exit`|Arayüz konfigürasyon modundan çıkar, global konfigürasyon moduna geri döner.|
|`Router2(config)# do write`|Yapılan LAN yapılandırmasını kalıcı belleğe kaydeder.|

## HTTP Server Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/HTTP%20Server%20Settings.png">

## HTTP Server FastEthernet0 Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/HTTP%20Server%20FastEthernet0%20Settings.png">

## HTTP Server Service Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/HTTP%20Server%20Services.png">

## DNS Server Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/DNS%20Server%20Settings.png">

## DNS Server FastEthernet0 Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/DNS%20Server%20FastEthernet0%20Settings.png">

## DNS Server Service Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/DNS%20Server%20Services%20Settings.png">

## DHCP Server Settings 

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/DHCP%20Server%20Settings.png">

## DHCP Server FastEthernet0 Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/DHCP%20Server%20FastEthernet0%20Settings.png">

## DHCP Server Service Settings

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/DHCP%20Server%20Services%20Settings.png">

## Web Page

<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/LAN/Web%20Page.png">
