1. vpnbook üzerinden vpnbook dosyalarını indir (bazen bağlantı yapamayabiliriz o yüzden birden fazla vpnbook indirebilirsiniz)
2. indirilen zipi zipten çıkar (sağ tık > extract here) 
3. terminale gel zipten çıkardığın klasörün içine gir (cd)
4. klasörün içinde tcp ve udp bağlantı dosyları (.ovpn) olacak birini seçip
```
openvpn secilen-dosya 
```
- yukarıda ki komutu çalıştırın. Kullanıcı adı ardından paraloyı isteyecek. vpnbook web sitesinden kullanıcı adı ve parolayı edinip buraya girin.
- vpn e bağlanmış olmalısın
---
### bağlanamadıysan şunu dene
nano ile ovpn dosyasını aç
ardından dosyanın en başına
```
tls-cipher "DEFAULT:@SECLEVEL=0"
```
yaz.
bu güvenli bağlantı ile ilgili bir ayar. eğer sorunun gene çözülmedi ise bir googlla derim.