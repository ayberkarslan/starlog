
/* Muhammet Ayberk ARSLAN | STAX TECH | 2025
<--StarLog--> Çok Fonksiyonlu Amatör Mobil Pentest Cihazı
ÖZELLİKLER: ∙IR Sinyallerini (infrared-kızılötesi) alıp kalıcı hafızaya kaydetme ∙Kullanıcı tarafından kaydedilen ve çok kullanılan cihazlara (TV,Klima vs) ait hazır IR Sinyallerini IR verici ile hedefe gönderme ∙Çevredeki WiFi ağlarını tarama (ESP 2.4ghz desteği yüzünden sadece 2.4ghz yayın yapan ağlar)(ilerleyen zamanlarda deauth ve beacon saldırı özellikleri eklenecek) ∙Diğer Araçlar menüsünden --> Servo motor kontrolü, harici 3v'luk Güç Çıkışı, Küçük Oyunlar (pong, snake, sayı tahmin) ∙DHT Sensörü ile anlık olarak sıcaklık ve nem bilgilerini ekrana yazdırma ∙Cihazın kendine ait bir ayarlar menüsü var. Bu menüden yazı, aydınlatma, DHT renkleri gibi şeyler değiştirilebilir. Bu sistem kalıcı bir hafıza elde etmek için eeprom ile entegre çalışıyor.
Geleceğe dair fikirler: ∙Servo kontrol gibi özellikler iki ESP kartı arası iletişim saplanarak akıllı ev otomasyonu gibi sistemlerler kullanılabilir ya da daha kapsamlı projeler için ESP-Bulut-ESP kurulabilir. ∙ Bu bulut sistemi geliştirilebilir ve ortaya bir "StarLog interneti" çıkabilir. Bu ağ üzerinden cihazlar belirli amaçlar için iletişim kurabilir. ∙ Bu iletişimin kullanılabileceği yerlerden biri acil durumlarda bilgi iletimi olabilir. Bu tarz küçük ve kolay iletilebilen veriler bu gibi acil durumlarda yararlı olabilir. ∙ Temel bir arayüz yaptım, başka arayüz seçeneğimiz yok ama arayüz seçenekleri eklenip cihaz kullanımı keyifli bir hale getirilebilir. ∙

Flipper Zero tarzı pentesting ve eğlence amaçlı kullanılan cihazlardan birini en az maliyet ve en ergonomik kodla oluşturmak istedim. Ortaya StarLog ismini verdiğim bir toolbox çıktı. Çok amaçlı bir cihaz. Henüz tam olarak ...... cihazı gibi bir ayrıma sahip olamayacak kadar farklı yönler var ancak ilerleyen zamanlarda pentest cihazı kısmına yöneleceğim (Deauther tarzı ağ test saldırıları üzerinde çalışıyorum) Programın kendi içerisinde olabildiğince kompakt olmasını ve yeni fonksiyonlar eklenmeye açık bir halde olmasını istediğim için çok fazla planlama yaptım ve ortaya yazdığım en düzenli programlardan biri çıktı. Çok fazla dış kaynaktan yardım aldım, sayısız site ziyaret ettim ve kod örneği inceledim, özellikle menü ve offset sistemleri için çünkü ilk defa yaptığım bir şeydi. Sensörler arasında da ilk defa kullandığım sensörler var (IR alıcı-verici sensörleri) ki projeyi aslında IR Sinyallerinin temelini anlamak ve bunları kullanmak için tasarladım. Tabii ki satırlar arasında sinyallerin ayrıntılı fiziksel açıklaması yok, bu dosyayı olabildiğince sade tutmak istedim.

*/

StarLog - Çok Amaçlı ESP32 Cihazı "Cebimde taşıyabileceğim, her durumda kullanabileceğim bir araç yapmak istedim." StarLog bir İsviçre çakısı gibi - her durumda işe yarayabilecek, cebimde taşıyabileceğim bir araç. WiFi ağlarını tarayabilen, sensör verileri okuyabilen, servo motorları kontrol edebilen ve hatta oyun oynayabileceğim bir platform.Bu proje benim için sadece bir kod yığını değil - elektronik, yazılım ve kullanıcı deneyimi arasındaki dengeyi öğrenme sürecim.

Temel Özellikler1: IR Kumanda Klonlayıcı TV, klima, ses sistemi kumandalarını kopyalar 50 adede kadar sinyali kaydeder 23 popüler TV markası için hazır kodlar (Samsung, LG, Sony, Vestel...) NEC, RC5, Sony protokollerini destekler

    WiFi Ağ Tarayıcı

Çevredeki tüm WiFi ağlarını listeler Gizli ağları bile görüntüler Sinyal gücünü gösterir Kaydırılabilir liste ile rahat gezinti

    Sensör İzleme

DHT11 ile sıcaklık ve nem ölçümü Gerçek zamanlı veri gösterimi Her ekranda sürekli görünür durum çubuğu

    Servo Motor Kontrolü

0-180 derece hassas kontrol Perde açma, kapı kilidi gibi projelerde kullanılabilir 10'ar derece artışlarla ayarlanabilir

    Mini Oyunlar

Snake: Klasik yılan oyunu Pong: Tek kişilik top oyunu Sayı Tahmin: Tahmin oyunu

    Özelleştirilebilir Arayüz

Vurgu, başlık ve sensör renklerini değiştir 10 farklı renk seçeneği Tüm ayarlar EEPROM'a kaydedilir (kalıcı)


<br>
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/1.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/2.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/3.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/4.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/5.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/6.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/7.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/8.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/9.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/10.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/11.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/12.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/13.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/14.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/15.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/16.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/17.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/18.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/19.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/20.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/21.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/22.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/23.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/24.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/25.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/26.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/27.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/28.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/29.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/30.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/31.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/32.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/33.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/34.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/35.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/36.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/37.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/38.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/39.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/40.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/41.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/42.jpg" width="400" alt="text">
<img src="https://raw.githubusercontent.com/ayberkarslan/starlog/refs/heads/main/images/43.jpg" width="400" alt="text">
