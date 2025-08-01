# 7_5GHZ-Bandpass-Filter-AWR

## Genel Bakış
Bu proje, 7.5 GHz merkez frekanslı bir **mikroşerit band geçiren filtre** tasarımını ve simülasyonunu içermektedir. Tasarım, **AWR Microwave Office** yazılımı kullanılarak gerçekleştirilmiştir. Filtrenin iki farklı versiyonu analiz edilmiştir:  
- **STEP TRANSITION içeren tasarım**
- **STEP TRANSITION içermeyen (doğrudan bağlantılı) tasarım**

Amaç, 7.5 GHz civarındaki sinyallerin geçişine izin verirken diğer frekansları bastıran bir filtre yapısı ortaya koymak ve  STEP TRANSITION kullanmanın filtre performansına etkisini değerlendirmektir.

##  Proje Hedefleri
- Mikroşerit teknolojisiyle 7.5 GHz merkez frekanslı bir filtre tasarlamak
- STEP TRANSITION yapılarının fiziksel geçiş etkilerini simüle etmek
- S-parametre analizleriyle iki farklı yapının sonuçlarını karşılaştırmak
- PCB layout ve grafiksel analizlerle tasarımları değerlendirmek

## Kullanılan Araçlar ve Teknolojiler
- **AWR Microwave Office** – RF devre simülasyonu, layout üretimi
- **Mikroşerit Elemanları:** MLIN, MTEE, STEP
- **S-parametre Analizi:** S11 (yansıma) ve S21 (geçiş) karakteristikleri
- **STEP TRANSITION:** iletim hattı genişlikleri arasındaki geçişleri modellemek için kullanıldı

 **V1 – STEP TRANSITION YOK**  Tüm MLIN hatları doğrudan bağlandı 
 **V2 – STEP TRANSITION VAR**  Hat geçişleri STEP elemanları ile modellenerek daha gerçekçi simülasyon elde edildi 


## Şematik Tasarım

<img width="2220" height="979" alt="image" src="https://github.com/user-attachments/assets/453d455d-13b0-432d-b444-7880af167ead" />


## Simülasyon

<img width="1972" height="986" alt="image" src="https://github.com/user-attachments/assets/0514b623-ed03-459f-bea2-5eb983b1de21" />


## Simülasyon Sonuçları Karşılaştırması

STEP TRANSITION kullanılmadan yapılan tasarımda, 7.5 GHz frekansında S(2,1) değeri -1.555 dB olarak ölçülmüş; yani geçiş kaybı düşük seviyede kalmıştır. Aynı tasarımda S(1,1) yansıma -16.55 dB olup giriş empedans eşleşmesi makul düzeydedir.
STEP TRANSITION kullanıldığında ise, geçiş ve yansıma kayıpları benzer seviyede kalmasına rağmen, filtre 7 GHz civarındaki frekansları da iletmeye başlamıştır. Bu durum, STEP TRANSITION’ın mikroşerit hat geçişlerini daha gerçekçi şekilde modellemesinden kaynaklanmaktadır. Böylece tasarım, gerçek dünya üretim koşullarına daha yakın bir davranış sergilemiştir.
