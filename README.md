# Mini PHP Postacı

PHP ile yazılmış basit bir API test aracıdır. GET, POST, PUT, DELETE ve PATCH istekleri gönderebilir; istekleri koleksiyonlar içinde saklayabilirsiniz.

## Özellikler

- HTTP isteklerini cURL ile gönderme
- Klasör ve koleksiyonlarla istekleri düzenleme
- İstek başlıklarını ve gövdesini düzenleme
- JSON yanıtlarını biçimli gösterme
- IP tabanlı erişim kontrolü

## Gereksinimler

- PHP 7 veya üzeri
- cURL eklentisi etkin PHP
- Apache, Nginx veya PHP yerleşik web sunucusu

## Kurulum

1. Depoyu alın:

   ```sh
   git clone https://github.com/erdiakaltun/PHP-mini-postaci.git
   cd PHP-mini-postaci
   ```

2. Web sunucunuzda uygulamayı çalıştırmadan önce erişmesine izin verilecek IP adreslerini ortam değişkeninde tanımlayın. Birden fazla adresi virgülle ayırabilirsiniz:

   ```sh
   MINI_POSTACI_ALLOWED_IPS="203.0.113.10,2001:db8::10"
   ```

   Apache veya PHP-FPM kullanıyorsanız değişkeni web sunucusu/PHP-FPM servis yapılandırmasına ekleyin. Uygulama istemci adresi olarak yalnızca `REMOTE_ADDR` değerini kullanır; ters vekil başlıkları güvenilir kabul edilmez. Değişken ayarlanmazsa tüm istekler reddedilir.

3. Web kökünü bu klasöre yönlendirin. Yerel geliştirme için:

   ```sh
   php -S 127.0.0.1:8000
   ```

   Ardından `http://127.0.0.1:8000` adresini açın ve `127.0.0.1` değerini izin verilen IP listesine ekleyin.

## Veri

Koleksiyonlar `collections.json` dosyasında saklanır. Web sunucusu kullanıcısının bu dosyaya yazma izni olmalıdır. Dosyayı web üzerinden doğrudan indirmeye kapatmanız önerilir.

## Güvenlik notu

HTTPS hedeflerinde TLS sertifika doğrulaması etkin tutulur. Uygulamayı internete açık bırakmayın; IP erişim kontrolü uygulama düzeyinde ek bir korumadır ve kimlik doğrulamanın yerini tutmaz.
