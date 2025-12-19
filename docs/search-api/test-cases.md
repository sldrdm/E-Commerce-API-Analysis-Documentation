Hata Başlığı: Geçersiz Arama Sorgusunda API'nin "Harry Potter" Testini Geçememesi ve Yanlış Veri Eşleşmesi. 
ID: BKM-BUG-001 
Ciddiyet (Severity): Medium (Kullanıcı deneyimini etkiliyor).
1. Hata Tanımı: Arama sorgusuna (query) anlamsız/geçersiz bir metin girildiğinde, API hala 200 OK dönmekte ancak dönen ilk ürünün başlığı beklenen "Harry Potter" ifadesini içermemektedir. Sistem, alakasız bir sonucu (Devonu Lugati-t-Türk...) ilk sıraya getirmektedir.
2. Yeniden Üretme Adımları (Steps to Reproduce):
Postman üzerinden https://bkm-best.wawlabs.com/search_v2 adresine gidilir.
search_params içindeki query parametresine geçersiz bir dizi karakter girilir.
İstek gönderilir (Send).
3. Beklenen Sonuç (Expected Result):
Eğer ürün bulunamadıysa total_item_count 0 dönmeli ve res dizisi boş olmalıdır.
Veya API, sorgunun geçersiz olduğuna dair bir uyarı mesajı dönmelidir.
4. Gerçekleşen Sonuç (Actual Result):
API başarıyla cevap vermiş (200 OK) ancak alakasız bir kitabı sonuç listesine eklemiştir.
Yazdığımız Arama sonuçları Harry Potter içeriyor testi, gelen veri "Harry Potter" içermediği için FAILED vermiştir.
5. Kanıt (Evidence):
Görsel: APITEST1.png dosyasındaki "AssertionError: expected 'Devonu Lugati-t-Türk...' to include 'Harry Potter'" hatası.
