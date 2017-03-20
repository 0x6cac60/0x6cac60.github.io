---
layout: post
title: Temel Linux Komutları
---




>$mkdir 

* dizin oluşturma

>$rmdir 

* dizin silme

>$ls

* dosya ve dizin listeleme

>$cd

* çalıma dizinin değiştirme

>$pwd

* çalışma dizinini görüntüleme

>$touch

* dosya erişim zamanını güncelleme

>$rm

* dosya ve dizin silme

>$cp

* dosya ve dizin kopyalama

>$mv

* dosya ve dizin taşıma, isim değiştirme

>$file

* dosya türünü öğrenme

>$find

* dosya ve dizin arama

#### Çevrim İçi Klavuz Sayfaları  
>$man <komut_adı>

* Bir komutun kılavuz sayfasını çağırmak için aşağıdaki komut kullanılabilir.

>$man –K directory, man –K board

* Kılavuz sayfalarında anahtar kelime aratma

#### Haberleşme Komutları 

>$wall 

* Sisteme bağlı tüm kullanıcılara anlık mesaj göndermek için kullanılır.

>$mesg 

* “mesg y” komutu ile mesaj gönderme izni verilir.

* “mesg n” komutu ile mesaj alımı kapatılabilir.

>$write 

* “write kullanici_adi” komutu ile oturum açmış kullanıcıya mesaj gönderilebilir.

* “write kullanici_adi” komutu ile sisteme o anda giriş yapmış bulunan kullanıcılara
mesaj gönderilebilir. Giriş yapmamış kullanıcılara mesaj göndermek için “mail
kullanici_adi” komutu ile e-posta gönderilebilir.

* “write kullanici_adi” komutu verildikten sonra iletilmesi istenen mesaj yazılabilir; mesaj
uygulamasını sonlandırmak için “Ctrl + D” tuş kombinasyonu kullanılabilir. 

#### etc/mod

**NOT**: Kullanıcılar oturum açtıklarında görmeleri istenilen duyurular “/etc/motd”
dosyasına yazılmalıdır. motd (ing. Message Of The Day)

* Kullanıcılar oturum açtıklarında “/etc/motd” dosyası görüntülenir. Duyuru mesajlarını
bu dosyaya yazarak sisteme giriş yapan herkesin ilgili mesajı görmesini
sağlayabilirsiniz.



# root

* UNIX sisteminizin en yetkili kullanıcısı “0” kullanıcı numarasına sahip olan
‘root’ tur
* ‘root’ kullanısının UNIX türevi dışındaki işletim sistemlerinde tam bir
karşılığı yoktur
* ‘root’ dışında, ftp, nobody, mail gibi özel tanımlı kullanıcılar da vardır

#### Grup ile ilgili komutlar

UNIX’te tüm kullanıcılar en az bir kullanıcı grubunun üyesidirler
* Bilgisayar kaynaklarına grup bazında erişim denetimi de mümkündür
* Grup bilgileri /etc/group dosyasında tutulur
* Grup parolaları /etc/gshadow dosyasında tutulur

>$groupadd

* Yeni bir çalışma gurubu oluşturmak için

>$groupdel 

* Mevcut bir bir çalışma grubu silmek için komutları kullanılır.

>$gpasswd

* Bir kullanıcıyı belli bir çalışma grubuna eklemek veya çıkarmak için kullanılır.

>$who 

* Sistemde çalışan kullanıcıları, sisteme giriş zamanları ile birlikte listelemektedir.

>$w 

* Sistemde çalışan kullanıcıları ve hangi programları çalıştırdıklarını listelemektedir.

>$passwd 

* Parola değişikliği için kullanılır.

* Sistemdeki kabuk alternatifleri /etc/shells dosyasında yazılıdır.

* Kabuk değişikliği için chsh komutu kullanılır.


>$finger

* Kullanıcı bilgileri arayıp görüntülenebilir.

>$chfn 

* Komutu ile kullanıcı bilgilerini değiştirilebilir.

>$su: Bir kullanıcının başka bir kullanıcının kimliğine bürünmesini sağlar.

* su (Switch User) – Bir kullanıcının başka bir kullanıcının kimliğine bürünmesini sağlar.
“-” parametresi kullanılırsa belirtilen kullanıcının başlangıç betiklerinin işletilmesi
sağlanır, “-” parametresi kullanılmazsa kullanıcının başlangıç betikleri işletilmez. Su
ile kullanıcı kimliği değiştirildikten sonra exit komutu ile kimlik eski durumuna
döndürülebilir.

>$sudo: Bir kullanıcının başka bir kullanıcının kimliği ile komut işletmesini
sağlar.

* sudo – Bir kullanıcının başka bir kullanıcı kimliği ile bir programı çalıştırmasını sağlar.
“/etc/sudoers” dosyasındaki yetki tanımlarına uygun olarak kullanıcının programlar
çalıştırabilmesi sağlanır.

### Erişim yetkilerinin incelenmesi

* rwx (okuma var, yazma var, çalıştırma var)
* rw- (okuma var, yazma var, çalıştırma yok)
* r-- (okuma var, yazma yok, çalıştırma yok)
* --- (okuma yok, yazma yok, çalıştırma yok)
* --x (okuma yok, yazma yok, çalıştırma var)

### Erişim Yetkilerinin Düzenlenmesi


>$chmod [ugoa][+ – =][rwxst][, ...] dosya/dizin

#### Kim?

* “g” – grubun (group)
* “a” – her üçünün de (all)
* “u” – sahibinin (user)
* “o” – diğerlerinin (other)
yetkilerinin düzenlenmesi

#### İşleç

* “+” – söz konusu yetkinin verilmesi
* “–” – söz konusu yetkinin verilmemesi
* “=” – sadece söz konusu yetkinin verilmesi

#### Yetki

* “r” – okuma yetkisi (read)
* “w” – yazma yetkisi (write)
* “x” – çalıştırma yetkisi (execute)
* “s” – sahibi olarak çalıştırma yetkisi (setuid, setgid)
* “t” – dizine özel yazma yetkisi (sticky)

#### Örnek 

>$chmod ugo+x dosya.txt 
* Sahibine, gruba ve diğerlerine çalıştırma yetkisi verilmektedir. Son erişim yetkileri “rwxr-xr-x” olmaktadır.

#### Yetkilerin düzenlenmesi (8 tabanı)

* chmod sekiz_tabanında_yetki_sayısı dosya
“r” = 4, “w” = 2, “x” = 1, “-” = 0

* Dosyanın erişim yetkilerinin “rw-r-----” olması için yetki sayısının (4+2+0) (4+0+0)
(0+0+0) = 6 4 0 olması gerekir.

Yani şu şekilde de yazılabilir:

>$chmod 640 dosya

#### Disklerin Yönetilmesi

>$fdisk

>$gparted

#### Dosya Sistemlerinin Bağlanması

>$mount 

* Dosya sistemini dizin altına bağlar.

>$umount 

* Bağlı olan dosya sistemini ayırır

#### Disk Kullanım Bilgileri

>$df -k

* df(disk free)-Bağlanmış tüm dosya sistemlerinin doluluk bilgilerini göstermektedir.
Örnekte “-k” seçeneği ile değerlerin KB birimi ile gösterilmesi sağlanmıştır.

* Dosya sistemlerinin kullanım bilgilerini verir.

>$du -ks

* du(disk usage)– “-k” seçeneği ile değerlerin KB birimi ile gösterilmesi, “-s” seçeneği
ile de sadece toplam kullanım bilgisinin gösterilmesi sağlanmıştır.

* Bir dizinin kullanım bilgilerini verir.

#### Girdi Çıktı Yönlendirme

>$program > dosya

* Bir programın çıktısını bir dosyaya yönlendirme .

>$program >> dosya


* Bir program çıktısını mevcut olan bir dosyaya ekleme yaparak
yönlendirme

>$program < dosya


* Bir programın standart çıktısını başka bir programa standart girdi olarak
yönlendirme

>$program2 > dosya

* Bir programın standart hata çıktısını bir dosyaya yönlendirme

>$program > dosya 2>&1

* Bir programın standart çıktısını ve standart hata çıktısını tek bir dosyada
birleştirme













