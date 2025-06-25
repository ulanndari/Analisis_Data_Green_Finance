# 🌗 Analisis_Data_Green_Finance
### 🌱📊 Apa Itu Green Finance?
   Green finance adalah semua aktivitas keuangan yang bertujuan untuk mendukung pembangunan yang ramah lingkungan dan berkelanjutan. Ini mencakup pembiayaan, investasi, dan kebijakan yang mendorong transisi menuju ekonomi rendah karbon, efisien sumber daya, dan tahan terhadap perubahan iklim. 
Green finance adalah sistem keuangan yang diarahkan untuk mendanai proyek, inisiatif, atau kebijakan yang memiliki manfaat positif bagi lingkungan.
Green Finance adalah pembiayaan proyek yang mendukung keberlanjutan lingkungan. Analisis ini menggabungkan data keuangan dan data lingkungan untuk:
1. Menilai kelayakan finansial proyek hijau
2. Menghitung manfaat lingkungan secara ekonomis
3. Menilai risiko dan potensi insentif dari pasar hijau (green bond, greenium)
### 🔎 Kenapa Green Finance Penting?
1. Mengurangi dampak perubahan iklim 🌍
2. Mendorong pertumbuhan ekonomi hijau dan lapangan kerja hijau 💼
3. Menekan risiko lingkungan dalam portofolio investasi
4. Mendorong inovasi teknologi hijau 🚀
__________________________________________________________________________________________________________________________________________________________________________________________
## 👋 Hai Para Eco Techno Leader, mari berpetualang bersama. saya akan mempublikasikan tugas struktur SELF DIRECTED LEARNING dengan SHARING SESSION and RESEARCH DATA GREEN FINANCE© 2025 bersama Bapak Arry Hutomo
__________________________________________________________________________________________________________________________________________________________________________________________
Di proyek ini kita belajar bareng gimana cara menilai kelayakan proyek hijau, bukan cuma dari sisi duit 💸, tapi juga dari sisi lingkungan 🌍.
Yuk kita bahas dari awal sampai visualisasi datanya!
### 📚 Penjelasan Dataset yang Dipakai
Sebelum masuk ke rumus dan kodingan, yuk kenalan dulu sama jenis-jenis data yang kita pakai. Proyek ini pakai pendekatan yang menyeluruh, gak cuma lihat aspek finansial aja, tapi juga dampak lingkungan, sosial, ekonomi, dan lokasi proyek. Berikut penjelasan singkat tiap bagian:
### 📊 1. Financial Dataset
Ini data utama buat ngitung kelayakan proyek dari sisi uang dan risiko.
1. Investment_Amount - Jumlah uang yang diinvestasikan (Rp)
2. Loan_Interest_Rate - Suku bunga pinjaman (% per tahun)
3. Default_Risk_Score - Skor risiko gagal bayar (0-100)
4. Revenue_Stream - Perkiraan arus kas masuk tahunan dari proyek
5. Green_Bond_Spread - Selisih imbal hasil antara obligasi hijau vs biasa. Nilai negatif = greenium
### Analisis Finansial: GNPV dan Green Bond 💸
Untuk menilai apakah proyek hijau ini **layak dibiayai**, kita hitung sesuatu yang namanya **Green Net Present Value (GNPV)**.
##### 🔍 Apa Itu GNPV?
GNPV itu versi “ramah lingkungan” dari NPV biasa. Bedanya, kita **tambahkan manfaat lingkungan** (seperti pengurangan emisi CO₂) ke dalam arus kas proyek.
**Rumus GNPV:**

$$
\text{GNPV} = \sum_{t=1}^{N} \frac{(CF_t + E_t)}{(1 + r)^t} - I_0
$$

- `CFₜ`: Arus kas masuk tahunan  
- `Eₜ`: Nilai moneter dari manfaat lingkungan  
- `r`: Tingkat diskonto (misal: 5%)  
- `N`: Umur proyek (misal: 10 tahun)  
- `I₀`: Investasi awal proyek
---
##### ⚙️ Contoh Perhitungan Manual

```python
investasi = 100_000_000_000       # I₀
cashflow = 20_000_000_000         # CFₜ
eksternalitas = 5_000_000_000     # Eₜ
r = 0.05                          # diskonto
N = 10                            # umur proyek

gnpv = 0
for t in range(1, N + 1):
    nilai_sekarang = (cashflow + eksternalitas) / ((1 + r) ** t)
    gnpv += nilai_sekarang
gnpv -= investasi

print("GNPV: Rp", round(gnpv))
📤 Output:
GNPV: Rp 93043373230
✅ Proyek ini LAYAK secara finansial dan lingkungan
```

---
##### 🧮 Perhitungan Otomatis untuk Semua Proyek
```python
import pandas as pd

df = pd.read_csv("Financial_Dataset.csv")

umur_proyek = 10
diskonto = 0.05
emisi_ton_per_tahun = 100
harga_karbon = 96000  # berdasarkan pasar karbon Indonesia (2025)

def hitung_gnpv(revenue, investment):
    eksternalitas = emisi_ton_per_tahun * harga_karbon
    gnpv = 0
    for t in range(1, umur_proyek + 1):
        nilai = (revenue + eksternalitas) / ((1 + diskonto) ** t)
        gnpv += nilai
    return round(gnpv - investment, 2)

df["GNPV_Rp"] = df.apply(lambda row: hitung_gnpv(row["Revenue_Stream"], row["Investment_Cost"]), axis=1)
df["Kelayakan"] = df["GNPV_Rp"].apply(lambda x: "Layak ✅" if x > 0 else "Tidak Layak ❌")
```
---
##### 📉 Evaluasi Green Bond Spread (Greenium)
```python
if "Green_Bond_Spread" in df.columns:
    df["Greenium_Status"] = df["Green_Bond_Spread"].apply(lambda x: "Greenium ✅" if x < 0 else "Normal ⚠️")
else:
    df["Greenium_Status"] = "Data Tidak Ada"
```
---
##### Visualisasi GNPV
![image](https://github.com/user-attachments/assets/5acd7a36-7595-40e0-8198-e87a0ff1da8c)


---
##### 📘 Keterangan:
- Greenium artinya investor rela terima imbal hasil lebih rendah karena proyek ini ramah lingkungan 🌱
- Kalau tidak ada greenium, mungkin proyek masih dianggap berisiko atau kurang menarik
##### 📌 Kesimpulan Singkat:
- GNPV bantu kita nilai kelayakan proyek dari sisi finansial + lingkungan
- Green Bond Spread bantu lihat apakah proyek menarik bagi investor hijau
---
##### 📜 Regulasi Terkait & Tips Tambahan

✅ **Regulasi Penting dari OJK (Otoritas Jasa Keuangan):**

- **Taksonomi Hijau Indonesia (THI) Edisi 1.0 (2022)**  
  Merupakan acuan utama untuk mengklasifikasikan proyek sebagai "hijau". Kelayakan finansial (misalnya GNPV positif) harus sejalan dengan kriteria dalam THI.

- **POJK No. 60/POJK.04/2017**  
  Aturan khusus tentang penerbitan *Green Bond*. Termasuk di dalamnya kewajiban pelaporan dampak lingkungan yang relevan dengan perhitungan seperti GNPV.

- **POJK No. 51/POJK.03/2017**  
  Mengatur tentang Rencana Aksi Keuangan Berkelanjutan (RAKB). GNPV dapat digunakan sebagai bagian dari analisis kelayakan proyek dalam laporan ini.
---
##### 💡 **Tips Teknis:**
- **Valuasi Eksternalitas (`Eₜ`)**  
  Untuk menghitung manfaat lingkungan seperti pengurangan emisi CO₂ atau penghematan air, gunakan sumber harga yang kredibel. Contoh: pasar karbon Indonesia, laporan World Bank, atau lembaga lingkungan nasional.

- **Greenium (`Green_Bond_Spread`)**  
  Jika `Green_Bond_Spread` bernilai negatif, artinya proyek mendapat **greenium**. Ini menunjukkan investor bersedia menerima imbal hasil lebih rendah karena percaya proyek tersebut berdampak positif bagi lingkungan.  
  ✔️ Greenium = sinyal bahwa proyek ramah lingkungan = lebih disukai pasar!
---
### 🌿 2. Environmental Dataset
Ngasih gambaran tentang dampak proyek terhadap lingkungan. Cocok buat analisis keberlanjutan.
1. CO2_Reduction - Emisi CO₂ yang dikurangi (ton/tahun)
2. Energy_Output - Energi bersih yang dihasilkan (kWh/tahun)
3. Environmental_Risk_Index - Skor risiko lingkungan proyek (0–100)
4. Konteks_Lingkungan - Ringkasan isu lingkungan di lokasi proyek
5. Peringkat_Dampak - Peringkat keseluruhan dampak proyek (misalnya: Rendah, Sedang, Tinggi)
#### 🔢 Perhitungan CROI (Carbon Return on Investment)
CROI digunakan untuk mengukur efisiensi investasi dalam pengurangan emisi karbon:
# CROI = (Rₜ × P_c × N) / I₀
Keterangan:
- `Rt`: Pengurangan emisi tahunan (`CO2_Emissions_Reduction`)
- `Pc`: Harga karbon per ton CO₂e (dalam Rp)
- `I₀`: Investasi awal (`Investment_Amount`)
- `N`: Umur proyek (`Project_Lifetime`)
  Aturan Praktis:
- CROI > 1 → proyek efisien secara karbon
- CROI < 1 → proyek belum layak secara karbon

---

#### 🧮 Contoh Perhitungan Manual (Python)

```python
investasi_awal = 100_000_000_000
reduksi_emisi_tahunan = 10_000
harga_karbon_per_ton = 500_000
umur_proyek_tahun = 10

croi = (reduksi_emisi_tahunan * harga_karbon_per_ton * umur_proyek_tahun) / investasi_awal
print(f"Hasil CROI = {croi:.2f}")
```
---
#### 🧠 Evaluasi Otomatis Proyek
```python
import pandas as pd

df = pd.read_csv("Environmental_Dataset.csv")

if "Investment_Amount" not in df.columns:
    df["Investment_Amount"] = 100_000_000_000
if "Project_Lifetime" not in df.columns:
    df["Project_Lifetime"] = 10

df["Water_Savings"] = df["Project_ID"].apply(lambda x: 1200 if "PLTS" in x else 800)
df["Biodiversity_Impact_Score"] = df["Environmental_Risk_Index"].apply(lambda x: max(0, min(100, 100 - x)))

harga_karbon = {"rendah": 100_000, "sedang": 500_000, "tinggi": 1_000_000}

for level, harga in harga_karbon.items():
    df[f"CROI_{level}"] = (df["CO2_Reduction"] * harga * df["Project_Lifetime"]) / df["Investment_Amount"]
    df[f"Efisiensi_Karbon_{level}"] = df[f"CROI_{level}"].apply(lambda x: "Efisien" if x > 1 else "Kurang Efisien")

def rekomendasi_dnsh(water, biodiversity):
    if water >= 1000 and biodiversity >= 70:
        return "✅ Layak sebagai proyek hijau (DNSH)"
    elif water >= 800 and biodiversity >= 50:
        return "⚠️ Perlu peningkatan dampak lingkungan"
    else:
        return "❌ Belum memenuhi prinsip hijau"

df["Rekomendasi_DNSH"] = df.apply(
    lambda row: rekomendasi_dnsh(row["Water_Savings"], row["Biodiversity_Impact_Score"]),
    axis=1
)
```
---
#### 📈 Visualisasi Beyond Carbon
![image](https://github.com/user-attachments/assets/d4138d16-d6ad-4955-81bb-125cd2d83005)

---
#### 📜 Regulasi Terkait
- Perpres No. 98 Tahun 2021: Menetapkan Nilai Ekonomi Karbon dan skema perdagangan karbon di Indonesia.
- Taksonomi Hijau Indonesia (THI): Menentukan ambang batas teknis proyek hijau, termasuk validasi berbasis CO2_Emissions_Reduction.
----
### 🧝‍♂️ 3. Social Dataset
Aspek sosial itu penting! Ini data yang menilai apakah proyek bermanfaat atau berisiko buat masyarakat sekitar.
1. Job_Creation - Jumlah pekerjaan yang diciptakan
2. Community_Involvement - Level partisipasi masyarakat (rendah–tinggi)
3. Social_Risk_Flag - Apakah ada potensi konflik sosial (ya/tidak)
#### 🧾 Dataset: `Social_Dataset.csv`
Dataset ini mencakup berbagai indikator sosial dari proyek energi hijau di beberapa wilayah. File berisi kolom-kolom berikut:
| Kolom | Deskripsi |
|-------|-----------|
| `Project_ID` | ID unik tiap proyek |
| `Jobs_Created` | Jumlah lapangan kerja baru yang tercipta |
| `Community_Engagement_Score` | Skor partisipasi masyarakat (0-100) |
| `Access_to_Clean_Energy_Rate` | Persentase rumah tangga yang kini mendapat akses energi bersih |
| `Gini_Coefficient_Impact` | Dampak proyek terhadap ketimpangan ekonomi lokal |
| `Investment_Cost` | Total investasi proyek (Rp) |
| `Social_Benefit_Estimate` | Estimasi manfaat sosial yang dimonetisasi (Rp) |

---

#### 📈 Perhitungan Utama
##### 🔁 SROI (Social Return on Investment)
$$
\text{SROI} = \frac{\text{Social Benefit Estimate}}{\text{Investment Cost}}
$$

- **SROI > 1** → Investasi sosial efisien
- **SROI < 1** → Dampak sosial masih rendah dibanding investasi

---
##### 💸 Monetisasi Dampak Sosial
Monetisasi dilakukan dengan financial proxies, seperti:
- Jobs_Created → dikalikan upah rata-rata tahunan
- Community Engagement → proksi nilai dari pelatihan, pertemuan publik, dll
- Access to Clean Energy → estimasi penghematan biaya energi
- Gini Coefficient Impact → model pengurangan ketimpangan diukur dari redistribusi pendapatan

---

##### 🛑 Evaluasi Risiko Sosial
Proyek dievaluasi berdasarkan:
| Kategori Risiko | Indikator |
|-----------------|-----------|
| Risiko Partisipasi Rendah | `Community_Engagement_Score < 50` |
| Risiko Eksklusi Energi | `Access_to_Clean_Energy_Rate < 60%` |
| Risiko Ketimpangan | `Gini_Coefficient_Impact > 0.05` (worsening inequality) |

📌 Proyek dengan lebih dari 2 risiko tinggi akan ditandai sebagai "⚠️ Risiko Sosial Tinggi"

---
##### 📊 Visualisasi
![image](https://github.com/user-attachments/assets/5ebefd85-c350-4063-bdf0-5cf0ad8e2bf6)
 
##### ✅ Contoh Output SROI

| Project_ID | Jobs_Created | SROI | Risiko_Sosial |
|------------|--------------|------|----------------|
| PLTS_A     | 15           | 1.25 | Rendah          |
| PLTB_B     | 5            | 0.67 | ⚠️ Tinggi        |

---

##### 🚀 Tujuan Proyek

- Mengukur **efisiensi sosial** dari proyek energi hijau
- Menyediakan dasar data untuk pengambilan keputusan berbasis bukti (*evidence-based policy*)
- Mendukung prinsip **Just Energy Transition** di daerah tertinggal dan terpencil

---

##### 🏷 Referensi Regulasi
- **POJK 51/2017**: Keuangan Berkelanjutan
- **SDGs 7, 10, 11**: Energi bersih, pengurangan ketimpangan, komunitas berkelanjutan
---

#### 📈 4. Economic Dataset
Data ini bantu kita melihat dampak ekonomi lokal, termasuk efek berantai dari proyek.
1. Local_Economic_Impact - Indeks kontribusi terhadap ekonomi lokal
2. SME_Inclusion - Apakah proyek melibatkan UMKM? (ya/tidak)
3. Cost_Benefit_Ratio - Rasio antara total manfaat ekonomi dibanding biaya proyek
#### 🗌️ 2.5 Geospatial Dataset
Ini data lokasi buat bantu analisis spasial, misalnya jarak ke pemukiman, atau apakah proyek berada di kawasan rawan bencana.
1. Latitude, Longitude - Titik koordinat lokasi proyek
2. Proximity_to_Village - Jarak ke desa terdekat (km)
3. Disaster_Zone_Flag - Apakah lokasi termasuk zona rawan bencana? (ya/tidak)
#### 📌 Kenapa ini penting?
Karena proyek yang bagus itu gak cuma menghasilkan uang, tapi juga:
1. 🌍 Melindungi lingkungan
2. 👥 Menguntungkan masyarakat
3. 💼 Mendorong ekonomi lokal
4. 📉 Sesuai konteks lokasi
