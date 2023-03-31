komutların parametrelerini, kullanımı öğrenmek
```
rm --help, cd --help, touch --help (çoğu komut hakkında bu şekilde bilgi alabilirsin)
```
---
içinde bulunduğun çalışma klasörünü yazdırır.
```
pwd
```
---
içinde bulunduğun dizinin klasör ve dosyalarını listeler
```
ls
```
---
içinde bulunduğun dizinin klasör ve dosyalarını detayları ile listeler (gizli dosyalar dahil)
```
ls -la
```
---
dizin değiştirme
```
cd klasör-adı
```
---
önceki dizine gelme
```
cd ..
```
---
yeni klasör oluşturma
```
mkdir klasör-adı
```
---
yeni dosya oluşturma
```
touch dosya-adı
```
---
dosya silme
```
rm dosya-adı
```
---
dosya silme (zorla sil)
```
rm -f dosya-adı
```
---
klasör silme
```
rm -r klasör-adı
```
---
klasör silme (zorla sil)
```
rm -rf klasör-adı
```
---
dosya okuma
```
cat dosya-adı
```
---
terminali temizleme
```
clear
```
---
terminali kapatma
```
exit
```
---
notes.txt dosyasını test klasörü içine "kopyala" (dizinler farklı ise yol belirtilmeli)
```
cp notes.txt test/notes.txt
```
---
notes.txt dosyasını test2 klasörü içine "taşı"
```
mv notes.txt test2/notes.txt
```
---
root kullanıcıya geçme
```
sudo su (ardından parolanızı soracak)
```
---
klavye dili değiştirme (örnekte türkçe yapıyoruz)
```
setxkbmap tr
```
---
yerel ip bilgilerini verir
```
ifconfig
```
---
parola değiştirme (komuta enter yaptıktan sonra eski şifrenizi, ardından yeni şifrenizi gireceksiniz)
```
passwd 
```
---
ping atmak (ctrl + c durdurur)
```
ping domain-adı
```
---
dosya izinleri ayarlama
```
chattr +i dosya-adi (dosyayı yazılamaz yapar)
chattr -i dosya-adi (dosyayı yazılabilir yapar)
gördüğün gibi i bir parametredir ve eklenip çıkarılabilir.
bunun gibi bir sürü parametre var. chattr --help komutu ile
ayrıntıları öğrenebilirsin
```

