# STM32F401RCT6 Çok Fonksiyonlu Gösterge ve Kontrol Sistemi

Bu proje, STM32F401RCT6 mikrodenetleyici kullanılarak yapılan çok fonksiyonlu bir gömülü sistem uygulamasıdır. Sistem, potansiyometre, NTC sensör, LED, 4'lü 7 segment display ve LCD ekran ile veri ölçümü ve gösterimi yapmaktadır.

## Özellikler

- **Duty Oranı Ölçümü:** Potansiyometreden alınan duty oranı ADC ile ölçülür ve bir LED’in parlaklığına uygulanır.
- **Sıcaklık Ölçümü:** NTC sensör kullanılarak ortam sıcaklığı ölçülür.
- **Veri Gösterimi:**
  - LCD ekranda duty oranı ve sıcaklık değerleri sırayla gösterilir.
  - 4’lü 7 segment display’de sıcaklık değeri görüntülenir.
- **Kullanıcı Etkileşimi:** Butona basıldığında LCD ekranındaki gösterilen veri duty oranı ve sıcaklık arasında geçiş yapar.

## Kullanılan Donanım

| Donanım           | Bağlantı Noktası        |
|------------------|-----------------------|
| STM32F401RCT6     | -                     |
| LCD (16x2)        | RS=PB0, E=PB1, D4-D7=PB4-PB7 |
| Buton             | PB12 (dahili pull-up etkin) |
| Potansiyometre    | ADCx (örnek: PA0)      |
| LED               | PA5                    |
| NTC sensör        | ADCy (örnek: PA1)      |
| 4'lü 7 segment display | A1-A7 = A-G, COM1-COM4 = A8-A11 |

## Yazılım Özellikleri

- STM32CubeIDE kullanılarak C dilinde geliştirilmiştir.
- HAL kütüphaneleri ile ADC, GPIO ve Timer konfigürasyonu yapılmıştır.
- PWM ile LED parlaklığı duty oranına göre ayarlanır.
- 7 segment display sürümü multiplexing ile yapılmıştır.
- LCD’deki veri değişimi buton kesmesi ile kontrol edilir.

## Kurulum

1. Proje dosyalarını STM32CubeIDE ile açın.
2. ADC, GPIO ve Timer ayarlarını kendi devre bağlantılarınıza göre kontrol edin.
3. Kodları derleyip mikrodenetleyiciye yükleyin.
4. Potansiyometreyi çevirerek duty oranını değiştirin, LED parlaklığını gözlemleyin.
5. Butona basarak LCD’de duty ve sıcaklık değerleri arasında geçiş yapın.
