

# iii. Hafta Ödevleri

## 1. .NET kodu nedir, nasıl derlenir ?
> .NET kodu amacı performansla ilgili olarak komut dosyası ortamlarının karşılaştığı sorunları ortadan kaldıran bir kod yürütme ortamı sağlamak.
- .NET Core ve .NET Framework ' de bir veya daha fazla kaynak kodu dosyasından derleme oluşturulabilir. 
- Kaynak kodunuz, ortak ara dil (CIL) veya MSIL (Microsoft Ara Dili) olarak bilinen bir bayt kodunda derlenir.
- Derlemeler _. exe_ veya _. dll_ dosyaları olarak uygulanır. Her sınıftan ve her yöntemden veriler, sonuçta ortaya çıkan yürütülebilir dosyanın (bir dll veya bir exe) başlığına dahil edilir. 
- . exe_ veya _. dll_ dosyaları üretilirken, yürütülebilir dosya çalıştırıldığında CLR'yi (Ortak dil çalışma zamanı) yüklemekten sorumlu geleneksel bir önyükleyici de içerir.
- Eğer bir kod MSIL’ye çeviriliyor ise bu kodun CLR tarafından manage edilmesi gerekiyordur. CLR tarafından manage edilen kodlara Managed Code diyoruz.
- Eğer bir kod MSIL’e çevrilmeden direkt olarak işletim sistemi ile iletişime geçiyor ise bu kodlara  Unmanaged Code diyoruz.
> .NET Framework’de bulunan CLR’ın karşılğını .NET Core’da CoreCLR alırken, Class Library’nin karşılığını da [dotnet/runtime](https://github.com/dotnet/runtime) (CoreFx) almıştır. NET Core modüler yapısıyla ve open source bir framework olarak contribute edilebilir ortam sağlamıştır. Microsoft hem kendi frameworkünü .NET ekosisteminde yaşayan geliştiricilerin isteklerine hızlı cevap verir hale getirdi. 
> .NET Standard kısmında fiziksel olarak herhangi bir iş yapmamaktadır. .NET Standard, Class Library’lerin (.NET Framework CL , CoreFx CL, Mono CL) ortak olarak çalışmasını yani ilgili runtime’da Class Library üzerinde bulunan hangi özelliklerin kullanabileceğini belirler.

## 2. Roslyn compiler ne işe yarar ?
> Roslyn .NET platformu için kod analizi, runtime esnasında dinamik olarak derlemeyi ve kod üretmeyi sağlayan kütüphane ve altyapıları sunan bir yapıdır. C# kodunun bilgisayar üzerinde çalışabilmesi için öncelikle derleyicisi Roslyn tarafından derlenmesi gerekmektedir. Roslyn  kütüphanesi ile çalışırken sanki visual studio veya benzer bir .Net editör ve compiler ile çalışır gibi size bir .Net uygulamasının yapısını (project, class, interface, method, properties, attribute vs..) bilgilerini yani kod ile ilgili bütün bilgileri verecektir. .NET Compiler Platform (Roslyn) çözümleyiciler stil, kalite, bakım, tasarım ve diğer sorunlar için C# veya Visual Basic kodunuzu inceler.  Bu denetleme veya analiz, tüm açık dosyalardaki tasarım zamanı sırasında yapılır.
## 3. Restful servisler nasıl çalışır ? Alternatifleri nelerdir ve nasıl çalışırlar?
> REST client-server iletişimiyle ilgili bir mimaridir. HTTP protokolü ile paralel olarak gelişmiştir ve World Wide Web sisteminde kullanılıyorlar. REST mimarisini kullanan servislere genel olarak RESTful servis deniyor. 
> Restful servisteki ana fikir client-server arasında ki veri alışverişini alternatifleri olan SOAP, RPC gibi kompleks mimarilerle sağlamak yerine, HTTP protokolü üzerinden sağlamaktır. RESTful servisler SOAP, RPC’nin aksine basit ve hafiftirler. Basit olmalarının yanında oldukça da esnek ve yeteneklidirler. SOAP'a ait keskin standarlar Restful servislerinde bulunmaz. Birçok platformun standart library’leri kullanılarak, kendimiz de hızlıca REstful Servisler geliştirilebilirler. 
> SOAP ile en büyük farkı, SOAP gibi proxy kullanmaya, bir WSDL’e zorlamıyor olmasıdır. REST mimarisindeki önemli noktalardan biride her HTTP request’inde yapılması istenilen işlemin POST, PUT, DELETE, GET gibi HTTP metotlarıyla ifade edilmesidir.  Böylece proxy ihtiyacı ortadan kalkmış olur ve platform bağımsız yapılar kurmak kolaylaşır. 
> RESTful servislerin birçok farklı response tipi olabilir. Bugünlerde popüler olarak JSON kullanılıyor fakat XML, CSV veya amaca bağlı olarak HMTL bile kullanılabilir.
> Kısacası Rest servisler ;
-   Platform bağımsızlar. (Client’ın Windows, Server’ın Linux olmasının hiç bir önemi yok)
-   Dil bağımsızlar .
-   HTTP üzerinden çalışıyorlar.
-   Esnekler ve çok kolay genişletilebilirler.
## 4. Extension method nedir? Nasıl yazılır ?
> Extension method mevcut class ve struct yapılar üzerinde değişiklik yapmadan genişletilmiş metod yazılabilmesini sağlar. Extension Method'lar C#3.0 ile hayatımıza girmiştir.
> Extesion metod yazarken uymamız gereken bir kaç kural vardır. Bunlar;
-   Extension metodlar static bir class içerisinde static olarak tanımlanmalıdır.
-   Extend edilecek class ilgili extension metoda metodun ilk parametresi olarak verilip önünde  **this**  keyword'ü ile tanımlanmalıdır
-   Extension metod da tanımlı parametrelerden sadece 1 tanesi  **this**  keyword'ü ile tanımlanır.
## 5. MVC'nin alternatifleri nelerdir ?
> MVP ve MVVM MVC alternatifleri olarak gösterilebilirler. MVVM, bugün özellikle mobil(android, iOS), UWP, WPF için uygulamalar geliştirirken tercih edilen yazılım mimarilerinden bir tanesi. **MVVM**, **Presentation Model** mimarisinin **WPF** ve **Silverlight** teknolojileri için **özelleştirilmiş** bir halidir. Doğrudan Silverlight ve WPF için özelleştirilmiş bir uygulama geliştirme mimarisi olduğu içinde haliyle bu teknolojilerin tüm özelllikleri fazlasıyla bu mimari model içerisinde kullanılmakta.
- **Model :** Model, uygulama içerisinde kullanacağımız olan datadır. Bu datalar WCF RIA Services ile döndürülen entityler olabileceği gibi doğrudan tanımlanmış POCO nesneleri de olabilir.
- **View :** View, datanın sunulduğu katmandır. Tüm görsellikler View'da yer alır. Kısaca verinin sunulduğu yerdir(**Ekran**).
- **ViewModel :** ViewModel ise  **Model** ile  **View'ı** bağlayan yapıdır. View ile Model arasında bir yapıştırıcı görevi görür. View doğrudan ViewModel yardımıyla Model'e erişir ve bazı işlemleri gerçekleştirir. Teknolojik olarak WPF veya Silverlight teknolojilerinden konuşursak  **ViewModel** aslında  **View'ın  _DataContext'idir_**.
> MVVM getirdiği artılar şu şekildedir. 
- Commanding, Binding, Behaviour gibi özellikleri kullanarak dekleratif programlama özelliklerini kullanarak hızlı ve etkin uygulama geliştirme.
-   View arkasında bulunan kod dosyası içerisinde  **sıfır kod**  yazarak bağımlılıkları minimuma indirmek ve uygulama içerisinde katmanların bağımlılıklarını minimuma indirmek.
-   Daha genişletilebilir, bakımı yapılabilir ve test edilebilir uygulamalar geliştirmek.
-   Arayüzü kolay bir şekilde taşınabilen uygulamalar geliştirmek.
> MVP(Minimum Geçerli Ürün-Minimum Viable Product) öğrenmenin etkisini vurgulayan, kullanıcılardan en hızlı şekilde geri-bildirim almaya odaklanan bir konsepttir. Yeni bir ürünün en az eforla, en fazla kullanıcı geri-bildirimi alınmasına olanak sağlayan bir sürümüdür. MVP konsepti özellikle yeni ürün geliştirme sürecinde ekiplere çok büyük faydalar sağlamaktadır.
## 6. Architectural pattern nedir? Neden ihtiyaç duyuyoruz?
> Bileşen, Servis, vb yapılarından oluşan uygulamaların aşağıdaki özellikler benzer problemler oluşturur. Bu problemleri gidermek için kullanılan, sistemin tamamında benzer örneklerin görüldüğü çözümlere/yapılara **architectural pattern(Mimari örüntüler)** denir.
> Mimari örüntülerin, tasarım örüntülerinden farkı, belli bir alanda, belli bir kapsamdaki problemi çözmek yerine uygulamanın her yerinde geniş alana yayılan problemi çözmeyi hedeflemesidir.
> Architectural patternlerdan bazıları ;
 -   Microservices
-   Microfrontends
-   Service-oriented architecture (SOA)
-   Layers, Multi tier Katmanlı Uygulama Mimarisi
-   Flux Patten (Redux, vb…)
-   MVC (Model View Controller) Örüntüsü]
-   Broker Pattern
-   Event-Driven Architecture
-   Blackboard System
-   Pipe and filter architecture

> 
## 7. ViewData, ViewBag, TempData farkları nelerdir? Çalıştığımız proje üzerinde başka bir branch açarak bunları deneyiniz?
> Denetleyiciden görünüme ve sonraki sonrakine veri iletmek için, ASP.Net MVC çerçevesi, ViewData, ViewBag ve TempData gibi farklı seçenekler sunar.
> Kısaca ViewBag , ViewData ve TempData ; Bu üç .Net MVC nesnesinin belirgin özelliğini küçük boyutlardaki verilerimizi **Controller** dan **View** kısmına aktarmak için kullanılır.
> ViewData ve ViewBag aynı çalışma mantığına sahip olmakla beraber ViewData ; .Net MVC, .Net MVC 2 ve .Net MVC 3 de çalışmaktadır. Fakat ViewBag .Net MVC 3 ile birlikte gelen yeni ve runtime içerisinde oluşan dinamik bir nesnedir. 
> Tempdata ise herhangi Controller dan oluşturulmuş olan veriyi Views ler arasında taşımamıza veya tek bir View içerisinde elimizdeki veriyi ekran çıktısı olarak görüntüler.
> Eğer büyük bir nesne Controller dan Views gönderilecekse büyük boyutlardaki veriler için **ViewModels** kullanılması önerilir.

#### Kaynaklar 
- https://docs.microsoft.com/tr-tr/visualstudio/code-quality/roslyn-analyzers-overview?view=vs-2019
- https://medium.com/@sonmezosman/roslyn-ile-statik-kod-ve-etki-analizi-752b7699b1bd
- https://medium.com/@sercandumansiz/kod-nas%C4%B1l-%C3%A7al%C4%B1%C5%9F%C4%B1r-net-bak%C4%B1%C5%9F-a%C3%A7%C4%B1s%C4%B1yla-ge%C3%A7mi%C5%9Ften-g%C3%BCn%C3%BCm%C3%BCze-e0cb430e6601
- https://www.codeproject.com/Articles/3992/What-is-NET
- https://stackoverflow.com/questions/1236182/how-and-when-does-net-actually-compile-code
- https://docs.microsoft.com/tr-tr/dotnet/standard/assembly/
- https://denizirgin.com/rest-ve-restful-web-servis-kavram%C4%B1-30bc4400b9e0
- https://medium.com/@bsrutmn/rest-ve-restful-web-servi%CC%87s-nedi%CC%87r-7258b7db7f66
- http://www.canertosuner.com/post/C-Extension-Method-Kullan%C4%B1m%C4%B1
- https://medium.com/@serkan22789/c-extension-method-nedir-16dde50f9630
- https://stackoverflow.com/questions/28299365/what-is-the-difference-between-viewdata-viewbag-and-tempdata
- http://www.aspmvcnet.com/tr/m/razor/viewbag-viewdata-ve-tempdata-asp-net-mvc-3-kullanimi-ve-farklari.html
- https://medium.com/architectural-patterns/architectural-patterns-mimari-%C3%B6r%C3%BCnt%C3%BCler-2e945dc761b3
- https://www.ilkayilknur.com/mvvm-model-view-viewmodel-nedir
