-- 1. Tüm öğrenci verilerini getir
SELECT * 
FROM ogrenciler;  -- 'ogrenciler.csv' dosyasından aktarılan tablo

-- 2. Ortalama notu 80 ve üzeri olan öğrencileri getir
SELECT * 
FROM ogrenciler 
WHERE ortalama >= 80;  -- filtreleme koşulu

-- 3. Sadece 'Kadın' öğrencileri getir
SELECT * 
FROM ogrenciler 
WHERE cinsiyet = 'Kadın';

-- 4. Sadece 'Erkek' öğrencileri getir
SELECT * 
FROM ogrenciler 
WHERE cinsiyet = 'Erkek';

-- 5. En yüksek ortalama notuna sahip öğrenciden en düşüğe doğru sırala
SELECT * 
FROM ogrenciler 
ORDER BY ortalama DESC;

-- 6. En düşük ortalamaya sahip 5 öğrenciyi getir
SELECT * 
FROM ogrenciler 
ORDER BY ortalama ASC  -- artan şekilde sırala
LIMIT 5;               -- ilk 5 kaydı getir

-- 7. Öğrencilerin sadece adı, cinsiyeti ve ortalamasını listele
SELECT ad_soyad, cinsiyet, ortalama 
FROM ogrenciler;

-- 8. Cinsiyete göre gruplandır ve her grubun ortalamasını hesapla
SELECT cinsiyet, 
       ROUND(AVG(ortalama), 2) AS cinsiyet_ortalamasi 
FROM ogrenciler 
GROUP BY cinsiyet;

-- 9. Öğrencileri ortalamaya göre sırala, başarı listesi oluştur
SELECT * 
FROM ogrenciler 
ORDER BY ortalama DESC;

-- 10. Matematik notu 90'dan büyük olan öğrencileri listele
SELECT * 
FROM ogrenciler 
WHERE matematik > 90;

-- 11. Kimya ve fizik notu 80 ve üstü olan öğrencileri getir
SELECT * 
FROM ogrenciler 
WHERE kimya >= 80 AND fizik >= 80;

-- 12. Ortalama notu en yüksek olan ilk öğrenciyi getir
SELECT * 
FROM ogrenciler 
ORDER BY ortalama DESC 
LIMIT 1;

-- 13. Öğrencilerin sadece isimlerini ve başarı durumunu göster
SELECT ad_soyad, 
       CASE 
         WHEN ortalama >= 85 THEN 'Çok Başarılı'
         WHEN ortalama >= 70 THEN 'Başarılı'
         ELSE 'Gelişmeye Açık'
       END AS basari_durumu
FROM ogrenciler;

-- 14. Her dersin ortalama notunu hesapla
SELECT 
  ROUND(AVG(matematik), 2) AS ort_matematik,
  ROUND(AVG(fizik), 2)     AS ort_fizik,
  ROUND(AVG(kimya), 2)     AS ort_kimya,
  ROUND(AVG(biyoloji), 2)  AS ort_biyoloji
FROM ogrenciler;

-- 15. Ortalama notu 70-80 arası olan öğrencileri getir
SELECT * 
FROM ogrenciler 
WHERE ortalama BETWEEN 70 AND 80;

-- 16. Soyadı 'Yıldız' olan öğrenciyi getir
SELECT * 
FROM ogrenciler 
WHERE ad_soyad LIKE '%Yıldız';

-- 17. Öğrencileri alfabetik olarak sırala
SELECT * 
FROM ogrenciler 
ORDER BY ad_soyad ASC;

-- 18. Ortalama notu 85 ve üzeri olan erkek öğrencileri getir
SELECT * 
FROM ogrenciler 
WHERE cinsiyet = 'Erkek' AND ortalama >= 85;

-- 19. Aynı isimle başlayan öğrencileri listele (örn: 'Me' ile başlayanlar)
SELECT * 
FROM ogrenciler 
WHERE ad_soyad LIKE 'Me%';

-- 20. ID'si 1005 olan öğrenciyi getir
SELECT * 
FROM ogrenciler 
WHERE id = 1005;
