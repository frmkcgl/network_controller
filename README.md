🔍 Amaç
Bu script, birden fazla Linux sunucusunu yöneten sistem yöneticilerinin işini kolaylaştırmak amacıyla geliştirilmiştir. Özellikle Red Hat, CentOS, Ubuntu, Fedora gibi dağıtımlar üzerinde çalışan sistemlerde, ağ bağlantılarını, ağ arayüzlerini, aktif IP ve port iletişimlerini ve spesifik bağlantı kontrollerini merkezi bir yerden, SSH üzerinden gerçekleştirmeye olanak tanır.
Sunucular arasında geçiş yaparken SSH bağlantılarını yönetir, otomatikleştirir ve gerektiğinde kullanıcıya SSH anahtar kurulumu önerisinde bulunur.

🚀 Ne İşe Yarar?
Aynı ağda bulunan çok sayıda sunucuya tek bir menülü arayüzle bağlanarak:


Ağ arayüzlerini listeleme

Port/IP bağlantılarını inceleme

Belirli bir IP veya porta trafik olup olmadığını kontrol etme

SSH bağlantısını anahtar üzerinden kurarak şifre girişi zorunluluğunu ortadan kaldırma

Anahtar kurulu değilse: kullanıcıya anahtar yüklemek ister misiniz? sorusunu sorma

Anahtar kurulumu reddedilirse, manuel (şifreli) SSH bağlantıya izin verme

🧩 Özellikler
🔸 1. Dinamik ve Katmanlı Menü Sistemi
Ana menü → Yerel sunucu / Uzak sunucu seçimi
Uzak sunucu → Sunucu listesi üzerinden seçim
Her sunucu için ayrı bir ağ kontrol menüsü

🔸 2. Uzak Sunucuya Bağlantı Adımları:
Ping ile sunucu erişilebilir mi kontrol edilir
SSH anahtar bağlantısı denenir (parola sormadan)
Başarılı değilse kullanıcıya şu soru sorulur:
 "Anahtar kurulumu yapılsın mı?"
 Evet: ssh-keygen ve ssh-copy-id ile kurulum yapılır, tekrar SSH denenir
 Hayır: Parola ile SSH bağlantı denenir


🔸 3. Ağ İşlemleri
Her sunucuda aşağıdaki ağ işlemleri yapılabilir:
🟢 Network Bacak Durumu
Tüm ağ arayüzlerinin adı, durumu (up/down), türü ve IP adresi listelenir

Yeşil: aktif ve IP almış arayüzler
Kırmızı: pasif veya IP almamış arayüzler

🔌 IP ve Port Bilgileri
ss -tunp çıktısından hedef/source IP:port bilgileri listelenir

🔍 IP/Port Trafik Kontrolü
Kullanıcıdan IP ve/veya port bilgisi alınır

Bu bilgilerle bağlantı trafiği var mı kontrol edilir

Hiçbir bilgi girilmezse işlem iptal edilerek menüye dönülür
