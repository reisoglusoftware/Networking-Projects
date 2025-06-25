<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/RIP%20(Routing%20Information%20Protocol)/RIP.png">

# RIP (Routing Information Protocol) Nedir?

* RIP, en eski mesafe vektör yönlendirme protokollerinden biridir.

* Maksimum atlama sayısı (hop count) 15'tir – bu da 16 olduğunda ağ ulaşılamaz olarak değerlendirilir.

* Varsayılan olarak 30 saniyede bir routing tablosunu gönderir.

* En kısa yol, atlama sayısına (hop sayısı) göre belirlenir.

* RIP’in iki sürümü vardır:

* * RIPv1: Sınıfsal, subnet bilgisi taşımaz.

* * RIPv2: Sınıfsızdır, subnet ve yönlendirme bilgilerini taşır. Multicast kullanır (224.0.0.9).

---

## CLI Kodları
|-|
|q|

* `Router> enable`					                    | Yetkili moda geçmek için kullanılır.
* `Router# configure terminal`		            	| Global yapılandırma moduna girilir.
* `Router(config)# router rip`		            	| RIP yönlendirme protokolü başlatılır.
* `Router(config-router)# version 2`	        	| RIP'in 2. sürümü kullanılır. Bu sürüm subnet bilgisi ile çalışır.
* `Router(config-router)# network 192.10.10.0`	| Bu komutla, 192.10.10.0/24 ağı RIP’e dahil edilir.
* `Router(config-router)# network 192.20.20.0`	| Yönlendiriciye bağlı olan 192.20.20.0/24 ağı da dahil edilir.
* `Router(config-router)# no auto-summary`	  	| Sınıf temelli ağ özetlemesini devre dışı bırakır. Farklı subnetlerin daha doğru öğrenilmesini sağlar.
* `Router(config-router)# exit`		            	| >
* `Router(config)# exit`			                	| >
* `Router# write memory`			                	| > Yapılandırmalar kaydedilir.

---

## RIP Doğrulama Komutları

Tüm yönlendirme tablosunu görmek için:
* `Router# show ip route`

RIP komşularını ve gönderilen/alınan rotaları görmek için:
* `Router# show ip protocols`

Arayüzün RIP mesajı gönderip alıp almadığını kontrol etmek için:
* `Router# debug ip rip`














