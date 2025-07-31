
# Reinforcement Learning ve Bellman Denklemi

## 📌 Reinforcement Learning (RL) Nedir?
- Ajan, ödül/ceza ile öğrenir.
- Amaç: Toplam ödülü maksimize etmek.
- Deneme-yanılma ile öğrenme.

## 🔁 Markov Karar Süreci (MDP)
- **Durum (s)**, **Eylem (a)**, **Ödül (r)**, **Geçişler**, **Politika (π)** içerir.

## 🧠 Q-Öğrenme ve Bellman Denklemi
- **Q(s, a)**: Bu durumda bu eylemin beklenen toplam ödülü.
- **Denklem**:
  ```
  Q(s, a) = R(s, a) + γ * max Q(s', a')
  ```
- Gelecek ödüllere göre bugünkü kararı değerlendirir.

## 💰 Finans/Trading Uygulaması
- Eylemler: Buy / Sell / Hold
- Ödül hemen alınmaz → delayed gratification gerekir.
- Bellman: “Hold” gibi bekleme eylemlerini gelecekteki kârla ödüllendirir.

## 🧮 Örnek:
- γ = 0.9, Q(1, a) = 1.8 ise:
  ```
  Q(0, Wait) = R + 0.9 * 1.8
  ```
  Eğer Q(0, Wait) = 1.62 ise → R = 0

## 🧠 Deep RL
- Durum uzayı büyükse, Q-Tablosu yerine sinir ağı kullanılır.

## 🎯 Sonuç
- Bellman: RL'nin kalbidir.
- Kararları uzun vadeli ödüllere göre şekillendirir.
