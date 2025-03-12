# LARAVEL
* PHP tabanlı web geliştirme [framewoküdür.](https://github.com/xBugor/WebFrameWork)
.
* Açık kaynak kodludur.
* Basit sözdizimi(syntax) sahiptir.
* Kapsamlı dökümantasyona sahiptir.
* [MVC](https://github.com/xBugor/MVC) mimarasine sahiptir.
* **ORM** - The Eloquent Object-Relational Mapper, Laravel framework’ün içerisinde bulunan veri tabanı yönetim aracıdır. ORM veritabanı uygulamalarını da kolaylaştırır.
* **Blade şablonu** PHP kodlarını HTML ile birleştirirken temiz ve okunabilir kod oluşturmaya yarar.

    ```<h1>{{ $degisken }}</h1>``` gibi

* **Laravel Artisan CLI**  MVC için yeni controller oluşturma, modeller oluşturma ve veri tabanı [migrasyon](#Migrasyon)
 oluşturmak için hızlı bir çözümdür.


* [Middleware](#Middleware) özelliği vardır.


































### Migrasyon
Geleneksel yöntemlerde veritabanı tablolarını manuel olarak oluşturup değiştirmek gerekirken, migration sayesinde bu işlemler kod ile tanımlanabilir ve sürüm kontrolüne alınabilir.Migration, veritabanı tablolarını oluşturmak, güncellemek ve silmek için kullanılan Laravel'in bir özelliğidir.
### Middleware 
Laravel’de gelen HTTP istekleri ile yanıtlar arasında yer alan ve isteklerin belirli bir işlemden geçmesini sağlayan bir katmandır.
Middleware, bir filtre gibi çalışır. Örneğin:

- Kullanıcı giriş yapmış mı? (Yetkilendirme)
- Kullanıcının IP adresi belirli bir aralıkta mı? (Güvenlik)
- Gelen istekleri logla.
- İstek belirli saatler dışında mı geliyor? (Erişim Kontrolü)