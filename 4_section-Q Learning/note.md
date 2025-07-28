# Q Tabloları Oluşturma ve Bellman Denklemi

## Hedef
- **Bellman denklemini** açıklamak.
- **Q tabloları (state-action tables)** oluşturabilmek.

## Marshmallow Örneği ile Açıklama

### Kurgu
Çocuk ya **şimdi marshmallow yer (action 1)** ya da **beklerse iki marshmallow kazanır (action 2)**.

### R (Reward) Tablosu
- İki sütun var: **Eat** ve **Wait**
- **Herhangi bir anda yemek → 1 puan**
- **Son ana kadar beklemek → 2 puan**
- Başlangıçta, “wait” eylemi için çoğu satırda ödül **0** (çünkü hemen ödül alınmaz).
- Sadece son adıma yakınken "wait" için **gerçek ödül = 2** olur.

### Problem
- R tablosunda sadece doğrudan ödüller yer alır.  
  → Ara adımların getirisi bilinmez.  
  → Eğer sadece R’ye bakarsak, **nerede ne yapılması gerektiği anlaşılamaz.**


## Çözüm: Bellman Denklemi

### Denklem
\[
Q(s, a) = R(s, a) + \gamma \cdot \max Q(s', a')
\]

### Terimler
- **S** → Şu anki durum (state)
- **A** → Mevcut eylemler kümesi
- **I** → Bu kümeden seçilen belirli bir eylem
- **R** → Ödül tablosu (doğrudan kazançlar)
- **Q** → Öğrenilen Q tablosu (geçmiş + tahmini ödüller)
- **γ (gamma)** → Öğrenme oranı (gelecekteki ödüllere ne kadar önem verdiğimizi belirler)

#### Gamma’nın Etkisi
- **γ = 0** → Q = R olur, yani **öğrenme yoktur**
- **γ > 0** → Gelecekteki kazançlar hesaba katılır → **Öğrenme başlar**, çünkü Q zamanla değişir.

---

## Nasıl Uygulanır?

1. **Son adımdan başlanır** (örnekte 7. dakika).
   - Burada “wait” aksiyonu ile **2 puan** alındığı bilinir.
   - Yani: Q(7, wait) = 2

2. **Önceki adıma geri gidilir (6. dakika):**
   - R(6, wait) = 0 (çünkü bu adımda doğrudan ödül yok)
   - Q(6, wait) = R(6, wait) + γ × max Q(7, a)
   - max Q(7, a) = 2 (en iyi sonraki adım)
   - γ = 0.9  
     → Q(6, wait) = 0 + 0.9 × 2 = **1.8**

3. **Bu işlem geriye doğru tüm zaman adımlarında tekrar edilir.**
   - Yani Q tablosu **adım adım doldurulur.**

---

## Klasik RL vs Derin RL (Deep RL)

- **Klasik RL:**  
  - Q değerleri **bir tablo (Q-table)** ile tutulur.  
  - Tablo büyüdükçe hesaplama zorlaşır.

- **Derin RL:**  
  - Q değerlerini **yapay sinir ağı** öğrenir ve tahmin eder.  
  - Büyük durum-aksiyon uzaylarında daha etkili olur.
