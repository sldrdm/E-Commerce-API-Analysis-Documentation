📚 E-Commerce Technical Analysis & API Testing Suite (BKM Kitap Case Study)

Bu proje, bir e-ticaret platformunun (BKM Kitap) arama altyapısını Tersine Mühendislik (Reverse Engineering) yöntemleriyle analiz etmek, sistem mimarisini modellemek ve API uç noktalarını otomatik test scriptleri ile doğrulamak amacıyla hazırlanmış bir Teknik İş Analizi çalışmasıdır.

🎯 Proje Hedefleri

Canlı bir sistemin API trafik analizini yaparak veri haritasını (Data Mapping) çıkarmak.

Sistem bileşenleri arasındaki iletişimi Sequence Diagram ile görselleştirmek.

Postman kullanarak fonksiyonel ve performans odaklı API testleri gerçekleştirmek.

Tespit edilen uç vakaları (edge cases) profesyonel bir Bug Report formatında raporlamak.

🏗 Sistem Mimarisi & Akış Şeması

Sistemin çalışma mantığı, kullanıcı sorgusundan başlayıp CDN üzerinden görsel sunumuna kadar aşağıdaki Sequence Diagram (Miro) üzerinde modellenmiştir:

![searchApıSequenceDiagram](https://github.com/user-attachments/assets/7eed2c7f-f68a-48af-b3a9-7da751a99a57)


🧪 API Test Stratejisi & Test Case'ler

Postman üzerinde JavaScript kullanılarak hazırlanan test suite, her istekte aşağıdaki senaryoları otomatik olarak doğrulamaktadır:

Test ID,Senaryo Adı,Kontrol Noktası,Beklenen Sonuç,Durum

TC01,System Availability,HTTP Status Code,200 OK,✅ PASS

TC02,Latency Check,Response Time,< 800ms,✅ PASS

TC03,Data Integrity,Property Check,stock_level mevcut mu?,✅ PASS

TC04,Content Accuracy,Business Logic,"Başlık ""Harry Potter"" içeriyor mu?",✅ PASS

<img width="1918" height="1022" alt="APITEST1" src="https://github.com/user-attachments/assets/eb7c5c82-fc73-42f8-8320-2ff7c468f78f" />

🐞 Tespit Edilen İyileştirme Alanları (Bug Report)
Analiz sırasında sistemin negatif senaryolardaki tepkisi ölçülmüştür:

Bulgu: Geçersiz arama sorgularında (örn: anlamsız karakter dizileri)

API 200 OK dönmekte ancak içerik olarak alakasız veriler listelenmektedir.

Öneri: Bu tür durumlarda API'nin boş bir dizi dönmesi veya UI tarafında "Sonuç Bulunamadı" sayfasını tetikleyecek bir hata kodu (örn: 404 veya özel bir flag) dönmesi kullanıcı deneyimini iyileştirecektir.

🛠 Kullanılan Araçlar

Postman: API Request simülasyonu ve Otomatik Test Scriptleri.

Miro: Sistem mimarisi görselleştirme.

DevTools: Network trafiği ve API keşfi.

Markdown: Teknik dokümantasyon.

