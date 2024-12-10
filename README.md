

# Diffie-Hellman Chat Application
Bu proje, istemciler (clients) ve bir sunucu (server) arasında güvenli iletişim kurmak için Diffie-Hellman Anahtar Değişim Algoritmasını kullanır. Ayrıca, istemciler sunucuya bağlandıktan sonra diğer kullanıcılarla mesajlaşabilir ve mesajlarını kaydedebilir. Proje, brute force saldırılarını test etmek için bir konsol komutu da sunar.

## Özellikler
Diffie-Hellman Anahtar Değişimi:

İstemci ile sunucu arasında anahtar değişimi yapılır.
Anahtarlar güvenli bir şekilde oluşturulur ve kullanılır.
## Mesajlaşma:

"Everyone" seçeneği ile mesajlar tüm kullanıcılara iletilebilir.
Belirli bir kullanıcıya doğrudan mesaj gönderilebilir.
## Kayıt ve Giriş Sistemi:

Kullanıcılar kayıt olabilir ve giriş yapabilir.
Giriş yaptıktan sonra, daha önce kendilerine gönderilen mesajlar istemciye iletilir.
## Sunucu Özellikleri:

Gelen mesajları kaydeder.
Sunucu üzerinden istemcilere mesaj gönderilebilir.
## Brute Force Testi:

Konsola bruteforce yazılarak sistemin brute force saldırılarına karşı performansı test edilebilir.
# Kurulum ve Çalıştırma
## Gereksinimler
.NET Framework veya .NET Core SDK
MySQL Veritabanı (Mesaj ve kullanıcı bilgileri için)
## Adımlar
### Proje Depolarını Klonlayın:
```
git clone https://github.com/PnterNN/Diffie-Hellman-Project
```
### Sunucu (Server) Başlatma:

Server projesini çalıştırın.
Sunucu, varsayılan olarak Port: 900 üzerinden çalışır.
### İstemci (Client) Bağlantısı:

Client projesini çalıştırın.
Sunucu IP adresi ve port bilgilerini girerek bağlantı kurun.
### Mesajlaşma:

Kayıt olun veya giriş yapın.
"Everyone" seçeneğiyle herkese veya belirli bir kullanıcıya mesaj gönderin.
### Brute Force Testi:

MiddleMan projesini çalıştırın.
Konsola bruteforce yazarak brute force testini başlatın.
Kullanım
### Sunucu (Server):
Mesaj gönderimi:
Everyone veya belirli bir kullanıcıya mesaj gönderebilirsiniz.
Mesajlar ve kullanıcı bilgileri MySQL veritabanına kaydedilir.
### İstemci (Client):
Giriş yaptıktan sonra:
Daha önce alınan mesajlar istemciye iletilir.
Diğer kullanıcılarla mesajlaşabilirsiniz.
Yeni bir kullanıcı oluşturmak için kayıt olabilirsiniz.
### Brute Force (MiddleMan):
Konsola bruteforce yazarak şifreleme algoritmasının güvenliğini test edebilirsiniz.
Bu işlem, Diffie-Hellman protokolünün belirli anahtarları ne kadar hızlı bulabileceğini analiz eder.
## Proje Mimarisi
### Client (İstemci):
Kullanıcı kayıt/giriş sistemi
Diğer istemcilere mesaj gönderimi
Diffie-Hellman anahtar değişimi
### Server (Sunucu):
Kullanıcı oturumları ve mesajları yönetir.
Mesajları veritabanında saklar.
Anahtar değişimini yönetir.
3. MiddleMan (Ara Katman):
Brute force saldırı testi.
Diffie-Hellman anahtar değişim güvenliğini analiz eder.
Ekran Görüntüleri
## Sunucu Arayüzü
Sunucunun bağlantıları, mesajlaşmaları ve kullanıcı yönetimini gösterir.
![image](https://github.com/user-attachments/assets/76d1f460-bdb5-407a-87cd-63be7a1f73a4)


## İstemci Arayüzü
Kullanıcı giriş/kayıt ekranı ve mesajlaşma arayüzünü içerir.
![image](https://github.com/user-attachments/assets/2eb550a2-529f-4ab7-a473-5451c3aa72e3)

## Önemli Notlar
Anahtar değişiminde Diffie-Hellman algoritması kullanılmaktadır.
Sunucu, kullanıcı oturum bilgilerini ve mesajları güvenli bir şekilde kaydeder.
MiddleMan uygulaması yalnızca test amaçlıdır; gerçek saldırılar için kullanılmamalıdır.
## Veritabanı Şeması
<div>
  <h3>Veritabanı Şeması</h3>

  <h4>Tablo: Users</h4>
  <table border="1">
    <thead>
      <tr>
        <th>Column</th>
        <th>Data Type</th>
        <th>Açıklama</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Id</td>
        <td>INT</td>
        <td>Kullanıcı ID</td>
      </tr>
      <tr>
        <td>Username</td>
        <td>VARCHAR</td>
        <td>Kullanıcı Adı</td>
      </tr>
      <tr>
        <td>Email</td>
        <td>VARCHAR</td>
        <td>E-posta</td>
      </tr>
      <tr>
        <td>Password</td>
        <td>VARCHAR</td>
        <td>Şifre (Hashlenmiş)</td>
      </tr>
    </tbody>
  </table>

  <h4>Tablo: Messages</h4>
  <table border="1">
    <thead>
      <tr>
        <th>Column</th>
        <th>Data Type</th>
        <th>Açıklama</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Id</td>
        <td>INT</td>
        <td>Mesaj ID</td>
      </tr>
      <tr>
        <td>Sender</td>
        <td>VARCHAR</td>
        <td>Mesajı gönderen</td>
      </tr>
      <tr>
        <td>Receiver</td>
        <td>VARCHAR</td>
        <td>Mesajın alıcısı</td>
      </tr>
      <tr>
        <td>Message</td>
        <td>TEXT</td>
        <td>Mesaj içeriği</td>
      </tr>
      <tr>
        <td>Timestamp</td>
        <td>DATETIME</td>
        <td>Mesaj gönderim zamanı</td>
      </tr>
    </tbody>
  </table>
</div>

## Geliştirici Notları

### Şifreleme: 
Diffie-Hellman algoritması kullanılarak iletişim güvenliği sağlanmıştır.

### Test: 
MiddleMan uygulaması ile brute force testleri yapılabilir.

### Genişletilebilirlik: 
Mesajlaşma protokolü ve kayıt sistemi genişletilebilir şekilde tasarlanmıştır.
