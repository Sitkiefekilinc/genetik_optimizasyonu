# Akıllı Depo Raf Optimizasyonu (Genetik Algoritma)

Bu proje, bir lojistik firmasının **Akıllı Depo** sistemindeki raf yerleşimini optimize etmek amacıyla geliştirilmiştir. **Genetik Algoritma (GA)** kullanılarak, belirli kısıtlar altında depo verim puanını maksimize eden en uygun raf yüksekliği ($x_1$) ve derinliği ($x_2$) hesaplanmaktadır.

## Proje Amacı ve Senaryo

Lojistik firması, maliyetleri düşürmek ve taşıma verimini artırmak istemektedir. Problem matematiksel olarak şu şekilde modellenmiştir:

* **Amaç Fonksiyonu (Verim Puanı):**
    $$f(x) = 4x_1 + 3x_2 - 0.5x_1x_2$$
* **Değişkenler:**
    * $x_1$: Raf Yüksekliği (2m - 6m arası)
    * $x_2$: Raf Derinliği (1.5m - 4m arası)
* **Kısıtlar:**
    * $x_1 + x_2 \le 8$ (Depo tavan yüksekliği sınırı)
    * $x_2 \ge 1.5$ (Minimum derinlik sınırı)

## Kullanılan Algoritma Mimarisi

Bu projede **Gerçel Değer Kodlamalı (Real-value coded)** bir Genetik Algoritma tasarlanmıştır. Kullanılan yöntemler şunlardır:

* **Seçilim (Selection):** Popülasyon çeşitliliğini korumak için **Turnuva Seçimi (Tournament Selection)** kullanılmıştır.
* **Çaprazlama (Crossover):** Sayısal genler için **Aritmetik Çaprazlama** yöntemi uygulanmıştır.
* **Mutasyon (Mutation):** Yerel tuzaklardan kurtulmak için **Gaussian Mutasyon** uygulanmış ve sınırlar `clamping` yöntemi ile korunmuştur.
* **Ceza (Penalty) Fonksiyonu:** Kısıtları ihlal eden bireylerin uygunluk puanları (Fitness) düşürülerek, çözümün geçerli sınırlar içine çekilmesi sağlanmıştır.
* **Elitizm:** Her neslin en iyi bireyleri korunmuştur.

## Kurulum ve Çalıştırma

Projeyi kendi bilgisayarınızda çalıştırmak için aşağıdaki adımları izleyebilirsiniz.

### 1. Gereksinimler
Proje Python 3 üzerinde çalışmaktadır. Gerekli kütüphaneleri yüklemek için:

```bash
pip install numpy matplotlib
```

### 2. Çalıştırma
Jupyter Notebook dosyasını açarak tüm hücreleri sırasıyla çalıştırınız:

``` bash
jupyter notebook Project.ipynb
```

## Dosya Düzeni
```
.
├── Project.ipynb       # Tüm kodları ve analizleri içeren ana proje dosyası
├── README.md           # Proje dökümantasyonu ve açıklamalar
```
