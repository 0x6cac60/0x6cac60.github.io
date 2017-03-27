---
layout: post
title: Temel Linux Komutları
---





$<strong>mkdir</strong> |dizin oluşturma

$<strong>rmdir</strong> |dizin silme



$<strong>ls</strong> |dosya ve dizin listeleme



$<strong>cd</strong> |çalışma dizinin değiştirme



$<strong>pwd</strong> |çalışma dizinini görüntüleme


$<strong>touch</strong> |dosya erişim zamanını güncelleme



$<strong>rm</strong> |dosya ve dizin silme



$<strong>cp</strong> |dosya ve dizin kopyalama



$<strong>mv</strong> |dosya ve dizin taşıma, isim değiştirme



$<strong>file</strong> |dosya türünü öğrenme



$<strong>find</strong> |dosya ve dizin arama

<br>


### A. Çevrim İçi Klavuz Sayfaları
  
$<strong>man "komut_adı"</strong> | Komutun kılavuz sayfasını çağırma



$<strong>man –K directory, man –K board</strong> | Kılavuz sayfalarında anahtar kelime aratma

<br>

### B. Haberleşme Komutları 

$<strong>wall</strong> |Sisteme bağlı tüm kullanıcılara anlık mesaj göndermek için kullanılır.

$<strong>mesg</strong> |“mesg y” komutu ile mesaj gönderme izni verilir. | “mesg n” komutu ile mesaj alımı kapatılabilir

$<strong>write “write kullanici_adi”</strong> |komutu ile oturum açmış kullanıcıya mesaj gönderilebilir

| “$<strong>write kullanici_adi” </strong>

* komutu ile sisteme o anda giriş yapmış bulunan kullanıcılara
mesaj gönderilebilir. Giriş yapmamış kullanıcılara mesaj göndermek için “mail
kullanici_adi” komutu ile e-posta gönderilebilir.

| “$<strong>write kullanici_adi” </strong>

* komutu verildikten sonra iletilmesi istenen mesaj yazılabilir; mesaj
uygulamasını sonlandırmak için “Ctrl + D” tuş kombinasyonu kullanılabilir. 

<br>

### C. etc/mod

**NOT**: Kullanıcılar oturum açtıklarında görmeleri istenilen duyurular “/etc/motd”
dosyasına yazılmalıdır. motd (ing. Message Of The Day)

* Kullanıcılar oturum açtıklarında “/etc/motd” dosyası görüntülenir. Duyuru mesajlarını
bu dosyaya yazarak sisteme giriş yapan herkesin ilgili mesajı görmesini
sağlayabilirsiniz.

<br>


### D. root

* UNIX sisteminizin en yetkili kullanıcısı “0” kullanıcı numarasına sahip olan
‘root’ tur
* ‘root’ kullanısının UNIX türevi dışındaki işletim sistemlerinde tam bir
karşılığı yoktur
* ‘root’ dışında, ftp, nobody, mail gibi özel tanımlı kullanıcılar da vardır

<br>

### E. Grup ile ilgili komutlar

UNIX’te tüm kullanıcılar en az bir kullanıcı grubunun üyesidirler
* Bilgisayar kaynaklarına grup bazında erişim denetimi de mümkündür
* Grup bilgileri /etc/group dosyasında tutulur
* Grup parolaları /etc/gshadow dosyasında tutulur

$<strong>groupadd</strong> |Yeni bir çalışma gurubu oluşturmak için

$<strong>groupdel</strong> |Mevcut bir bir çalışma grubu silmek için komutları kullanılır.

$<strong>gpasswd </strong>|Bir kullanıcıyı belli bir çalışma grubuna eklemek veya çıkarmak için kullanılır.

$<strong>who</strong> |Sistemde çalışan kullanıcıları, sisteme giriş zamanları ile birlikte listelemektedir.

$<strong>w </strong>|Sistemde çalışan kullanıcıları ve hangi programları çalıştırdıklarını listelemektedir.

$<strong>passwd</strong> |Parola değişikliği için kullanılır.

* Sistemdeki kabuk alternatifleri /etc/shells dosyasında yazılıdır.

* Kabuk değişikliği için chsh komutu kullanılır.


$<strong>finger</strong> |Kullanıcı bilgileri arayıp görüntülenebilir.

$<strong>chfn</strong> |Komutu ile kullanıcı bilgilerini değiştirilebilir.

$<strong>su</strong> |Bir kullanıcının başka bir kullanıcının kimliğine bürünmesini sağlar.

* su (Switch User) – Bir kullanıcının başka bir kullanıcının kimliğine bürünmesini sağlar.
“-” parametresi kullanılırsa belirtilen kullanıcının başlangıç betiklerinin işletilmesi
sağlanır, “-” parametresi kullanılmazsa kullanıcının başlangıç betikleri işletilmez. Su
ile kullanıcı kimliği değiştirildikten sonra exit komutu ile kimlik eski durumuna
döndürülebilir.


$<strong>sudo </strong>|Bir kullanıcının başka bir kullanıcının kimliği ile komut işletmesini sağlar.

$<strong>sudo – </strong> |Bir kullanıcının başka bir kullanıcı kimliği ile bir programı çalıştırmasını sağlar.

* “/etc/sudoers” dosyasındaki yetki tanımlarına uygun olarak kullanıcının programlar
çalıştırabilmesi sağlanır.


#### Erişim yetkilerinin incelenmesi

rwx |(okuma var, yazma var, çalıştırma var)
rw- |(okuma var, yazma var, çalıştırma yok)
r-- |(okuma var, yazma yok, çalıştırma yok)
--- |(okuma yok, yazma yok, çalıştırma yok)
--x |(okuma yok, yazma yok, çalıştırma var)

#### Erişim Yetkilerinin Düzenlenmesi


|$chmod [ugoa][+ – =][rwxst][, ...] dosya/dizin

#### Kim?

 “g” – |grubun (group)
 “a” – |her üçünün de (all)
 “u” – |sahibinin (user)
 “o” – |diğerlerinin (other)

yetkilerinin düzenlenmesi

#### İşleç

 “+” – |söz konusu yetkinin verilmesi
 “–” – |söz konusu yetkinin verilmemesi
 “=” – |sadece söz konusu yetkinin verilmesi

#### Yetki

 “r” – |okuma yetkisi (read)
 “w” – |yazma yetkisi (write)
 “x” – |çalıştırma yetkisi (execute)
 “s” – |sahibi olarak çalıştırma yetkisi (setuid, setgid)
 “t” – |dizine özel yazma yetkisi (sticky)

##### Örnek 

|$<strong>chmod ugo+x dosya.txt </strong>

* Sahibine, gruba ve diğerlerine çalıştırma yetkisi verilmektedir. Son erişim yetkileri “rwxr-xr-x” olmaktadır.

#### Yetkilerin düzenlenmesi (8 tabanı)

chmod sekiz_tabanında_yetki_sayısı dosya
“r” = 4, “w” = 2, “x” = 1, “-” = 0

* Dosyanın erişim yetkilerinin “rw-r-----” olması için yetki sayısının (4+2+0) (4+0+0)
(0+0+0) = 6 4 0 olması gerekir.

Yani şu şekilde de yazılabilir:

|$<strong>chmod 640 dosya</strong>

<br>

### F. Disklerin Yönetilmesi

|$<strong>fdisk</strong>

|$<strong>gparted</strong>

<br>

### G. Dosya Sistemlerinin Bağlanması

$<strong>mount</strong> |Dosya sistemini dizin altına bağlar.

$<strong>umount</strong> |Bağlı olan dosya sistemini ayırır

<br>

### H. Disk Kullanım Bilgileri

|$<strong>df -k</strong>

* df(disk free)-Bağlanmış tüm dosya sistemlerinin doluluk bilgilerini göstermektedir.
Örnekte “-k” seçeneği ile değerlerin KB birimi ile gösterilmesi sağlanmıştır.

* Dosya sistemlerinin kullanım bilgilerini verir.

|$<strong>du -ks</strong>

* du(disk usage)– “-k” seçeneği ile değerlerin KB birimi ile gösterilmesi, “-s” seçeneği
ile de sadece toplam kullanım bilgisinin gösterilmesi sağlanmıştır.

* Bir dizinin kullanım bilgilerini verir.

<br>

### I. Girdi Çıktı Yönlendirme

|$program > dosya 

* Bir programın çıktısını bir dosyaya yönlendirme .

|$program >> dosya 

* Bir program çıktısını mevcut olan bir dosyaya ekleme yaparak
yönlendirme

|$program < dosya 

* Bir programın standart çıktısını başka bir programa standart girdi olarak
yönlendirme

|$program2 > dosya 

* Bir programın standart hata çıktısını bir dosyaya yönlendirme

|$program > dosya 2>&1 

* Bir programın standart çıktısını ve standart hata çıktısını tek bir dosyada
birleştirme













