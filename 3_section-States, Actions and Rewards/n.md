# 📘 Elements of Reinforcement Learning

Bu derste, pekiştirmeli öğrenmenin temel öğeleri olan **state (durum)**, **action (eylem)** ve **reward (ödül)** kavramları açıklanmaktadır.

## 🎮 Örnek: Pong Oyunu

- Oyuncu üç eylemden birini seçer: `up`, `down`, `stay`
- Bu seçimler **action** olarak adlandırılır ve her zaman adımında yapılır (`t`)

## Finansal İşlemlerde Action

Yatırımcı genelde şu üç karardan birini verir:
- `buy` (al)
- `hold` (bekle)
- `sell` (sat)

Bu kararlar da **action** olarak değerlendirilir.

## State (Durum) Nedir?

### Pong’ta:
- Topun ve raketin konumu: `state`

### Piyasada:
- OHLC verileri (Open, High, Low, Close)
- Göstergeler (RSI, MA, momentum, volatilite)
- Farklı zaman ölçeklerinde veriler

> Tüm bu bilgiler, zaman anındaki bir durumu temsil eden `state vector (Sₜ)`'yi oluşturur.

## 📊 Örnek: Tesla - 29 Haziran 2020

- OHLC verisi yeterli değildir.
- Kapanış fiyatındaki değişim, RSI gibi göstergeler kullanılır.
- Daha doğru kararlar için daha zengin bir state gerekir.

## 🧠 İnsan Yatırımcı Benzerliği

- İnsan da piyasayı gözlemler ve karar verir.
- RL sistemleri de benzer şekilde durumu analiz eder ve eylem seçer.

## 🤔 Peki 30 Haziran’da Ne Yapmalı?

- Sistem, `Sₜ` durumuna göre `action` seçecek.
- Karar, bu eylemden alınacak **reward (ödül)** ile ilgilidir.

## 🎯 Reward (Ödül) Nasıl Belirlenir?

- "Buy" yaptıysa ve fiyat arttıysa → pozitif ödül
- Fiyat düştüyse → negatif ödül

> Peki ödül neye göre tanımlanmalı?

## ⏭ Sonraki Adım

> 📌 Bir sonraki derste: **Reward Function Design** (Ödül Fonksiyonu Tasarımı)

## 🧩 Özet Tablosu

| Bileşen | Açıklama |
|--------|----------|
| `State` | Piyasadan algılanan veri (fiyatlar, göstergeler vs.) |
| `Action` | Alınan karar (buy, hold, sell) |
| `Reward` | Eylem sonucunda elde edilen kazanç/kayıp |
