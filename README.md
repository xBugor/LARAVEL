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

* **Laravel Artisan CLI**   Server başlatılması,veri tabanı [migrasyon](#Migrasyon) oluşturma,controller oluşturma vs gibi tüm işlemlerin yapılabildiği komut satırı arayüzüdür.


* [Middleware](#Middleware) özelliği vardır.


## Windows işletim sistemine Nasıl Kurulur ?

ADIMLAR

1.PHP kurmak

  * Xammp yada wammp server uygulamaları kurabilirsiniz aracaılığyla kurmak.(Önerilir)

  *  Php buradan da kurabilirsiniz https://www.php.net/downloads  versiyonun en az 7 ve üzeri olması gerekiyor. 

2. PHP bağımlıkları için composer yüklemek.Kısaca composer kütüphaneleri manuel olarak kurmak yerine  zahmetsiz bir şekilde yüklemene imkan tanıyor.
    * https://getcomposer.org/

3. laravelin yüklenmesi
    *  Komut satırını açın şu komutu girin:

       <code> `composer global reguire laravel/installer` </code>
  
:exclamation: Bu adamda zip ile ilgili bir hata oluyorsanız lütfen php.ini dosyasında "extension=zip" önündeki noktali virgülü(;) silin ve kaydedin ve programları  yeniden başlatın.

4. laravel projesi oluşturma işlemi
    
    cd komutu ile istediğiniz bir klasöre geçin daha sonra bu klasör içerisinde şu kodu yazın.
   
    ``` laravel new klasoradı ```
    
    ( klasöradı kısmını istediğiniz gibi ayarlayın.)

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

Not: Bu kısımda [MVC](https://github.com/xBugor/MVC) sistemin bilindiği varsayıldı .

:green_apple:  web.php dosyası, uygulamanızın web rotalarını ([Route](#Route)) tanımladığınız dosyadır.

:green_apple: *MVC sisteminde controller bulunduğu klasör*

 yüklediğinizyer/app/http/controller 
 
  - yeni controller oluşturmak için php artisan make:controller yenicontroller
  
  Not: Yeni oluşturduğunuz controllerın namespace yazısından sonraki kısmı kopyalıp web.php dosyasına 'use' yazıp  yapıştırdıktan sonra \ işareti koyup yeni controllerdaki classının adını yapıştırmalısınız.  Aksi halde hata verir.

 ![Photo by xBugor][resim5]

[resim5]: ./assets/controller.png "controller ayarı"

Yukarıdaki gibi bir controllerın web.php dosyası içerisne şu şekilde entegre etmek gerekir.

```use App\Http\Controller\Dene\DeneController```



:green_apple: Veritabanı işlemleri için models klasörü bulunduğu yer:


/app/http/models


:green_apple: MVC sistemindeki viewler bulunduğu yer:

/resources/views

:green_apple:Laravelde web sitesinin php dosylarında blade kullanmanız gerekiyor.
     
  dosyaadı.blade.php

:green_apple:Herhangibir işlem yapıldığında hangi url'ye gidileceğini gösteren route dosyası.(web.php)

  /routes/web.php dosyasından ayarlanıyor.

:green_apple: Public dosyanın içine  css+javascript ve html dosyalarınızı ekleyebilirsiniz. 

:green_apple: .env dosyasının içerisinde database ile ilgili konfigürasyonlar yapabilirsin.

 

:green_apple: ([MiddleWare](#Middleware)) dosyası
 \app\Http\Middleware\Girismiddleware.php
içerisindedir.


### Migrasyon
Geleneksel yöntemlerde veritabanı tablolarını manuel olarak oluşturup değiştirmek gerekirken, migration sayesinde bu işlemler kod ile tanımlanabilir ve sürüm kontrolüne alınabilir.Migration, veritabanı tablolarını oluşturmak, güncellemek ve silmek için kullanılan Laravel'in bir özelliğidir.
### Middleware 
Laravel’de gelen HTTP istekleri ile yanıtlar arasında yer alan ve isteklerin belirli bir işlemden geçmesini sağlayan bir katmandır.
Middleware, bir filtre gibi çalışır. Örneğin:

- Kullanıcı giriş yapmış mı? (Yetkilendirme)
- Kullanıcının IP adresi belirli bir aralıkta mı? (Güvenlik)
- Gelen istekleri logla.
- İstek belirli saatler dışında mı geliyor? (Erişim Kontrolü)


### Route
Gelen HTTP isteklerini (örneğin, bir kullanıcı bir URL'yi ziyaret ettiğinde) belirli bir işlemi gerçekleştirecek şekilde yönlendiren yapıdır. Laravel, rotalar aracılığıyla kullanıcıların belirli URL'lere yönlendirilmesini ve bu isteklerin nasıl işleneceğini tanımlar.
Rota Türleri

-GET: Sayfa görüntülemek için kullanılır (tarayıcıda bir sayfa açmak).

-POST: Form verilerini göndermek için kullanılır.

-PUT: Veriyi güncellemek için kullanılır.

-DELETE: Veriyi silmek için kullanılır

### Controller
Kullanıcıdan gelen istekler burda değerlendirilir. İsteğin detaylarına göre hangi işlemin yapılacağını seçer.(veri güncelleme gibi )

Gerekli verileri Model’den alır, üzerinde işlem yapar ve View’e (görünüme) yönlendirir. View’e işlenmiş verileri iletir ve istemciye HTML, JSON veya başka bir formatta yanıt döndürülmesini sağlar.