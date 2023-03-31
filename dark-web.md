##### tor kaynak ve kütüphanelerini indirme
```
1. apt-get install tor -y (y parametresi gelen sorulara evet işaretle anlamına gelir)
2. tor browser internet sitesine gidip linux sürümünü indirin.
```
#

##### inen dosyayı unzip yapıyoruz (arayüzden sağ tık ile yapabilirsin) ardından tor browser klasörü nereye indi ise (genelde download klasörün de olur) terminalden klasörü açıyoruz. ardından aşağıdaki komutu çalıştırıyoruz
```
./start-tor-browser.desktop  (isim farklı ise düzenlemeleri yapın)
```
#
#### tor root olarak giriş yapmaya izin vermezse...
```
1. tor browser klasörün de, browser klasörü içinde start-tor-browser scriptini bul.
2. bu scripti herhangibir editör ile aç
3. ardından 
if [ "`id -u`" -eq 0 ]; then
	complain "The Tor Browser should not be run as root.  Exiting."
	exit 1
fi
bul shell scriptini bulup dosya içinden sil ve değişikliği kaydet.
4. hala root olarak giremiyorsan boşver normal kullanıcı olarak gir :)
5../start-tor-browser.desktop bu komut ile tor browserı açabiliyor olmalısın.
Bundan sonra hidden wiki yazıp onion uzantılı sitelerde gezebilirsin
```
#