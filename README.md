LOJİK DEVRE TASARIMI

DÖNEM PROJESİ 

**Tanım** 

Bir ana caddenin trafik akışını ekonomik ve hızlı bir şekilde çözebilmek için akıllı trafik sistemi  uygulanması  istenmektedir.  Akıllı  trafik  ışıklarının  uygulanacağı  bu  caddenin planı aşağıdaki şekilde verilmiştir. 

![](Aspose.Words.689fe6ac-d3e7-465e-ac36-bb32b73dfef1.001.png)

**Şekil 1:** Üç Trafik Işıklı Cadde Planı 

**Sistem Özellikleri** 

Bu trafik sisteminde üç adet trafik ışık sinyali bulunmaktadır. Bunlar sırasıyla planda **A1**, **A2**, **A3** olarak adlandırılmıştır. Her bir trafik ışığı kendi içerisinde **KIRMIZI**, **SARI** ve **YEŞİL** ışık arasında sürekli bir döngü içerisinde yanmaktadır. Her bir trafik ışığının geçişlerini bir durum olarak belirtirsek, bu cadde için aşağıda belirtilen 7 farklı duruma oluşmuştur; 

- **DURUM 1:** **YOL1**’den gelen araç ya düz gidebilir ya da sola dönebilir (**A1**=**YEŞİL**, **A2**=**KIRMIZI**, **A3**=**KIRMIZI**)
- **DURUM 2:** **YOL2**’den gelen araç ya düz gidebilir ya da sola dönebilir (**A1**=**KIRMIZI**, **A2**=**YEŞİL**, **A3**=**KIRMIZI**)
- **DURUM 3:** **YOL3**’den gelen araç ya düz gidebilir ya da sola dönebilir (**A1**=**KIRMIZI**, **A2**=**KIRMIZI**, **A3**=**YEŞİL**)
- **DURUM 4:** **DURUM 1**‘in hazırlık durumuna geçmesi (**A1**=**SARI**, **A2**=**KIRMIZI**, **A3**=**KIRMIZI**)
- **DURUM 5:** **DURUM 2**‘nin hazırlık durumuna geçmesi (**A1**=**KIRMIZI**, **A2**=**SARI**, **A3**=**KIRMIZI**)
- **DURUM 6:** **DURUM 3**‘ün hazırlık durumuna geçmesi (**A1**=**KIRMIZI**, **A2**=**KIRMIZI**, **A3**=**SARI**)
- **DURUM 7:** Hiç bir yoldan aracın gelmemesi veya yolun boş olması (**TÜM IŞIKLAR** **KIRMIZI**)

**KONTROL DEVRESİ VE SENSÖRLER** 

Bu üç trafik ışığının birbirleriyle eşzamanlı bir şekilde değişmesini yani durumlar arasındaki geçişlerin nasıl yapılacağını **YOL1**, **YOL2** ve **YOL3** üzerindeki sensörler ve trafik kontrol devresi belirlemektedir. Her bir yol için sırasıyla **X1**, **X2** ve **X3** sensörleri bulunmaktadır. Kontrol devresi sensörlerden aldığı bilgiyi aşağıdaki tabloya göre işlemekte ve sistemin çalışmasını sağlamaktadır. 



|**X3 X2 X1** |**TRAFİK DURUMU** |**OPERASYON** |
| - | - | - |
|000 |Tüm yollar boş, trafik yok |**DURUM** 7’de kal |
|001 |Sadece YOL 1 trafik var |**DURUM** 1’de kal |
|010 |Sadece YOL 2 trafik var |**DURUM** 2’de kal |
|100 |Sadece YOL 3 trafik var |**DURUM** 3’de kal |
|011 |YOL 1 ve YOL 2 trafik var |**DURUM**: 1-4-2-5-1-4… DÖNDÜR |
|101 |YOL 1 ve YOL 3 trafik var |**DURUM**: 1-4-3-6-1-4… DÖNDÜR |
|110 |YOL 2 ve YOL 3 trafik var |**DURUM**: 2-5-3-6-2-5… DÖNDÜR |
|111 |Tüm yollarda trafik var |**DURUM**: 1-4-2-5-3-6-1-4… DÖNDÜR |
**Tasarım ipucu:** 

- Sensörleri X3-X2-X1 giriş (3 input), Kırmızı-Sarı-Yeşil ışıkları çıktı olarak düşünmelisiniz.  Her  bir  trafik  ışığının  Kırmızı-Sarı-Yeşil  sinyallerinin olduğu düşünüldüğünde toplamda 3x3 = 9 output oluşacaktır.
- Durum geçişleri girişlerle değişecektir. Çıktılar ise sadece bulunduğu durumlarda oluştuğu için Moore modeli kullanılmalıdır.

**Yukarıda verilen bilgiler ışığında sistemin;** 

- Durum Diyagramı
- Durum  Tablosu  (Flip-Flop  seçimi  size  aittir  herhangi  birini kullanabilirsiniz)
- Karnough Sadeleştirmeleri
- Devre Çizimi
- Logisim Simülasyonu

Yapılacaktır. Detaylar diğer sayfada anlatılmıştır. 

**RAPOR DÜZENİ VE İSTENİLENLER** 

1. **Sistemin Durum Diyagramı** 
- Durum geçişleri, girdiler, çıktılar açıkça diyagramda belirtilmelidir. Okunabilir olmalıdır.
2. **Durum Tablosu (Flip- Flop Seçimleri size aittir, herhangi bir   flip-flop çeşidi kullanılabilir.)** 
- **Tablo çizimi manuel yapılacaktır.**     Tüm adımlar mutlaka olmalıdır. Okunabilir şekilde fotoğraflanıp rapora eklenecektir.
3. **Denklemler ve Sadeleştirme İşlemleri** 
- Tüm adımlar mutlaka olmalıdır. Sadeleştirmeler için girdi sayısı 5’e kadar Karnough, 6 ve üzeri inputlar için Tablo yöntemi kullanılabilir. Sadeleştirme seçimlerinde yapılan çizimler karışık olmamalı, okunabilir şekilde fotoğraflanıp rapora eklenmelidir.
4. **Devre Çizimi (El ile veya diyagram yazılımlarıyla çizilebilir.)** 
- El ile yapılan çizimler fotoğraflanarak rapora eklenecektir.
- Diyagram çizim yazılımıyla yapılan çizimler yazılımdan export edilerek (tüm ekranın çıktısını almayın) rapora eklenecektir.
5. **Logisim simülasyon tasarımı**
- Tasarlanan devre Logisimde uygulanarak simülasyonu yapılacaktır. Logisim içerisinde sistemin nasıl çalıştığını anlatan açıklamalar mutlaka olmalıdır.
- Devrenin genel görünüşü logisimden export edilerek rapora eklenecektir.
4 
