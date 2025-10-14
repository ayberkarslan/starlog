# 🌟 StarLog - Çok Amaçlı ESP32 Cihazı
### "Cebimde taşıyabileceğim, her durumda kullanabileceğim bir araç yapmak istedim."

**Muhammet Ayberk ARSLAN | STAX TECH | 2025**

---

StarLog, düşük maliyetli ve ergonomik kod ile oluşturulmuş, **Flipper Zero** tarzı çok amaçlı bir cihazdır. Bir İsviçre çakısı gibi tasarlanan StarLog, elektronik, yazılım ve kullanıcı deneyimi dengesini bir araya getirerek her durumda işe yarayabilecek bir araç sunar. Pentesting, otomasyon ve eğlence amaçlı birçok fonksiyonu cebinizde taşıyın.

## ✨ Temel Özellikler

### 1. IR (Kızılötesi) Kumanda Klonlayıcı
Kızılötesi sinyalleri (infrared) alıp kalıcı hafızaya kaydedebilir.
* ∙IR Sinyallerini (infrared-kızılötesi) alıp kalıcı hafızaya kaydetme.
* ∙Kullanıcı tarafından kaydedilen ve çok kullanılan cihazlara (TV, Klima vs) ait hazır IR Sinyallerini IR verici ile hedefe gönderme.
* ∙NEC, RC5, Sony protokollerini destekler.
* ∙50 adede kadar sinyali kaydeder.
* ∙23 popüler TV markası için hazır kodlar.

### 2. WiFi Ağ Tarayıcı
Çevrenizdeki ağlar hakkında bilgi edinmenizi sağlar.
* ∙Çevredeki WiFi ağlarını tarama (ESP 2.4ghz desteği yüzünden sadece 2.4ghz yayın yapan ağlar).
* ∙Gizli ağları bile görüntüler.
* ∙Sinyal gücünü gösterir.
*(Geliştirme aşamasında: İlerleyen zamanlarda deauth ve beacon saldırı özellikleri eklenecek.)*

### 3. Sensör İzleme
* ∙DHT Sensörü ile anlık olarak sıcaklık ve nem bilgilerini ekrana yazdırma.
* ∙Gerçek zamanlı veri gösterimi, her ekranda sürekli görünür durum çubuğu.

### 4. Diğer Araçlar & Kontrol
* ∙Servo motor kontrolü (0-180 derece hassas kontrol).
* ∙Harici 3v'luk Güç Çıkışı.

### 5. Mini Oyunlar
* ∙Küçük Oyunlar (pong, snake, sayı tahmin).

### 6. Özelleştirilebilir Arayüz (EEPROM Entegrasyonu)
Kullanıcı deneyimini kişiselleştirin.
* ∙Cihazın kendine ait bir ayarlar menüsü var. Bu menüden yazı, aydınlatma, DHT renkleri gibi şeyler değiştirilebilir.
* ∙Bu sistem kalıcı bir hafıza elde etmek için EEPROM ile entegre çalışıyor.

---

## 💡 Geleceğe Dair Fikirler (Roadmap)

1.  **Gelişmiş İletişim:** Servo kontrol gibi özellikler iki ESP kartı arası iletişim saplanarak akıllı ev otomasyonu gibi sistemlerler kullanılabilir ya da daha kapsamlı projeler için ESP-Bulut-ESP kurulabilir.
2.  **StarLog İnterneti:** Bu bulut sistemi geliştirilebilir ve ortaya bir "StarLog interneti" çıkabilir. Bu ağ üzerinden cihazlar belirli amaçlar için iletişim kurabilir.
3.  **Acil Durum Bilgi İletimi:** Bu iletişimin kullanılabileceği yerlerden biri acil durumlarda bilgi iletimi olabilir.
4.  **Arayüz Seçenekleri:** Temel bir arayüz yaptım, başka arayüz seçeneğimiz yok ama arayüz seçenekleri eklenip cihaz kullanımı keyifli bir hale getirilebilir.

---

## 📸 Projeden Görseller

Aşağıdaki alana, cihazınızın ve arayüzünüzün fotoğraflarını sırasıyla ekleyebilirsiniz. Lütfen **Drive'dan aldığınız herkese açık bağlantıları** (`<URL_N>`) aşağıdaki HTML formatında sırayla yerlerine yapıştırın.

### ⬇️ Görseller (Sırasıyla)

<p align="center">
  <img src="<URL_1>" alt="Görsel 1" width="400"/>](https://drive.google.com/file/d/1tAzGawHzs0uRezlR6jIiRI45Ymh7ggFn/view?usp=sharing
  <br>
  <img src="<URL_2>" alt="Görsel 2" width="400"/>
  <br>
  <img src="<URL_3>" alt="Görsel 3" width="400"/>
  <br>
  <img src="<URL_4>" alt="Görsel 4" width="400"/>
  <br>
  <img src="<URL_5>" alt="Görsel 5" width="400"/>
  <br>
  <img src="<URL_6>" alt="Görsel 6" width="400"/>
</p>

***

**(Not: Lütfen `<URL_N>` kısımlarını kendi görsel bağlantılarınızla değiştirmeyi unutmayın. Görsellerin yatayda ortalanması için `<p align="center">` etiketi kullanıldı.)**

**Tekrar Hatırlatma:** Google Drive linklerinin doğru çalışması için, linkin doğrudan `.jpg` veya `.png` gibi bir görüntü dosyasına işaret etmesi gerekir. Eğer Drive size bir görüntüleme sayfası linki veriyorsa, resmi direkt olarak GitHub deponuza yükleyip o linkleri kullanmak en garantili yoldur.
