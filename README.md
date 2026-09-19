# Campus Life RPG

Campus Life RPG, C# ile geliştirilmiş konsol tabanlı bir kampüs yaşam simülasyonu ve rol yapma oyunudur.

Oyuncu, üniversite kampüsünde farklı konumlar arasında hareket eder ve yaptığı seçimlere göre enerji, akademik başarı, sosyallik ve sağlık değerlerini yönetir.

Proje özellikle Nesne Yönelimli Programlama (OOP), sınıf tasarımı, kalıtım, soyutlama, polymorphism, oyun döngüsü ve durum yönetimi kavramlarını uygulamak amacıyla geliştirilmiştir.

## Projenin Amacı

Bu projenin amacı bir öğrencinin kampüs içerisindeki günlük yaşamını basit bir RPG sistemi üzerinden modellemektir.

Oyuncunun gün içerisinde yaptığı seçimler karakter özelliklerini doğrudan etkiler.

Örneğin:

- Derse gitmek akademik başarıyı artırır.
- Kütüphanede çalışmak akademik başarıya katkı sağlar.
- Spor yapmak sağlığı artırır ancak enerji tüketir.
- Kantine gitmek sosyalliği ve sağlığı artırabilir.
- Yurtta dinlenmek enerjiyi yeniler.
- Dinlenme alanında vakit geçirmek sosyalliği artırır.

Bu nedenle oyuncunun gün içerisindeki aktiviteler arasında denge kurması gerekir.

## Oyun Özellikleri

- Konsol tabanlı RPG sistemi
- Oyuncu karakteri oluşturma
- Kampüs haritasında hareket
- W, A, S, D tuşlarıyla kontrol
- Farklı kampüs konumları
- Zaman yönetimi sistemi
- Sabah, öğleden sonra ve akşam döngüsü
- Karakter özelliklerinin dinamik olarak değişmesi
- Gün sonunda yurda dönüş
- Farklı aktivitelerin farklı sonuçlar üretmesi
- Konuma bağlı karakter durum güncellemeleri
- Oyun durumunun konsol üzerinde gösterilmesi

## Karakter Özellikleri

Oyuncunun dört temel karakter özelliği bulunmaktadır:

- Enerji
- Akademik Başarı
- Sosyallik
- Sağlık

Bu değerler 0 ile 100 arasında tutulmaktadır.

Her kampüs aktivitesi oyuncunun özelliklerini farklı şekilde etkiler.

## Kampüs Konumları

### Yurt

Yurtta dinlenmek enerji ve sağlık değerlerini artırır.

Akşam olduğunda oyuncu yurda dönerek günü tamamlar.

Uyku sonrasında enerji seviyesi yenilenir.

### Sınıf

Sınıfta derse katılmak:

- Akademik başarıyı artırır.
- Sosyalliği artırabilir.
- Enerjiyi azaltır.
- Sağlık değerini bir miktar düşürebilir.

### Kütüphane

Kütüphanede ders çalışmak:

- Akademik başarıyı artırır.
- Enerjiyi azaltır.
- Sosyalliği düşürebilir.
- Sağlığı bir miktar azaltabilir.

### Kantin

Kantinde yemek yemek ve arkadaşlarla vakit geçirmek:

- Sosyalliği artırır.
- Sağlığı artırır.
- Enerjiyi bir miktar azaltır.

### Spor Salonu

Spor yapmak:

- Sağlığı önemli ölçüde artırır.
- Sosyalliğe katkı sağlar.
- Enerji tüketir.

### Dinlenme Alanı

Dinlenme alanında arkadaşlarla vakit geçirmek:

- Sosyalliği artırır.
- Sağlığa küçük bir katkı sağlar.
- Enerji tüketir.

## Zaman Yönetimi

Oyunda üç farklı zaman dilimi bulunmaktadır:

- Morning
- Afternoon
- Evening

Oyuncu her önemli aktivite gerçekleştirdiğinde zaman ilerler.

Zaman akışı:

    Morning
       ↓
    Afternoon
       ↓
    Evening

Akşam olduğunda oyuncunun yurda dönmesi gerekir.

Gün tamamlandıktan sonra zaman yeniden sabaha döner.

## Kampüs Haritası

Oyun içerisinde karakter ASCII tabanlı bir kampüs haritasında hareket etmektedir.

Haritada kullanılan bazı semboller:

- `Y` — Yurt
- `S` — Sınıf
- `K` — Kütüphane
- `C` — Kantin
- `G` — Spor Salonu
- `D` — Dinlenme Alanı
- `♀` — Oyuncu karakteri

Oyuncu harita üzerinde:

- `W` — Yukarı
- `A` — Sol
- `S` — Aşağı
- `D` — Sağ
- `E` — Bulunduğu yerde kal
- `Q` — Oyundan çık

tuşlarını kullanabilir.

## Oyun Kuralları

Oyuncunun gün içerisindeki seçimlerine göre bazı ek kurallar bulunmaktadır.

Örneğin sabah saatlerinde ders veya kütüphane dışında farklı bir aktivite tercih edilmesi akademik başarı üzerinde olumsuz etki oluşturabilir.

Oyuncunun akşam olduğunda yurda dönmesi gerekir.

Bu kurallar sayesinde yalnızca konum değiştirmek yerine zaman ve karakter özelliklerinin birlikte yönetilmesi amaçlanmıştır.

## Nesne Yönelimli Programlama

Proje Nesne Yönelimli Programlama prensipleri kullanılarak geliştirilmiştir.

### Soyutlama

Kampüs konumlarının ortak özellikleri:

`BaseLocation`

soyut sınıfı içerisinde tanımlanmıştır.

Her konum:

`Visit(Player player)`

metodunu kendi davranışına göre uygular.

### Kalıtım

Kampüs konumları `BaseLocation` sınıfından türetilmiştir.

Örneğin:

- `Dormitory`
- `Classroom`
- `Library`
- `Cafeteria`
- `Gym`
- `RecreationArea`

aynı temel sınıftan kalıtım almaktadır.

### Polymorphism

Her konum aynı `Visit()` metodunu farklı şekilde uygular.

Bu sayede oyuncu farklı bir konuma gittiğinde aynı metod çağrısı üzerinden farklı karakter özellikleri güncellenebilir.

### Encapsulation

Oyuncu özellikleri doğrudan dışarıdan değiştirilemez.

Enerji, akademik başarı, sosyallik ve sağlık değerleri `Player` sınıfı üzerinden kontrol edilerek güncellenmektedir.

## Temel Sınıflar

### Player

Oyuncunun:

- Adı
- Enerjisi
- Akademik başarısı
- Sosyalliği
- Sağlığı

gibi bilgileri saklanmaktadır.

### GameManager

Oyunun ana akışını kontrol eder.

Görevleri arasında:

- Oyunu başlatmak
- Oyun döngüsünü yönetmek
- Hareketleri işlemek
- Konum ziyaretlerini yönetmek
- Zaman sistemini kontrol etmek
- Gün sonunda yurda dönüşü gerçekleştirmek

bulunmaktadır.

### GameMap

Kampüs haritasını oluşturur ve oyuncunun konumunu yönetir.

Oyuncunun harita sınırlarının dışına çıkmasını önler.

### TimeManager

Oyun içerisindeki zaman akışını yönetir.

Sabah, öğleden sonra ve akşam durumları arasında geçiş gerçekleştirir.

### BaseLocation

Tüm kampüs konumlarının kullandığı ortak soyut sınıftır.

Her konum oyuncunun özelliklerini farklı şekilde değiştirebilir.

## Proje Yapısı

- `CampusLifeRPG.cs` — Programın giriş noktası
- `CampusLifeRPG.sln` — Visual Studio Solution dosyası
- `CampusLifeRPG/CampusLifeRPG.csproj` — C# proje dosyası
- `CampusLifeRPG/GameManager.cs` — Oyun akışı ve temel oyun döngüsü
- `CampusLifeRPG/GameMap.cs` — Kampüs haritası ve hareket sistemi
- `CampusLifeRPG/Player.cs` — Oyuncu özellikleri ve durum yönetimi
- `CampusLifeRPG/TimeManager.cs` — Zaman yönetimi
- `CampusLifeRPG/BaseLocation.cs` — Kampüs konumlarının temel soyut sınıfı
- `CampusLifeRPG/Dormitory.cs` — Yurt davranışları
- `CampusLifeRPG/Classroom.cs` — Sınıf davranışları
- `CampusLifeRPG/Library.cs` — Kütüphane davranışları
- `CampusLifeRPG/Cafeteria.cs` — Kantin davranışları
- `CampusLifeRPG/Gym.cs` — Spor salonu davranışları
- `CampusLifeRPG/RecreationArea.cs` — Dinlenme alanı davranışları

## Kullanılan Teknolojiler

- C#
- .NET Framework
- Visual Studio
- Object-Oriented Programming
- Console Application
- Inheritance
- Abstraction
- Polymorphism
- Encapsulation
- Game Loop
- State Management

## Çalıştırma

Projeyi Visual Studio ile açmak için:

`CampusLifeRPG.sln`

dosyasını açın.

Projeyi derledikten sonra uygulamayı çalıştırın.

Program başladığında karakterinizin adını girmeniz istenir.

Daha sonra kampüs haritası ekrana gelir ve W, A, S, D tuşları kullanılarak karakter hareket ettirilebilir.

## Oyun Akışı

Program genel olarak aşağıdaki şekilde çalışmaktadır:

1. Oyuncu karakter adını girer.
2. Karakter yurtta oyuna başlar.
3. Kampüs haritası gösterilir.
4. Oyuncu kampüs içerisinde hareket eder.
5. Bir konuma girildiğinde ilgili aktivite gerçekleştirilir.
6. Karakter özellikleri güncellenir.
7. Zaman ilerler.
8. Akşam olduğunda oyuncu yurda döner.
9. Uyku sonrasında yeni gün başlar.

## Öğrenilen Kavramlar

Bu proje kapsamında aşağıdaki konular uygulamalı olarak kullanılmıştır:

- Nesne Yönelimli Programlama
- Sınıflar ve Nesneler
- Kalıtım
- Soyut Sınıflar
- Polymorphism
- Encapsulation
- Enum Kullanımı
- Dictionary Veri Yapısı
- Oyun Döngüsü
- Harita Yönetimi
- Klavye Kontrolleri
- Durum Yönetimi
- Zaman Yönetimi
- Hata Yönetimi

## Proje Notu

Bu proje Nesne Yönelimli Programlama ve C# programlama kavramlarını uygulamak amacıyla geliştirilmiş akademik bir çalışmadır.
