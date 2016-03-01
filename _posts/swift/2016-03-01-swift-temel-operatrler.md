---
layout: post
title: S02 - Swift Temel Operatörler
modified:
categories: swift
excerpt:
tags: [swift, operatörler, operators]
image:
  feature:
date: 2016-03-01T21:47:22+02:00
comments: true
---

Operatörler sayesinde matematiksel ve mantıksal birçok işlemi programlama diline yaptırabiliriz. Swift programlama dili C dilindeki çoğu standart operatörü desteklemektedir ve hataların önüne geçmek için birçok operatörün gelişmiş halini geliştiriciye sunmaktadır. 

### Terminology / Terminoloji

Operatörler üç ana başlık altında toplanmaktadırlar:

* Unary Operators: Tekil operatörlerdir ve tek bir hedefleri vardır. prefix ve postfix olmak üzere operatörün önüne veya arkadasına gelebilir. 
* Binary Operators: İkili operatörlerdir ve iki hedefi vardır. infix olarak kullanılır ve iki operatör arasında yer alır. 
* Ternary Operators: Üçlü operatördür ve üç hedefi vardır. Swift dilinde tıpkı C dilinde olduğu gibi bir tane ternary operatör bulunmaktadır. **Ternary Conditional Operator** (a ? b : c).

Operatörlerin etkilediği değerlere **operand** denir. '1' + '2' ifadesinde '+' *binary operator*, '1' ve '2' ise birer *operand* dır. 

### Assignment Operator / Atama Operatörü 

Atama operatörü ile bir değişkene ilk değeri atanabilir veya varolan bir değişkenin değeri değiştirilebilir.

```swift
let y = 10
var x = 5
x = y
// x şu an 10 değerine sahiptir
```

Tuple değişkendeki elemanları ayrı değişkenlere atamak için atama operatörü kullanabiliriz.

```swift
let (x, y) = (1, 2)
// x 1 değerini, y ise 2 değerini taşır
```

C ve Objective-C dilinin aksine Swift dilindeki atama operatörü geriye herhangi bir değer döndürmez. 

```swift
if x = y {
    // Bu kod parçası geçerli değildir çünkü x = y geriye değer döndürmez
}
```

Bu yaklaşım sayesinde atama operatörü olan (=) ile, karşılaştırma operatörünün (==) karıştırılması veya yanlışlıkla karşılaştırma operaötörü yerine atama operatörü kullanılması önlenmiştir. Swift bu tarz hataları daha kodlama bitmeden size bildirmektedir. 

### Arithmetic Operators / Aritmetik Operatörleri

Swift temel bütün matematiksel operatörleri desteklemektedir. 

* Ekleme (+)
* Çıkarma (-)
* Çarpma (*)
* Bölme (/)

C ve Objective-C dilinde yer alan aritmetiksel operatörlere kıyasla Swift aritmetik operatörleri değerlerin **overflow** olmasına varsayılan olarak izin vermemektedir. Bu davranışı elde etmek için Swift dilinde yer alan [overflow operatörleri][Overlow Operators] kullanılmalıdır. 

Ekleme operatörü ayrıca String değişkenleri birleştirmek için kullanılabilir.

```swift
"Mustafa, " + "Hastürk"  // "Mustafa Hastürk"
```

#### Remainder Operator / Kalan Bulma Operatörü

Diğer dillerde mod alma operaötörü olarak tanımlanan bu operatör davranışsal olarak Swift dilinde kalanı bulmaya yaramaktadır. 

```
a = (b x some multiplier) + remainder
```

Yukarıda gösterilen formül yardımı ile `a % b` bize *remainder* dönecektir. 

```swift
9 % 4    // 1 sonucunu dönecektir
-8 % 3   // -2 sonucunu dönecektir
```

#### Floating-Point Remainder Calculations / Kayan Noktalı Sayı Kalan Hesaplama

C ve Objective-C dilinin aksine Swift remainder operatörü kayan noktalı sayılar üzerinde de çalışmaktadır. 

```swift
8 % 2.5   // 0.5 sonucunu dönecektir
```

### Unary Minus Operator / Tekil Eksi Operatörü

Negatif sayıları tanımlarken kullanacağımız tekil operatördür. 

```swift
let three = 3
let minusThree = -three       // minusThree -3 değerine sahiptir
let plusThree = -minusThree   // plusThree 3 değerine sahiptir (-)(-)(3) = +3
```

### Unary Plus Operator / Tekil Artı Operatörü

Tekil artı operatörü kısaca operandının değerine etki etmeden geri döndürür. 

let minusSix = -6
let alsoMinusSix = +minusSix  // alsoMinusSix -6 değerine sahiptir

Tekil artı operatörü mantıksal olarak hiçbir iş yapmasa da tekil eksi operaötü ile simetrik olarak kullanılabilir.

### Compound Assignment Operators / Birleşik Atama Operatörleri

Tıpkı C dilinde olduğu bir değişkene, kendi değeri ile birlikte başka bir değer üzerinden işlem sonucu atanabilir. 

```swift
var a = 1
a += 2
// a 3 değerine sahiptir
```

Yukarıdaki işlem `a = a + 2` kod parçası ile aynı işlemi yapacaktır. 

Birleşik atama operatörü geriye herhangi bir değer döndürmez.

### Comparison Operators / Karşılaştırma Operatörleri

Swift, C dilinde yer alan standart karşılaştırma operatörlerinin hepsini destekler. 

* Eşittir (a == b)
* Eşit değildir (a != b)
* Büyüktür (a > b)
* Küçüktür (a < b)
* Büyük veya eşittir (a >= b)
* Küçük veya eşittir (a <= b)


### Ternary Conditional Operator

Swift dilinde yer alan üçlü tek operatördür. Anlamsal olarak, koşul doğru ise yapılacaklar ve yanlış ise yapılacakları tek satırda ifade etmek için kullanılır. 

```swift
mantıksal_ifade ? doğru_ise_yap : yanlış_ise_yap
```

Bir örnekte görmek gerekir ise;

```swift
let contentHeight = 40
let hasHeader = true
let rowHeight = contentHeight + (hasHeader ? 50 : 20)
// rowHeight 90 değerine sahiptir
```

Örnekte hasHeader değişkeni true olduğundan ? işareti ile : işareti arasındaki değer dönmüştür.

Yukarıdaki örneğimizi daha uzun bir şekilde if / else kontrol akışları ile de yazabiliriz.

```swift
let contentHeight = 40
let hasHeader = true
var rowHeight = contentHeight
if hasHeader {
    rowHeight = rowHeight + 50
} else {
    rowHeight = rowHeight + 20
}
// rowHeight 90 değerine sahiptir
```

if / else kontrol akışları sonraki yazılarda detaylı olarak incelenecektir. 
{: .notice}


### Nil Coalescing Operator / Nil Birleştirme Operatörü

Anlamsal olarak **opsiyonel** *a* değeri alır ve bu opsiyonel değer *nil* değilse **a** nın değerini döndürür eğer *a*, **nil** ise varsayılan değer olan **b** döner. 

```swift
(a ?? b) // şeklinde kullanılan bir operatördür
```

Eğer opsiyonel değişken olan "*a*" nil değilse "*b*" değeri hiç hesaplanmaz. Bu **short-circuit evaluation** olarak bilinir.

Ternary conditional operatörü ile göstermek gerekirse:

```swift
a != nil ? a! : b
```

Anlamayı kolaylaştırmak adına if / else kontrol akışı ile göstermek gerekirse:

```swift
var a: String?
let b = "Mustafa Hastürk"

var result: String

if a != nil {
    result = a!
}
else {
    result = b
}
```

Bu üç gösterim birbirinin dengidir. 

### Range Operators / Aralık Operatörleri 

Swift değer aralıklarını ifade etmek için iki farklı aralık operatörü sunmaktadır. 

#### Closed Range Operator / Kapalı Aralık Operatörü 

Verilen sınırların ikiside aralık içerisindedir ve döngüde sayılırlar. 

````swift
for index in 1...5 {
    print("\(index) çarpı 5 = \(index * 5)")
}
// 1 çarpı 5 = 5
// 2 çarpı 5 = 10
// 3 çarpı 5 = 15
// 4 çarpı 5 = 20
// 5 çarpı 5 = 25
```

for - in döngüleri kontrol akışlarında detaylı olarak incelenecektir.
{: .notice}


#### Half-Open Range Operator / Yarı Açık Aralık Operatörü

Verilen sınırlar arasında son sınır aralık değerlerinde yoktur. 

```swift
let names = ["Mustafa", "Hastürk", "Brian", "Jack"]
let count = names.count
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
// 1. kişi Mustafa aradı
// 2. kişi Hastürk aradı
// 3. kişi Bria aradı
// 4. kişi Jack aradı
```

for - in döngüleri kontrol akışlarında detaylı olarak incelenecektir.
{: .notice}

### Logical Operators / Mantıksal Operatörler

Boolean değerleri birleştirmek veya değiştirmek için mantıksal operatörlerden faydalanılır. C tabanlı dillerde yer alan üç adet mantıksal operatör Swift dili tarafından desteklemektedir.

* Mantıksal DEĞİL (!a)
* Mantıksal VE (a && b)
* Mantıksal VEYA (a || b)

#### Logical NOT Operator / Mantıksal DEĞİL Operatörü

Anlamsal olarak bir boolean değerin içerdiği değeri tersine çevirmektedir ve operandın önünde (prefix) yer almaktadır. 

```swift
let allowedEntry = false
if !allowedEntry {
    print("ACCESS DENIED")
}
// Ekrana "ACCESS DENIED" basar
```

#### Logical AND Operator / Mantıksal VE Operatörü

Anlamsal olarak etkilediği operandların ikisi de true ise true, herhangi biri false ise sonuç olarak false döndürmektedir. 

```swift
let enteredDoorCode = true
let passedRetinaScan = false
if enteredDoorCode && passedRetinaScan {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Ekrana "ACCESS DENIED" basar
```

#### Logical OR Operator / Mantıksal VEYA Operatörü

Anlamsal olarak etkilediği operandlardan herhangi biri true ise geriye true, operandların ikisi de false ise geriye false değer döndürmektedir.

```swift
let hasDoorKey = false
let knowsOverridePassword = true
if hasDoorKey || knowsOverridePassword {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Ekrana "Welcome!" basar
```

#### Combining Logical Operators / Mantıksal Operatöreri Birleştirmek

Birleşik ifadeler elde etmek için mantıksal operatörleri birleştirerek kullanmak mümkündür. 

```swift
if enteredDoorCode && passedRetinaScan || hasDoorKey || knowsOverridePassword {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Ekrana "Welcome!" basar
```

Örneğimizde ilk iki ifade false olduğundan (enteredDoorCode && passedRetinaScan) değeri false dönecektir. "hasDoorKey" değişkeni de false değere sahiptir ancak "knowsOverridePassword" değişkeni true değere sahip olduğundan sonuç itibari ile false || true ifadesi true dönecektir. 

Swift mantıksal operatörleri sol birleşmeli (left-associative) operatörlerdir. Birleşik ifadelerde kontrol soldan sağa gitmektedir. 
{: .notice}

#### Explicit Parentheses

Kompleks ifadeler tanımlarken işlem önceliklerini tanımlamak tıpkı matematikte olduğu gibi parantezlerden faydalanabiliriz. Kompleks karşılaştırma ifadelerini daha kolay okunabilir yapmak için parantezler kullanmak güzel olacaktır. Kullandığımız parantezler kompleks ifademizin sonucunu değiştirmese bile kodun okunabilir olması kodun kısa olmasından çoğu zaman daha önemlidir. 

```swift
if (enteredDoorCode && passedRetinaScan) || hasDoorKey || knowsOverridePassword {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Ekrana "Welcome!" basar
```

[Overlow Operators]: https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/AdvancedOperators.html "Swift Overlow Operatörleri"
