# LARAVEL
* PHP tabanlı web geliştirme [frameworküdür.](https://github.com/xBugor/WebFrameWork)
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


## Windows işletim sistemine Nasıl Kurulur ?

ADIMLAR
1.PHP kurmak

 * Xammp yada wammp server uygulamaları kurabilirsiniz. (Önerilir)

  *  Php buradan da kurabilirsiniz https://www.php.net/downloads  versiyonun en az 7 ve üzeri olması gerekiyor. 

2. PHP bağımlıkları için composer yüklemek.Kısaca composer kütüphaneleri manuel olarak kurmak yerine  zahmetsiz bir şekilde yüklemene imkan tanıyor.
    * https://getcomposer.org/

3. laravelin yüklenmesi
    * Komut satırını açın şu komutu girin composer global reguire laravel/installer
4. laravel projesi oluşturma işlemi
    * cd komutu ile istediğiniz bir klasöre geçin daha sonra bu klasör içerisnde şu kodu yazın
   
    ``` laravel new klasoradı``` klasoradı kısmını istediğiniz gibi ayarlayın.

5. Kurulurken bazı bilgiler isteyebilir   
  ![Photo by xBugor][resim]

[resim]: ./assets/Kurulum1.PNG "Front-End Seçimi"

- Eğer sadece backend ile ilgileniyorsanız: none yazıp Enter tuşuna basın. (Sonradan ekleme yapılabilir.)
- Eğer React kullanarak dinamik bir frontend oluşturmayı planlıyorsan bu seçeneği tercih etmelisin.
-  Eğer Vue.js kullanarak dinamik ve reaktif bir frontend oluşturmayı planlıyorsan, bu seçeneği seçmelisin.
- Eğer JavaScript kullanmadan dinamik, reaktif bir kullanıcı arayüzü oluşturmak istiyorsan, bu seçenek iyi bir tercihtir. Özellikle PHP'ye odaklanmak istiyorsan tercih edebilirsin.

  ![Photo by xBugor][resim2]

[resim2]: ./assets/Kurulum2.PNG "Veri tabananı seçimi"

* Hangi veritabanını kullanmak istiyorsanız seçin ve yazın.


  ![Photo by xBugor][resim3]

[resim3]: ./assets/Kurulum3.PNG "Veritabanı default ayarlar"

* Burada default olarak veritabanları satırlar sutünlar oluşturulsun diye soruyor.


  ![Photo by xBugor][resim4]

[resim4]: ./assets/Kurulum4.PNG "Veritabanı default ayarlar"

Laravel'in ön yüz (frontend) varlıklarını (assets) derlemek için gereklidir. Laravel, ön yüz dosyalarını derlemek için Node.js ve npm (Node Package Manager) kullanır. Yüklenmez ise front end tarafı bozuk çalışabilir.



## Dosyaları Tanıyalım
Not MVC sistemin bilindiği varsayıldı.

:green_apple: *MVC sisteminde controller bulunduğu klasör*

 ** yüklediğinizyer/app/http/controller **


:green_apple: Veritabanı işlemleri için models klasörü buşunduğu yer


/app/http/models


:green_apple: MVC sistemindeki viewler için

/resources/views

4.Buraya sayfa eklemek için blade de kullanmanız gerekiyor.
     
     dosyaadı.blade.php

5. İşlem yapılınca nereye gidileceğini url olarak ayarladığı yere gitmesi
     /routes/web.php dosyasından ayarlanıyor.

### Migrasyon
Geleneksel yöntemlerde veritabanı tablolarını manuel olarak oluşturup değiştirmek gerekirken, migration sayesinde bu işlemler kod ile tanımlanabilir ve sürüm kontrolüne alınabilir.Migration, veritabanı tablolarını oluşturmak, güncellemek ve silmek için kullanılan Laravel'in bir özelliğidir.
### Middleware 
Laravel’de gelen HTTP istekleri ile yanıtlar arasında yer alan ve isteklerin belirli bir işlemden geçmesini sağlayan bir katmandır.
Middleware, bir filtre gibi çalışır. Örneğin:

- Kullanıcı giriş yapmış mı? (Yetkilendirme)
- Kullanıcının IP adresi belirli bir aralıkta mı? (Güvenlik)
- Gelen istekleri logla.
- İstek belirli saatler dışında mı geliyor? (Erişim Kontrolü)