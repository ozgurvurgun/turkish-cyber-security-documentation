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