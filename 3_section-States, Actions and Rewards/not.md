# Reinforcement Learning Öğeleri

**Reinforcement Learning (Pekiştirmeli Öğrenme)** sürecindeki üç temel öğe:
- **State (Durum)**
- **Action (Eylem)**
- **Reward (Ödül)**

## 🕹️ Örnek: Pong Oyunu

1980'li yılların meşhur oyunu **Pong** üzerinden örnek verilmiştir.

- **Eylemler (Actions)**: Yukarı, aşağı veya sabit kal.
- Her eylem belirli bir **zaman adımında (T)** gerçekleştirilir.

Bu örnekten yola çıkarak ticaret (trading) uygulamasına geçilir:

- Bir yatırımcı genellikle üç karar alabilir: **Buy (Al), Hold (Tut), Sell (Sat)**.
- Bu kararlar da her zaman adımında bir eylemdir.

---

## 🧾 State (Durum) Nedir?

- **Pong'da**: Topun ve raketin pozisyonu = O anki **durum**.
- **Finansal piyasalarda**: Piyasa verileri (örneğin grafik görünümü) = Durum.

### Örnek:

29 Haziran 2020 tarihinde Tesla'nın **OHLC (Open, High, Low, Close)** verileri alınır.

Ancak yalnızca bu sayılar yeterli **durum bilgisi** sağlamaz. Daha anlamlı bir yapı gerekir.

---

## 🔍 Daha İyi Durum (State) Bilgisi Nasıl Oluşturulur?

### Basit yaklaşım:
- Sadece son kapanış fiyatı ile bir önceki kapanış fiyatı karşılaştırılır.

### Daha gelişmiş yaklaşım:
- Son N kapanış fiyatı dikkate alınır.
- Teknik göstergeler (indikatörler) eklenir:
  - **Hareketli Ortalamalar (Moving Averages)**
  - **RSI (Relative Strength Index)**
  - **Momentum**
  - **Volatilite**

---
## 🎯 Action (Eylem) Nedir?

### Pong’ta:
- Kullanıcının yaptığı hareket: yukarı, aşağı, bekle

### Finansal İşlemlerde:
- Yatırımcının her zaman adımında verebileceği kararlar:
  - `Buy` (Al)
  - `Hold` (Bekle)
  - `Sell` (Sat)

### Detaylar:
- Her `state` (durum) gözlemlendiğinde, sistem bir `action` seçer.
- Seçilen bu eylem, yatırım sonucunu belirler.
- Hangi eylemin seçileceği, geçmiş deneyimlerden ve o andaki `state`'ten etkilenir.

---

### Zaman dilimi farklılığı:
- RSI indikatörü hem dakikalık, hem saatlik, hem de günlük grafikte uygulanabilir.
- Bu sayede farklı zaman ölçeklerinden bilgi elde edilir.

Tüm bu bilgiler birleştirilerek **zaman t'deki State vektörü (Sₜ)** oluşturulur.

---

## 👤 İnsan Yatırımcı Analojisi

Bu durum (state), **insan yatırımcının piyasaya bakıp bir karar vermesi** gibi çalışır.

- O anki fiyat, göstergeler ve geçmiş tecrübeye dayanarak karar verilir.

---

## 📈 Ödül (Reward) Ne Zaman ve Nasıl Belirlenir?

> Peki 30 Haziran'da yatırımcı ne yapmalı?

Verilecek kararın (action) sonucunda **ödül (reward)** elde edilir.

Ama:

- Bu ödül, yalnızca **gelecekte** belli olur.
- Örneğin: Hisse senedini şimdi almak → İleride fiyat artarsa ödül, düşerse ceza doğar.

### Soru:
> "Bir aksiyonun ödülü nasıl belirlenmeli?"

Bu soru, **ödül fonksiyonu tasarımı (reward function design)** kavramına götürür.  
Bu konu bir sonraki video dersinde ele alınacaktır.

---

## 🧠 Sonuç

- **Action** = Her adımda yapılacak seçim (al, tut, sat gibi).
- **State** = O anki piyasa bilgisi ve göstergeler.
- **Reward** = Eylemin uzun vadede getirdiği sonuç.

Bu üç kavram Reinforcement Learning’in temelini oluşturur.  
Her karar, geçmiş durumlara ve kazanılan/kaçırılan ödüllere göre öğrenilir ve iyileştirilir.

---

