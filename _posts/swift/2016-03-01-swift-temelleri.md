---
layout: post
title: S01 - Swift Temelleri
modified:
categories: swift
excerpt: Swift programlama dilinin temellerini görebilir ve Swift programlama dilini öğrenmeye bu yazı ile başlayabilirsiniz.
tags: [swift, programlama, giriş, temel, değişkenler, optional, int, değişken, ]
image:
  feature:
date: 2016-03-01T18:41:06+02:00
comments: true
---

**Swift**, *iOS*, *OSX*, *tvOS*, *watchOS* ve *Linux* platformları için Apple tarafından açık kaynak bir şekilde geliştirilen yeni bir programlama dilidir.

Bir çok programalama dilinin iyi özelliklerini bünyesinde toplamıştır ve hem Apple hem de topluluğun gücü ile günden güne gelişmektedir. OSX ve Linux dağıtımlarında geliştirme yapmak mümkündür.

### Constants and Variables / Sabitler ve Değişkenler

Swift dilinde değişken tanımlarken iki şekilde bunu yapabiliriz. 

*Constant* olarak tanımlanmış bir değişken uygulama içerisinde ilk bildirim esnasında değer ataması yapılır ve program boyunca bir daha değiştirilemez.  

```swift
let maximumNumberOfLoginAttempts = 10
```

*Variables* olarak tanımlanmış değişkenler ise programlama boyunca değişitirlebilirler.

```swift
var currentLoginAttempt = 0
```

Birden fazla değişken veya sabit tanımlamalarını tek bir satırda virgüller ile ayırarak yapabiliriz.

```swift
var x = 0.0, y = 0.0, z = 0.0
let a = "a", b = "b", c = "c"
```

### Type Annotations / Tip Bildirimleri
Değişkenleri tanımlarken o değişkenin tip bildirimlerini değişken isimlerinden sonra gelecek ':' ile belirtebiliriz. Bu şekilde açıkça değişkenin tipi bildirilmiş olacaktır ve o değişkene yanlışlıkla başka tipte bir atama yapılamayacaktır.

```swift
var welcomeMessage: String
```

Bu kod parçası "*welcomeMessage*" adında "*String*" tipinde değişken tanımla demektir.

Birden fazla değişken için tip bildirimlerini tek bir satırda yapabiliriz.

```swift
var red, green, blue: Double
```

Kodlama yaparken tip bildirimlerini katı kurallı kodlar yazarken sıklıkla başvurabiliriz. Ancak atamanın tek seferde yapılacağı ve sonradan değiştirilmeyeceği sabit -constant- bildirimlerinde tip bildirimi yapmaya gerek yoktur. Swift dili değişkenin tipini anlayacaktır. 

### Değişken İsimledirme

Swift programlamada değişken isimleri neredeyse herhangi bir karakteri barındırabilirler. Unicode karakterli değişken isimleri de yaratabiliriz.

```swift
let π = 3.14159
let 你好 = "你好世界"
var 🎓 = "education"
```

Değişken isimleri özel karakterler, boşluk karakterleri (whitespace characters), matematik sembolleri, oklar, özel kullanımlı Unicode kod noktaları, satır veya kutu çizme karakterleri içeremezler. 

Değişken isimleri *rakam* ile başlayamaz.

Değişken ismi bir kere tanımlandıktan sonra aynı isimde farklı bir değişken tanımlaması yapılamaz.

Tanımlaması yapılmış bir değişkene tanımlaması yapılırken ifade edilmiş tipten başka tipte bir atama gerçekleştirilemez.

**Uyarı:** Swift için özel olarak ayrılmış anahtar kelimeleri değişken veya sabit ismi olarak kullanmanız gerekiyor ise bunu yapmak için backtick (`) karakterini kullanmanız gerekmektedir. Ancak anahtar kelimeleri değişken veya sabit ismi olarak kullanmamaya çalışın.
{: .notice}


### Değişken ve Sabitleri Ekrana Yazdırmak

Bunu başarmak için:

```swift
let welcomeMessage = "Merhaba Mustafa!"
print(welcomeMessage)
```

### Yorumlar

**Swift**, **C** dilindeki gibi tek satırlı ve çok satırılı yorumları desteklemektedir.

```swift
// Bu tek satırlık bir yorum ve compiler bunu okumyacak.
```

Çok satırlı yorumlar iç içe yazıldığında diğer dillerde sorun olsa da Swift dilinde yoktur. 

```swift
/* Bu çok satırlı yorum kullanımıdır
/* ve iç içe kullanılmayı desteklemektedir. */
Kod içerisinde yorum satırı kullanmamaya özen göstermek gerekir. */
```

### Semicolons / Noktalı Virgül

Diğer dillerin aksine kod satırlarının sonuna noktalı virgül koymak zorunlu değildir. Ancak noktalı virgül koyabilirsiniz. Tek satırda birden fazla kod bildirimi yaparken noktalı virgül kullanılabilir.

```swift
let cat = "🐱"; print(cat)
// prints "🐱"
```

### Integers / Tam Sayılar

Swift dili 8, 16, 32 ve 64 bit uzunluğundaki integer sayıları desteklemektedir.

Sayı sınırlarını görmek için;

```swift
let minValue = Int32.min
let maxValue = Int32.max 
```

##### Int

Tam sayıları ifade etmektedir. Negatif ve pozitif değer alabilirler. Tip bildiriminde `Int8`, `Int16`, `Int32` ve `Int64` olarak tanımlanır.

**Int** türündeki değişken

* 32 bit platformlarda Int32,
* 64 bit platformlarda Int64

ile aynı boyuttadır.

##### UInt

Swift ayrıca işaretsiz tam sayıları da desteklemektedir. Bu sayılar sıfırdan büyük ve negatif değer içermeyen tam sayılardır. Tip bildiriminde `UInt8`, `UInt16`, `UInt32` ve `UInt64` olarak tanımlanır.

**UInt** türündeki değişken

* 32 bit platformlarda UInt32,
* 64 bit platformlarda UInt64

ile aynı boyuttadır. 

### Floating-Point Numbers / Ondalıklı Sayılar

Tıpkı matematik de ki gibi onalıklı sayılar Swift dilinde desteklemektedir.

* Double 64-bit uzunluğundaki kayan noktalı sayıyı.
* Float 32-bit uzunluğundaki kayan noktalı sayıyı temsil etmektedir.

### Type Safety and Type Inference

Swift **type-safe** bir dildir. Kodlama yaparken kullandığımız değişkenin tipi konusunda açık olmamız beklenmektedir. *String* tipte değer bekleyen bir değişkene yanlışlıkla *Int* tipte bir değer atamamızı önlemektedir.

Swift compile time da tüm değişkenlerin tip kontrollerini yapmaktadır. Bunun sayesinde hatalar development sürecinde kolayca tespit edilebilmekte ve düzeltilmektedir.

Tip kontrolü farklı değişken tipleri ile uğraşırken hataları önlemektedir. Ancak Java dilinde olduğu gibi her değişkenin tip bildirimini yapmak zorunda değilsiniz. Swift, **type-inferance** sayesinde değişkene verilen değerin tipine bakarak değişken tipini otomatik olarak algılamaktadır.

Type inferance sayesinde diğer dillerdeki gibi her değişken tipinin bildirilmesi zorunluluğu ortadan kalkmıştır. Özellikle constant tanımlama yaparken tip bildirimlerine gerek yoktur. 

```swift
let pi = 3.14159
// pi Double tipte yorumlanmuştır.
```

Swift type inferance yaparken kayan noktalı sayılar için *Double* tipte çıkarım yapmaktadır.

### Numeric Literals

* Ondalıklı sayı hiçbir prefix olmadan
* İkili (binary) sayılar *0b* prefix ile 
* Sekizlik tabanda (octal) sayılar *0o* prefix ile 
* Onaltılık tabanda" sayılar *0x* prefix ile tanımlanır. 

Örneğin:

```swift
let decimalInteger = 17
let binaryInteger = 0b10001       // ikili notasyon
let octalInteger = 0o21           // sekizlik notasyon
let hexadecimalInteger = 0x11     // onaltılık notasyon
```

Numeric sayılar daha kolay okunabilmesi adına hem Int hemde Float / Double değişkenler de fazladan sıfır (0) veya alttan çizgi (_) kullanılabilir.

```swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```

### Type Aliases

Swift dilinde var olan bir tipe farklı bir isim ile erişmek istersek alias atayabiliriz.

```swift
typealias MyInt = Int16

var sampleRate: MyInt = 14 
```

### Booleans

Mantıksal olarak bir değişken ya true ya da false değeri alır.

```swift
let orangesAreOrange: Bool = true
let turnipsAreDelicious: Bool = false
```

Swift in type safety özelliği sayesinde bool tipte olmayan bir değişken control flow da statement olarak kullanılamaz.

```swift
let i = 1
if i {
    // Bu kod parçası derlenmeyecektir.
}
```

Alternatif bir çözüm ile

```swift
let i = 1
if i == 1 {
    print("Bu kod çalışacaktır.")
}
```

Örnekte olduğu gibi kontrol durumlarında boolean değer üretecek karşılaştırma operatörlerinden faydalanmak gerekir. Bu yaklaşım ile dilin daha açık olması sağlanmıştır. 

### Tuples

Birden fazla değerin birleştirilerek tek bir değermiş gibi kullanılmasına olanak sağlayan değişkenlerdir. Tuple tip değişkendeki değerler herhangi bir tipte olabilecekleri gibi bu tuple içerisindeki değerler birbirlerinden farklı tipte olabilirler.


```swift
let http404Error: (Int, String) = (404, "Not Found")
```

Örnekte gördüğümüz gibi hem Int hem de String tipteki değişken tek bir değişken olarak kullanılmıştır. 

Tuple değerlerini harici değişkenlere ayıklamak için;

```swift
let (statusCode, statusMessage) = http404Error
```

şekilde bir kullanıma gidebiliriz.

Tuple içerisinde istemediğimiz değişken varsa o değişkenler için alt çizgi (_) kullanarak atama yapmaktan vazgeçebiliriz.

```swift
let (justTheStatusCode, _) = http404Error
```

Tuple elemanlarına indis numaraları ile erişebiliriz.

```swift
print("The status code is \(http404Error.0)")
// Ekrana "The status code is 404" basacaktır.
print("The status message is \(http404Error.1)")
// Ekrana "The status message is 404" basacaktır.
```

Tuple elemanlarına isim vererek daha sonra tuple daki bu elemanlara bu isimler aracılığı ile erişebiliriz.

```swift
let http200Status:(statusCode: Int, description: String) = (statusCode: 200, description: "OK")

print("The status code is \(http200Status.statusCode)")
// Ekrana "The status code is 200" basacaktır.
print("The status message is \(http200Status.description)")
// Ekrana "The status message is OK" basacaktır.
```

Tuple tipte değişkenler bir fonksiyondan birden fazla değer döndürürken oldukça faydalıdır. 

### Optionals

Swift dilinde herhangi bir değeri olmayan / değer içermeyen değişkenler **nil** ile ifade edilmektedir. Bir değişkenin *nil* değer alabilmesi için optional olarak tanımlanması gerekir. 

Kısaca bir değişkenin ya kendi değerine sahip ya da nil içerebiliyor ise bu değişken opsioneldir. Opsionel değişkenler içerdikleri değerleri wrap eder ve sarmalarlar. 

Bir değişkeni opsionel olarak tanımlamak için değişken tipinden sonra soru işareti (?) koymak yeterlidir. 

```swift
var surveyAnswer: String?
// surveyAnswer varsayılan olarak nil değer içermektedir. 
```

Opsionel değişkenleri kullanmak istediğimizde o değişkenin sarmalanmış wrap edilmiş hali bize gösterilecektir. Bu durumdan kurtarmak istersek unwrapping yapmalı yani değişkeni sarmalanmış halinden kurtarmalıyız.

```swift
var author: String? = "Mustafa Hastürk"
print(author)
// "Optional("Mustafa Hastürk")\n"
```

### If Statements and Forced Unwrapping

Opsionel bir değişkeni nil olup olmadığını kontrol etmek ve sarmalanmış halinden kurtarmak için if kontrol statement kullanabilir ve nil ile karşılaştırabiliriz.

```swift
if author != nil {
    print("author değişkeni String türde değer içermektedir")
}
// "author değişkeni String türde değer içermektedir" yazacaktır.
```

Bir optional değişkenin nil içermediğine emin isek ünlem işareti ile (!) compiler a bu değişkenin nil içermediğine eminim diyerek sarmalanmış halinden çıkaraiblir ve kullanabiliriz.

```swift
print(author!)
// Ekrana "author" değerini basacaktır. 
```

Ancak bu kullanım tehlikelidir. Eğer optional değişken ! işareti ile force edilmesine rağmen nil değer içeriyorsa uygulamamız çökecektir. O yüzden unwrapping yaparken ! işareti tehlikelidir ve kullanmaktan kaçınmak gerekir. 

### Optional Binding

Optional değişkenleri unwrapping etmek yani sarmalanmış halinden çıkarmek ve kullanabilmek için en güvenli yöntem *optinal binding* dir. 

Bu yöntem ile optional değişken *if* kontrol durumu içerisinde başka bir *let* sabitine atanır. Eğer *let* sabiti *nil* değer içeriyorsa if koşulundan çıkılır, içermiyor ise optinal değişkenin değeri ile işlem yapılabilir. 

```swift
var author: String? = "Mustafa Hastürk"

if let authorName = author {
    print("Bu makale yazarı: \(authorName)")
}
else {
    print("'author' değişkeni nil değer içermektedir")
}
```

Ayrıca birden fazla optinal binding tek bir if statement ile handle edilebilir. **where** cümlecikleri ile kompleks karşılaştırmalar yapılaiblir. 

```swift
if let firstNumber = Int("4"), secondNumber = Int("42") where firstNumber < secondNumber {
    print("\(firstNumber) < \(secondNumber)")
}
// Ekrana "4 < 42" basar.
```

### Implicitly Unwrapped Optionals

Bazen geliştirici bir değişkenin değerinin olduğuna her zaman emin olabilir. Eğer bir optional değişkenin her zaman değere sahip olacağına emin isek implicitly unwrapped optionals kullanabiliriz. Bu optional oluştururken soru işareti (?) yerine ünlem işareti (!) kullanmak yeterli olacaktır. 

```swift
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // Ünlem işareti zorunlu 
 
let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // Ünlem işareti zorunlu değil ama koyulabilir.
```

Implicitly unwrapped optionals kullanılırken sarmalanmış halinden çıkarmaya gerek yoktur. Ancak forced unwrapping ile nil olup olmadığını kontrol edebiliriz. 

```swift
if assumedString != nil {
    print(assumedString)
}
// Ekrana "An implicitly unwrapped optional string." basar
```

Optinal binding, *Implicitly Unwrapped Optionals* ile kullanılabilir.

```swift
if let definiteString = assumedString {
    print(definiteString)
}
// Ekrana "An implicitly unwrapped optional string." basar
```

Değişkenin değeri nil olma ihtimali varsa *Implicitly Unwrapped Optionals* kullanmaktan kaçınmak gerekir. Implicitly Unwrapped Optionals kullandığımızda eğer değişkenin değeri nil ise runtime error alınır. 

-------

Yazıda herhangi bir hata ile karşılaşırsanız [pull request][Pull Request] gönderebilir veya yorum olarak bildirebilirsiniz.

Sevgiler... 🎈