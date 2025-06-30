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

Statik yönlendirmede kayıtlar bir yönetici ( router ) tarafından silinmelidir. Statik yönlendirmede yönlendiricilere lokalde bağlı olmayan ağlar tek tek tanıtılır. Dinamik yönlendirmede böyle bir zorunluluk bulunmamaktadır. 

	Statik yönlendirmede 3 meseleyi göz önünde bulundurmalıyız:
    1. IP paketinin gideceği adres
    2. IP paketinşn gideceği adresin alt ağ maskesi ( subnet mask )
    3. IP paketinin hangi arayüzle ya da IP adresi üzerinden gideceği

---

