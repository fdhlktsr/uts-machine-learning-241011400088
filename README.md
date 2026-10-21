# UTS Machine Learning – Linear & Logistic Regression

- **Nama  :** Muh Fadhl Kautsar
- **NIM   :** 241011400088
- **Kelas :** 05TPLM001 Reg B

## Ringkasan hasil

### Bagian A – Linear Regression (`Ads_Data.csv`, test_size 0.2)
- Persamaan (normal equation): **ŷ = 28,9055 + 9,0778 · BiayaIklan**
- Setiap tambahan biaya iklan 1 juta Rp diikuti kenaikan rata-rata penjualan sekitar 9,08 juta Rp.

| Metrik | Training | Testing |
|---|---|---|
| MAE | 4,8456 | 3,0449 |
| MSE | 42,1471 | 12,9576 |
| RMSE | 6,4921 | 3,5997 |
| R² | 0,9296 | 0,9830 |

- Gradient descent (5000 iterasi): learning rate 0,001 terlalu lambat (MSE 60,70), 0,02 sama dengan normal equation, 0,1 divergen (loss menjadi `inf`/`nan`).
- Prediksi penjualan: biaya iklan 4,5 juta → 69,76; 7 juta → 92,45; 12 juta → 137,84 (ekstrapolasi, kurang bisa dipercaya).

### Bagian B – Logistic Regression (`Email_Data.csv`, test_size 0.25)
- P(Spam) = σ(−13,4546 + 1,2446 · JumlahLink + 1,0172 · KataPromo)
- Hasil pada data testing (threshold 0,5): **Accuracy 0,8667**, Precision 1,00, Recall 0,75, F1 0,8571 (TN=7, FP=0, FN=2, TP=6).
- Eksperimen threshold: 0,3 → precision 0,857 / recall 0,75; 0,5 → 1,00 / 0,75; 0,7 → 1,00 / 0,625. Threshold yang dipilih: **0,5**.
- Prediksi email baru (threshold 0,5): E1 bukan spam, E2 bukan spam, E3 spam, E4 spam.

### Bagian C dan Bonus
- Jawaban konsep (C1–C5) ada di notebook.
- Bonus: Linear Regression sama persis dengan scikit-learn. Logistic Regression mirip dengan scikit-learn default (regularisasi L2, C=1.0) tetapi berbeda dari versi tanpa regularisasi (C=1e10); penjelasannya ada di notebook.