<img src="https://github.com/reisoglusoftware/Networking-Projects/blob/main/Statik%20Y%C3%B6nlendirme/Statik%20Y%C3%B6nlendirme.png">
---

# STATİK YÖNLENDİRME

Cisco cihazlarında Statik Yönlendirme (Static Routing), yönlendiricilere (router'lara) belirli ağlara nasıl ulaşacaklarını manuel olarak tanımladığımız bir yönlendirme türüdür. Dinamik yönlendirme protokollerinden farklı olarak, statik yönlendirme değişen ağ koşullarına otomatik olarak uyum sağlamaz; bu nedenle genellikle *küçük ve sabit ağ yapılarında* tercih edilir.


# Statik Yönlendirme Nedir?
Statik yönlendirme, yönlendirme tablosuna manuel olarak girilen, sabit rota bilgileridir. Bu yönlendirme türünde:

Bir ağ yöneticisi, her hedef ağ için hangi çıkış arabiriminin (interface) ya da sonraki yönlendiricinin (next-hop) kullanılacağını açıkça belirtir.

Rotalar değişmediği sürece, router her zaman tanımlı olan yolu kullanır.


# Statik Yönlendirme Avantajları

✅ Kaynak dostudur: CPU ve bellek tüketimi düşüktür.

✅ Güvenlidir: Saldırganların yönlendirme protokollerini manipüle etme riski yoktur.

✅ Öngörülebilirlik sağlar: Trafik akışı sabittir ve kontrol altındadır.


# Statik Yönlendirme Dezavantajları

❌ Yönetimi zordur: Büyük ağlarda yapı karmaşık hale gelir.

❌ Esnek değildir: Bir link arızasında yeni rota öğrenemez.

❌ Bakım maliyeti yüksektir: Her değişiklikte manuel müdahale gerekir.

# Statik Yönlendirme Türleri

|Tür|Açıklama|
|-|-|
|`Doğrudan (Directly Connected)`|Sonraki yönlendirici yerine fiziksel çıkış arayüzü tanımlanır.|
|`İndirekt (Indirect/Next-hop)`|Çıkış arabirimi yerine, bir sonraki yönlendiricinin IP adresi tanımlanır.|
|`Fully Specified Route`|Hem çıkış arabirimi hem de next-hop tanımlanır.|

---

Statik yönlendirmede kayıtlar bir yönetici ( router ) tarafından silinmelidir. Statik yönlendirmede yönlendiricilere lokalde bağlı olmayan ağlar tek tek tanıtılır. Dinamik yönlendirmede böyle bir zorunluluk bulunmamaktadır. 

	Statik yönlendirmede 3 meseleyi göz önünde bulundurmalıyız:
    1. IP paketinin gideceği adres
    2. IP paketinşn gideceği adresin alt ağ maskesi ( subnet mask )
    3. IP paketinin hangi arayüzle ya da IP adresi üzerinden gideceği

---

# SENARYO

### 2 adet farklı konumlardaki yönlendiriciye (router) bağlı cihazların bir birbiri ile iletişimi:

*NOT:* 2811 Routerlerini birbirine bağlayabilmek için ilk önce routera  giden enerjisi kesilir. Ardından boş portlara WIC-2T Modülü eklenir. Ardından routera giden enerji tekrardan açılır.

	1. Routerin ilk bacağının ( ilk ağ ) Network Adresine ait  IP: 192.10.10.0
	1. Routerin ilk bacağıyla 2. Routerin ilk bacağının (ikinci ağ) Network Adresine ait IP: 192.20.20.0
	2. Routerin ikinci bacağı ( üçüncü ağ ) Network Adresine ait IP: 192.30.30.0


### Router0 Yapılandırması

|Komut|Açıklama|
|-|-|
|`enable`|Yönlendiricinin kullanıcı EXEC modundan ayrıcalıklı EXEC moduna geçmesini sağlar. Bu modda daha fazla komuta erişim sağlanır ve cihaz üzerinde değişiklikler yapılabilir.|
|`configure terminal`|Ayrıcalıklı EXEC modundan global yapılandırma moduna geçilmesini sağlar. Bu modda, yönlendiricinin genel ayarları ve arayüz yapılandırmaları gibi global değişiklikler yapılır.|
|`interface FastEthernet 0/0`|FastEthernet0/0 arayüzünü seçmek için kullanılır. Bu arayüz, genellikle yerel ağa (LAN) bağlı olan ilk bacağı temsil eder.|
|`ip address 192.10.10.1 255.255.255.0`|Seçilen FastEthernet0/0 arayüzüne `192.10.10.1` IP adresini ve `255.255.255.0` alt ağ maskesini atar. Bu, ilk ağ `(192.10.10.0/24)` için Router0'ın ağ geçidi IP adresi olacaktır.|
|`no shutdown`|Varsayılan olarak kapalı (administratively down) olan arayüzü etkinleştirir. Bu komut olmadan arayüz çalışmayacaktır.|
|`exit`|Bulunulan arayüz yapılandırma modundan çıkarak bir önceki global yapılandırma moduna geri döner.|
|`interface Serial 0/2/0`|Serial 0/2/0 arayüzünü seçmek için kullanılır. Bu arayüz, genellikle iki yönlendirici arasındaki WAN bağlantısını (ikinci ağ) temsil eder.|
|`ip address 192.20.20.1 255.255.255.0`|Seçilen Serial 0/2/0 arayüzüne `192.20.20.1` IP adresini ve `255.255.255.0` alt ağ maskesini atar. Bu, iki yönlendirici arasındaki bağlantı için Router0'ın IP adresi olacaktır.|
|`no shutdown`|Serial 0/2/0 arayüzünü etkinleştirir.|
|`exit`|Serial 0/2/0 arayüz yapılandırma modundan çıkar.|
|`do write`|Yapılan yapılandırma değişikliklerini geçici bellekten (RAM - running-config) kalıcı belleğe (NVRAM - startup-config) kaydeder. Böylece yönlendirici yeniden başlatıldığında yapılandırmalar kaybolmaz. do öneki, global yapılandırma modunda olmanıza rağmen ayrıcalıklı EXEC moduna ait bir komutu çalıştırmanıza olanak tanır.|

### Router1 Yapılandırması

|Komut|Açıklama|
|-|-|
|`enable`|Router1'i ayrıcalıklı EXEC moduna geçirir.|
|`configure terminal`|Router1'i global yapılandırma moduna geçirir.|
|`interface FastEthernet 0/0`|FastEthernet 0/0 arayüzünü seçer. Bu arayüz, genellikle Router1'in bağlı olduğu üçüncü ağı (LAN) temsil eder.|
|`ip address 192.30.30.1 255.255.255.0`|Seçilen FastEthernet 0/0 arayüzüne `192.30.30.1` IP adresini ve `255.255.255.0` alt ağ maskesini atar. Bu, üçüncü ağ `(192.30.30.0/24)` için Router1'in ağ geçidi IP adresi olacaktır.|
|`no shutdown`|FastEthernet 0/0 arayüzünü etkinleştirir.|
|`exit`|Arayüz yapılandırma modundan çıkar.|
|`interface Serial 0/2/0`|Serial 0/2/0 arayüzünü seçer. Bu arayüz, iki yönlendirici arasındaki WAN bağlantısını (ikinci ağ) temsil eder.|
|`ip address 192.20.20.2 255.255.255.0`|Seçilen Serial 0/2/0 arayüzüne `192.20.20.2` IP adresini ve `255.255.255.0` alt ağ maskesini atar. Bu, iki yönlendirici arasındaki bağlantı için Router1'in IP adresi olacaktır.|
|`no shutdown`|Serial 0/2/0 arayüzünü etkinleştirir.|
|`exit`|Serial 0/2/0 arayüz yapılandırma modundan çıkar.|
|`do write`|Yapılan yapılandırma değişikliklerini kalıcı belleğe kaydeder.|




























