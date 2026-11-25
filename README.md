# boz213v01a02-TUBITAK-PROJESI
# DoReFly – Sesinle Uçan Kuş 🐦🎵

**Ortaokul öğrencileri için gerçek zamanlı perde tanımaya dayalı, oyunlaştırılmış solfej eğitim uygulaması.**

Noti adlı kuşu **kendi sesinle** uçurursun: piyano bir nota çalar, sen aynı notayı söylersin ve kuşun yüksekliği sesinin perdesini anında izler. Notayı doğru söyleyip kısa bir süre tutarsan kuş kapıdan geçer.

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-2.x-2ea44f)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)
![TÜBİTAK](https://img.shields.io/badge/T%C3%9CB%C4%B0TAK-2209--A-c8102e)

---

## 🎬 Tanıtım Videosu

[![DoReFly tanıtım videosu](https://img.youtube.com/vi/yehgcbm6N9M/maxresdefault.jpg)](https://youtu.be/yehgcbm6N9M)

▶️ **İzle:** https://youtu.be/yehgcbm6N9M

---

## 📌 Özet

Solfej, müzikal işitme, okuma ve düşünme becerilerinin temelidir. Ancak kalabalık sınıflarda öğretmenin her öğrencinin söyleyişini ayrı ayrı dinleyip anında geri bildirim vermesi güçtür. DoReFly bu boşluğu doldurmak için geliştirildi:

- 🎤 **Gerçek zamanlı perde tanıma:** Mikrofondan gelen sesin perdesi YIN algoritmasıyla hesaplanır. Öğrenci yalnızca doğru ya da yanlış olduğunu değil, **ne kadar pes ya da tiz kaldığını** da görür.
- 🗺️ **Kademeli öğrenme yolu:** Ses Eşleme → Aralık → Nota Okuma → Şarkı. Bir seviye **%80 başarıyla** geçilmeden sonraki açılmaz (tam öğrenme ilkesi).
- 🎼 **Şarkıdan otomatik alıştırma:** Öğretmenin yüklediği bir şarkı (MIDI / MusicXML / metin) analiz edilir. Oyun 1–10 arası bir zorluk puanı hesaplar ve öğrenciyi o şarkıya hazırlayan adım adım alıştırmaları kendisi üretir.
- ⭐ **Oyunlaştırma:** Puan, yıldız, can, jeton, rozet, kostüm ve takma adla haftalık lig.
- 🔒 **Gizlilik öncelikli:** Ses kaydedilmez, gerçek isim sorulmaz, tüm veri yalnızca kendi bilgisayarında kalır.

> Bu proje **TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma Projeleri Destekleme Programı** kapsamında hazırlanmıştır.
> **Proje yürütücüsü:** Kerem Karataş (Ankara Üniversitesi, Bilgisayar ve Öğretim Teknolojileri Öğretmenliği)
> **Danışman:** Öğr. Gör. Nimet Özgül Ünsal

---

## 🖼️ Ekran Görüntüleri

### Macera Haritası
Dört seviye bir harita üzerinde sıralanır. Her seviye bir öncekinin başarıyla tamamlanmasıyla açılır.

![Macera Haritası](docs/ekran_goruntuleri/03_harita.png)

### Oynanış: Aralık Seviyesi
Soldaki renkli cetvel notaları gösterir. Kapıdaki hedef notayı söyleyip tuttuğunda halka dolar ve kuş geçer. `H` tuşu hedef notayı tekrar dinletir.

![Aralık oynanışı](docs/ekran_goruntuleri/12_aralik_oynanis.png)

### Şarkı Stüdyosu
Yüklenen şarkının zorluk puanı, ezgi şekli, cümle sınırları ve zor atlayışları otomatik çıkarılır.

![Şarkı Stüdyosu](docs/ekran_goruntuleri/25_sarki_detay.png)

---

## 🎮 Nasıl Oynanır?

1. **Kulaklık tak.** Hoparlör sesi mikrofona girerse algılayıcı onu senin sesin sanabilir.
2. Piyano hedef notayı çalar, kapı sana doğru yaklaşır.
3. Notayı söyle. **±50 cent** içinde **0,3 saniye** tutarsan kapı açılır.
4. Yanlış notada kuş engele çarpar ve **1 can** kaybedersin (toplam 3 can).
5. Bölüm sonunda doğruluğa göre **1–3 yıldız** kazanırsın. Sonraki aşama için **%80** gerekir.

### Seviyeler

| Seviye | İçerik |
|---|---|
| 1 · Ses Eşleme | Do–Sol, Do–Mi–Sol, Do–Re–Mi, gam, tüm notalar |
| 2 · Aralık | Komşu notalar, üçlü, dörtlü-beşli ve büyük atlayışlar |
| 3 · Nota Okuma | Portedeki nota okunur, nota adı gizlidir |
| 4 · Şarkı | Şarkı Stüdyosu'nda üretilen kademeli yol |

### Kontroller

| Tuş | İşlev |
|---|---|
| Ses (mikrofon) | Kuşu yukarı/aşağı götürür |
| `H` | Hedef notayı tekrar dinle |
| `Esc` / `P` | Duraklat |
| `F11` | Tam ekran |
| `F12` | Ekran görüntüsü al |
| Fare modu: fareyi basılı tut / `1`–`8` | Mikrofon yoksa perde ver |

---

## 🎼 Şarkı Stüdyosu

Kendi şarkını ekle; oyun şarkıyı çözümleyip **sesine uygun** bir hazırlık yolu çıkarır:

1. **Analiz:** Ses aralığı, atlayışlar, yarım tonlar, ritim, tempo, nefes, yön değişimi ve uzunluğa göre **1–10 zorluk puanı** hesaplanır.
2. **Cümlelere bölme** yapılır ve **zor atlayışlar** işaretlenir.
3. **Transpozisyon:** Şarkı, kalibrasyonda ölçülen ses aralığına kaydırılır.
4. **Kademeli yol:** ısınma → zor atlayış alıştırmaları → cümleler → cümle birleştirme → tüm şarkı (%60 / %80 / %100 tempo).

**Desteklenen biçimler:** `.mid` `.midi` `.kar` · `.xml` `.musicxml` `.mxl` · `.txt`

Basit metin biçimi örneği:

```text
# Başlık: Benim şarkım
# Tempo: 100
C4:1 C4:1 G4:1 G4:1 | A4:1 A4:1 G4:2 |
```

Oyunda telif süresi dolmuş 10 halk ve çocuk şarkısı hazır gelir.

---

## 🚀 Kurulum

### Hazır sürüm (Windows)
[Releases](../../releases) sayfasından `DoReFly.exe` dosyasını indirip çalıştır. Python kurmana gerek yoktur.
Windows SmartScreen uyarı verirse **Ek bilgi → Yine de çalıştır** seçeneğine tıkla.

### Kaynak koddan çalıştırma

```bash
git clone <bu-deponun-adresi>
cd DoReFly
pip install -r requirements.txt
python main.py
```

| Komut | Açıklama |
|---|---|
| `python main.py` | Mikrofonla oyna |
| `python main.py --sim` | Mikrofon olmadan fare/klavye ile oyna |
| `python main.py --hepsi-acik` | Test modu: tüm seviyeler açık |

> **Not:** Python 3.15 gibi çok yeni sürümlerde `pygame` hazır paketi bulunmayabilir. Bu durumda `pip install pygame-ce` kullan; kod değişmeden çalışır.
> Linux'ta mikrofon için: `sudo apt install libportaudio2`

### Çalıştırılabilir dosya oluşturma (PyInstaller)

| Platform | Komut | Çıktı |
|---|---|---|
| Windows (klasör) | `build_windows.bat` | `dist\DoReFly\DoReFly.exe` |
| Windows (tek dosya) | `build_windows_tek_dosya.bat` | `dist\DoReFly.exe` |
| macOS | `./build_mac.sh` | `dist/DoReFly.app` |

Paketleme işletim sistemine özeldir: Windows sürümü Windows'ta, Mac sürümü Mac'te derlenir.

---

## 🧠 Teknik Yapı

```text
main.py                   Başlatıcı
doreFly/pitch.py          Perde algılama (YIN), mikrofon / fare kaynakları
doreFly/engine.py         Oyun çekirdeği: kapılar, puan, can, güçlendiriciler
doreFly/levels.py         Seviyeler ve aşama planları
doreFly/songlab/          Şarkı okuyucu, analiz, zorluk puanı, alıştırma yolu
doreFly/profile.py        Profil, ilerleme, mağaza, rozetler
doreFly/leaderboard.py    Haftalık sıralama ve ligler
doreFly/ui/               Ekranlar (menü, harita, oyun, sonuç, şarkılar, ayarlar)
assets/                   Görseller, sesler, müzikler, yazı tipleri
tests/                    pytest testleri
tools/                    Perde algılayıcı ölçüm aracı
```

**Kullanılan teknolojiler:** Python, Pygame, NumPy, sounddevice (PortAudio), PyInstaller

**Testler:**

```bash
pip install pytest
python -m pytest tests -q
```

---

## 🔒 Gizlilik

- Ses **kaydedilmez** ve diske yazılmaz. Yalnızca anlık perde bilgisi hesaplanır.
- Gerçek isim, e-posta veya okul bilgisi istenmez; oyuncular **takma ad** kullanır.
- Tüm veriler yalnızca bu bilgisayarda tutulur, internete hiçbir şey gönderilmez.
- Ayarlar menüsünden oyuncu verileri silinebilir.

---

## 🛣️ Yol Haritası

- [x] Gerçek zamanlı perde tanıma (YIN)
- [x] 4 seviyeli kilitli öğrenme yolu
- [x] Şarkı Stüdyosu: analiz, zorluk puanı, otomatik alıştırma
- [x] Puan, yıldız, can, rozet, mağaza, yerel lig
- [ ] Çevrimiçi lig ve çok oyunculu mod (FastAPI + SQLite)
- [ ] YIN, pYIN ve CREPE algoritmalarının karşılaştırılması
- [ ] Zorluk puanlarının müzik öğretmenlerinin sıralamasıyla doğrulanması
- [ ] Ortaokul öğrencileriyle kullanılabilirlik denemesi

---

## 🤖 Üretken Yapay Zekâ Beyanı

Bu projenin kodu, görselleri, sesleri ve müzikleri üretken yapay zekâ (Claude) yardımıyla geliştirilmiştir. Oyundaki hazır şarkılar telif süresi dolmuş geleneksel ezgilerdir.
