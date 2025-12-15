# BLG-307 Yapay Zeka Sistemleri – 1. Proje Ödevi

## Genetik Algoritma ile Endüstriyel Boya Karışımı Optimizasyonu

**Öğrenci:** Yeşim Ayma  
**Numara:** 2312721002  
**Senaryo:** 2 – Endüstriyel Boya Karışımı  

---

## 📌 Proje Açıklaması

Bu projede **Genetik Algoritma (GA)** kullanılarak, iki farklı pigmentten oluşan endüstriyel bir boya karışımının **renk kalitesi skorunu maksimize edecek** en uygun oranlarının bulunması amaçlanmıştır.

Problem, doğrusal olmayan bir amaç fonksiyonu ve belirli kısıtlar içerdiği için klasik optimizasyon yöntemleri yerine **genetik algoritma** tercih edilmiştir. Genetik algoritma sayesinde çözüm uzayı popülasyon tabanlı olarak taranmış ve küresel optimum çözüme ulaşılmıştır.

---

## 🏭 Senaryo: Endüstriyel Boya Karışımı

Bir endüstriyel boya fabrikasında, iki farklı pigmentin belirli oranlarda karıştırılmasıyla **ideal renk yoğunluğunun** elde edilmesi amaçlanmaktadır.

Kullanılan pigmentler:
- **Pigment A (x₁)**
- **Pigment B (x₂)**

Amaç, verilen kısıtlar altında **renk kalitesi puanını maksimize eden** pigment oranlarını bulmaktır.

---

## 🎯 Amaç Fonksiyonu

Bu proje kapsamında kullanılan amaç fonksiyonu aşağıdaki gibidir:

\[
y = 5x_1 + 2x_2 - x_1 x_2
\]

Bu fonksiyon **maksimize edilmektedir**.

---

## 🔢 Değişkenler

- **x₁:** Pigment A oranı (%)  
- **x₂:** Pigment B oranı (%)  

---

## ⚙️ Kısıtlar

- \(x_1 + x_2 = 100\)  (Karışım toplamı %100 olmalıdır)  
- \(x_1 \geq 30\)  (Pigment A en az %30 kullanılmalıdır)  
- \(0 \leq x_1, x_2 \leq 100\)

---

## 🧬 Kullanılan Yöntem: Genetik Algoritma

Bu projede optimizasyon problemi **Genetik Algoritma (GA)** kullanılarak çözülmüştür.  
Genetik algoritma, biyolojik evrim süreçlerinden esinlenen, popülasyon tabanlı bir optimizasyon yöntemidir.

Algoritma aşağıdaki temel adımlardan oluşmaktadır:

1. Başlangıç popülasyonunun oluşturulması  
2. Uygunluk (fitness) değerlerinin hesaplanması  
3. Seçilim (selection)  
4. Çaprazlama (crossover)  
5. Mutasyon (mutation)  
6. Elitizm ile en iyi bireyin korunması  

---

## 👤 Birey Temsili

Her birey bir boya karışımını temsil edecek şekilde aşağıdaki biçimde tanımlanmıştır:


Bu yaklaşım sayesinde algoritma boyunca **kısıt ihlali oluşması engellenmiştir**.

---

## 🧪 Başlangıç Popülasyonu

Başlangıç popülasyonu, kısıtlara uygun olacak şekilde **rastgele bireyler** oluşturularak elde edilmiştir.

- Popülasyon büyüklüğü: **30**
- Pigment A oranı: **%30 – %100** aralığında

Bu sayede çözüm uzayının farklı bölgeleri başlangıçta keşfedilebilmiştir.

---

## 🎯 Uygunluk (Fitness) Fonksiyonu

Her bireyin uygunluk değeri, doğrudan verilen amaç fonksiyonu kullanılarak hesaplanmıştır:

\[
Fitness = 5x_1 + 2x_2 - x_1x_2
\]

Amaç, bu fonksiyonun değerini **maksimize eden** pigment oranlarını bulmaktır.

---

## 🏆 Seçilim (Selection)

Bu projede **Rank Selection (Sıralama Tabanlı Seçilim)** yöntemi kullanılmıştır.

- Bireyler fitness değerlerine göre sıralanır
- Seçilme olasılığı, bireyin **sıralamadaki konumuna** bağlıdır
- Fitness değerlerinin negatif olabilme ihtimali nedeniyle bu yöntem tercih edilmiştir

Bu yöntem, iyi bireylerin seçilme ihtimalini artırırken popülasyon çeşitliliğini korur.

---

## 🔀 Çaprazlama (Crossover)

Çaprazlama aşamasında **tek noktalı çaprazlama** yöntemi uygulanmıştır.

- Çaprazlama noktası `x1` olarak belirlenmiştir
- Ebeveynlerin genetik bilgileri değiş tokuş edilerek iki yeni birey üretilmiştir
- Çaprazlama oranı: **%80**

Çaprazlama sonrası bireyler `repair` fonksiyonu ile kısıtlara uygun hale getirilmiştir.

---

## 🧬 Mutasyon (Mutation)

Mutasyon işlemi, popülasyon çeşitliliğini artırmak amacıyla uygulanmıştır.

- Mutasyon oranı: **%20**
- Sadece `x1` değeri üzerinde küçük rastgele değişiklikler yapılmıştır
- Mutasyon sonrası kısıtlar tekrar uygulanmıştır

Bu sayede algoritmanın erken yakınsamaya girmesi önlenmiştir.

---

## ⭐ Elitizm

Her nesilde en iyi birey **doğrudan yeni nesle aktarılmıştır**.

Bu yaklaşım sayesinde:
- En iyi çözümün kaybolması engellenmiştir
- Algoritmanın kararlılığı artırılmıştır

---

## 📈 Yakınsama Grafiği

Algoritmanın çalışması sırasında her nesilde elde edilen en iyi fitness değeri kaydedilmiştir.  
Bu değerler kullanılarak çizilen yakınsama grafiği, genetik algoritmanın **birkaç nesil içinde küresel optimuma ulaştığını** göstermektedir.

---

## 🏁 Elde Edilen Sonuçlar

Genetik algoritma çalıştırıldığında elde edilen en iyi çözüm aşağıdaki gibidir:

- **Pigment A (x1): %100**
- **Pigment B (x2): %0**
- **Maksimum renk kalitesi skoru: 500**

## ▶️ Kurulum ve Çalıştırma Yönergeleri

Bu proje Python ve Jupyter Notebook ortamında çalıştırılmak üzere hazırlanmıştır.

### Gerekli Yazılımlar
- Python 3.x
- Jupyter Notebook
- Matplotlib

### Gerekli Kütüphanelerin Kurulumu
Aşağıdaki komut ile gerekli kütüphaneler kurulabilir:

```bash
pip install matplotlib


## 🧠 Sonuç ve Değerlendirme

Bu projede genetik algoritmanın kısıtlı bir optimizasyon probleminde başarıyla uygulanabileceği gösterilmiştir.  
Elde edilen sonuçlar, hem genetik algoritmanın çalışma mantığı hem de problemin matematiksel analizi ile tutarlıdır.







