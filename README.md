
Yorgunluk ve Göz Kırpma Takip Sistemi
Bu proje, OpenCV ve MediaPipe kütüphanelerini kullanarak sürücü yorgunluğunu gerçek zamanlı olarak tespit eden bir görüntü işleme uygulamasıdır. Gözlerin açık/kapalı olma durumunu matematiksel bir oranla (EAR) analiz eder ve tehlikeli bir durumda sesli uyarı verir.

✨ Özellikler
Gerçek Zamanlı Takip: Kamera üzerinden anlık yüz analizi.

Göz Kırpma Sayacı: Kullanıcının kaç kez göz kırptığını takip eder.

Yorgunluk Alarmı: Gözler belirlenen süreden (1.2 saniye) daha uzun süre kapalı kalırsa hem görsel hem de sesli uyarı verir.

Yüksek Hassasiyet: MediaPipe'ın refine_landmarks özelliği sayesinde göz çevresinde 478 farklı nokta üzerinden hassas ölçüm yapar.

🛠️ Kurulum
Projeyi bilgisayarınızda çalıştırmak için aşağıdaki kütüphanelerin yüklü olduğundan emin olun:

Bash

pip install opencv-python mediapipe numpy
🚀 Kullanım
Terminal veya IDE üzerinden kodu çalıştırın:

Bash

python fatigue_detection.py
Uygulamadan çıkmak için klavyeden 'q' tuşuna basmanız yeterlidir.

🧠 Nasıl Çalışır?
Sistem, EAR (Eye Aspect Ratio - Göz Boy-En Oranı) algoritmasını kullanır. Gözün dikey ve yatay koordinatları arasındaki mesafe hesaplanarak bir oran elde edilir.

EAR > 0.20: Göz açık.

EAR < 0.20: Göz kapalı.

Eğer gözler 1.2 saniyeden uzun süre kapalı kalırsa, sistem yorgunluk teşhisi koyar ve os.system('say ...') komutuyla (macOS için) sesli uyarı verir.

Not: Windows kullanıcısıysanız sesli uyarı için os.system kısmını winsound veya pyttsx3 kütüphanesi ile değiştirmeniz önerilir.

⚙️ Ayarlar (Parametreler)
Kod içerisindeki şu değerleri kendi kullanımınıza göre optimize edebilirsiniz:

EAR_THRESHOLD: Gözün kapalı sayılması için gereken eşik değer.
CLOSED_TIME_LIMIT: Alarmın çalması için gözlerin ne kadar süre kapalı kalması gerektiği.

