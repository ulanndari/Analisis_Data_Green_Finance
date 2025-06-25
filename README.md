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
# 📊 1. Financial Dataset
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
##### Visualisasi GNPV
![image](https://github.com/user-attachments/assets/5acd7a36-7595-40e0-8198-e87a0ff1da8c)
Grafik ini menunjukkan nilai GNPV untuk berbagai proyek energi terbarukan, seperti PLTS (Pembangkit Listrik Tenaga Surya) dan PLTM (Pembangkit Listrik Tenaga Minihidro) dari seluruh Indonesia.
##### ✅ Apa itu GNPV?
GNPV adalah nilai bersih proyek dengan mempertimbangkan manfaat lingkungan (seperti pengurangan emisi karbon) dan manfaat ekonomi jangka panjang. Jika GNPV > 0, maka proyek tersebut:
- Layak secara finansial
- Memberikan dampak lingkungan yang positif
##### 📈 Penjelasan Grafik:
- **Sumbu Y (vertikal):** Kode proyek (misalnya: PLTS-NTB-001)
- **Sumbu X (horizontal):** Nilai GNPV dalam Rupiah
- **Warna batang:** Menunjukkan besar kecilnya GNPV
##### 🔍 Kesimpulan:
- Semua proyek memiliki GNPV positif → berarti layak dan hijau 🌱
- Nilai GNPV antar proyek hampir sama (sekitar Rp70 juta)
- Cocok untuk masuk dalam program pembiayaan hijau (green finance)
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

# 🌿 2. Environmental Dataset
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
#### 📈 Visualisasi Beyond Carbon
![image](https://github.com/user-attachments/assets/d4138d16-d6ad-4955-81bb-125cd2d83005)
Grafik ini menunjukkan dua aspek penting dari proyek energi hijau yang sering terlupakan, yaitu:

1. **Penghematan Air (Water Savings)**
2. **Skor Dampak Terhadap Keanekaragaman Hayati (Biodiversity Score)**

---

### 💧 Apa yang Ditampilkan Grafik?

- **Batang biru (Water Savings):** Jumlah air yang berhasil dihemat oleh masing-masing proyek (dalam liter).
- **Garis oranye dengan titik (Biodiversity Score):** Skor dari 0–100 untuk menilai dampak proyek terhadap keanekaragaman hayati.
- **Garis hijau putus-putus:** Ambang batas aman **DNSH (Do No Significant Harm)** yaitu skor ≥ 70.
- **Garis merah putus-putus:** Ambang minimum mutlak yaitu skor ≥ 50 (di bawah ini dianggap berisiko tinggi terhadap lingkungan).

---

### 🧐 Kesimpulan dari Grafik

- **Penghematan Air (Water Savings):**
  - Mayoritas proyek berhasil menghemat air antara **800–1200 liter**.
  - Proyek seperti `PLTS-NTT-001`, `PLTS-JATIM-001`, dan `PLTS-NTB-001` termasuk paling efisien dalam konservasi air.

- **Skor Keanekaragaman Hayati (Biodiversity Score):**
  - Hanya sedikit proyek yang **lulus ambang DNSH (≥70)**.
  - Beberapa proyek memiliki skor **di bawah 50**, yang artinya berisiko tinggi terhadap biodiversitas.
  - Proyek `PLTS-JABW-001` memiliki skor tertinggi dan paling ramah lingkungan secara ekosistem.

---

#### 📌 Mengapa Ini Penting?
✅ Analisis **Beyond Carbon** membantu memastikan bahwa proyek tidak hanya baik dalam mengurangi emisi karbon, tetapi juga:

- Menghemat sumber daya air
- Melindungi flora dan fauna lokal

Dengan mempertimbangkan aspek ini, kita mendorong proyek yang benar-benar **berkelanjutan secara menyeluruh**.

---
#### 📜 Regulasi Terkait
- Perpres No. 98 Tahun 2021: Menetapkan Nilai Ekonomi Karbon dan skema perdagangan karbon di Indonesia.
- Taksonomi Hijau Indonesia (THI): Menentukan ambang batas teknis proyek hijau, termasuk validasi berbasis CO2_Emissions_Reduction.
----

# 🧝‍♂️ 3. Social Dataset
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

- **Sumbu X:** Kode proyek (contoh: PLTS-NTT-001, PLTM-KALB-001)
- **Sumbu Y:** Nilai SROI
- **Garis merah putus-putus:** Ambang kelayakan minimum yaitu **SROI = 1**
- **Batang hijau:** Nilai SROI aktual masing-masing proyek

---

##### ✅ Hasil Analisis:

- Semua proyek memiliki **SROI jauh di atas 1**, artinya memberikan dampak sosial yang tinggi.
- Proyek `PLTS-JATIM-001` dan `PLTS-SULS-001` mencetak nilai tertinggi (~17), menunjukkan manfaat sosial yang sangat besar.
- Tidak ada proyek yang mendekati batas minimum → semua layak secara sosial.
---
##### 🌍 Kenapa Ini Penting?
Dengan menghitung SROI, kita tidak hanya fokus pada keuntungan finansial atau dampak lingkungan, tapi juga:
- Apakah proyek menciptakan pekerjaan?
- Apakah masyarakat lokal mendapatkan manfaat nyata?
- Apakah kesenjangan sosial bisa dikurangi?
  
Penilaian ini memastikan bahwa proyek energi hijau juga mendukung **keadilan sosial dan kesejahteraan masyarakat lokal**.

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

# 📈 4. Economic Dataset
Data ini bantu kita melihat dampak ekonomi lokal, termasuk efek berantai dari proyek.
1. Local_Economic_Impact - Indeks kontribusi terhadap ekonomi lokal
2. SME_Inclusion - Apakah proyek melibatkan UMKM? (ya/tidak)
3. Cost_Benefit_Ratio - Rasio antara total manfaat ekonomi dibanding biaya proyek
#### 📘 Analisis Risiko Ekonomi (ERAF) untuk Proyek Energi Hijau
##### 🎯 Tujuan
Menilai risiko ekonomi proyek energi terbarukan dengan melihat:
- Pertumbuhan Ekonomi (`GDP_Growth`)
- Inflasi (`Inflation_Rate`)
- Pengangguran (`Unemployment_Rate`)
- Investasi Asing Masuk (`FDI_Inflows`)

##### 📐 Rumus ERAF (Economic Risk Adjustment Factor)
Rumus:

$$
\text{ERAF} = 1 + w_1 \cdot \frac{Ir - Ir_{base}}{Ir_{base}} + w_2 \cdot \frac{Ur - Ur_{base}}{Ur_{base}} - w_3 \cdot \frac{Gg - Gg_{base}}{Gg_{base}}
$$

**Keterangan:**
- \( Ir \): Inflasi saat ini (`Inflation_Rate`)
- \( Ir_{base} = 3.0\% \): Inflasi dasar
- \( Ur \): Pengangguran saat ini (`Unemployment_Rate`)
- \( Ur_{base} = 5.0\% \): Pengangguran dasar
- \( Gg \): Pertumbuhan PDB saat ini (`GDP_Growth`)
- \( Gg_{base} = 5.5\% \): PDB dasar
- Bobot: \( w_1 = 0.4 \), \( w_2 = 0.3 \), \( w_3 = 0.3 \)
----
##### ✅ Contoh Perhitungan
Jika:
- Ir = 6%, Ur = 7%, Gg = 4%
- Maka:
ERAF = 1 + 0.4*(6-3)/3 + 0.3*(7-5)/5 - 0.3*(4-5)/5
= 1 + 0.41 + 0.30.4 + 0.3*0.2
= 1 + 0.2 + 0.12 + 0.06 = 1.38
---
###### 📌 Kategori Risiko
- ERAF > 1.05 → **Tinggi**
- 0.95 ≤ ERAF ≤ 1.05 → **Sedang**
- ERAF < 0.95 → **Rendah**
---
##### 💵 Katalis Investasi (FDI)
- FDI ≥ 4.0 → **FDI Tinggi** → Katalis hijau
- FDI 2.5 – 3.9 → **FDI Cukup**
- FDI < 2.5 → **FDI Rendah**
---
##### 🏁 Status Pendanaan
| Syarat ERAF & FDI               | Status                        |
|----------------------------------|-------------------------------|
| ERAF < 1 dan FDI ≥ 4.0          | ✅ Layak Investasi Hijau      |
| ERAF ≤ 1.05 dan FDI ≥ 2.5       | ⚠️ Cukup Layak               |
| ERAF > 1.05 atau FDI < 2.5      | 🔴 Risiko Tinggi / FDI Lemah |
---
##### 📉 Visualisasi
![image](https://github.com/user-attachments/assets/8553be72-bb87-4cc4-9f33-2904393f6145)
**🔍 Apa yang ditampilkan grafik?****
- Grafik menunjukkan tingkat risiko ekonomi (ERAF) untuk setiap proyek.
  1. Sumbu X = Project_ID (nama proyek)
  2. Sumbu Y = ERAF (Economic Risk Adjustment Factor)
  3. Garis abu-abu horizontal = batas normal risiko (ERAF = 1.0)
  **Warna batang:**
  1. 🟥 Merah = Risiko Tinggi (ERAF > 1.05)
  2. 🟧 Oranye = Risiko Sedang (ERAF antara 0.95 dan 1.05)
  3. 🟩 Hijau = Risiko Rendah (ERAF < 0.95)

**📈 Apa arti nilai ERAF?**
- ERAF > 1: Risiko ekonomi tinggi → biaya proyek bisa naik → perlu perhatian.
- ERAF < 1: Risiko rendah → proyek lebih stabil secara ekonomi.

**🧠 Kesimpulan Grafik:**
Sebagian besar proyek memiliki ERAF di atas 1.0, artinya:
1. Risiko ekonomi masih cukup tinggi
2. Bisa disebabkan oleh kombinasi seperti GDP rendah, inflasi tinggi, atau pengangguran tinggi
3. Proyek dengan GDP sangat rendah, seperti PLTS-JATIM-001, menunjukkan risiko paling tinggi.
---  
##### 🧠 Tips & Regulasi
- **Sensitivitas Makro**: Gunakan ERAF untuk uji ketahanan proyek terhadap perubahan inflasi & pertumbuhan.
- **Katalis Investasi**: FDI tinggi = iklim investasi baik.
- **Regulasi Penting**:
  - 📜 UU No. 25/2007 → mendukung FDI
  - 📜 Perpres No. 112/2022 → mendukung proyek di wilayah pengangguran tinggi
---

# 🗌️ 5 Geospatial Dataset
Ini data lokasi buat bantu analisis spasial, misalnya jarak ke pemukiman, atau apakah proyek berada di kawasan rawan bencana.
1. Latitude, Longitude - Titik koordinat lokasi proyek
2. Proximity_to_Village - Jarak ke desa terdekat (km)
3. Disaster_Zone_Flag - Apakah lokasi termasuk zona rawan bencana? (ya/tidak)
###### 🌍 Geospatial Risk Index (GRI) – Green Finance Analysis

Proyek ini menganalisis **risiko spasial** dari proyek energi terbarukan (PLTS, PLTM) berdasarkan informasi lokasi. Analisis dilakukan menggunakan pendekatan **Geospatial Risk Index (GRI)** sebagai bagian dari praktik **Green Finance**.

---

##### 📌 Tujuan

- Menilai **risiko lingkungan berbasis lokasi** proyek energi
- Mengklasifikasikan proyek berdasarkan tingkat risiko: Low, Medium, High
- Mendukung seleksi proyek yang sesuai **Taksonomi Hijau Indonesia (THI)** dan prinsip **Do No Significant Harm (DNSH)**

---

##### 📈 Metode Perhitungan GRI
GRI dihitung dengan rumus:

\[
\text{GRI} = (w_1 \times S_{\text{hazard}}) + (w_2 \times S_{\text{proximity}}) + (w_3 \times S_{\text{landuse}})
\]

Di mana:

- \( S_{\text{hazard}} \) = Skor risiko bencana alam (0–1)
- \( S_{\text{proximity}} \) = Skor kedekatan dengan kawasan lindung (0–1)
- \( S_{\text{landuse}} \) = Skor risiko perubahan lahan (0–1)
- \( w_1, w_2, w_3 \) = Bobot masing-masing komponen (misal: 0.4, 0.3, 0.3)
---

**Komponen:**

- `S_hazard`: Risiko bencana alam (banjir, gempa, longsor)
- `S_proximity`: Kedekatan dengan kawasan lindung (hutan, taman nasional)
- `S_landuse`: Risiko perubahan lahan (deforestasi, konversi hutan)
- `w₁, w₂, w₃`: Bobot masing-masing faktor (misalnya: 0.4, 0.3, 0.3)

---

##### ✅ Aturan Praktis Penilaian Risiko

| Nilai GRI | Tingkat Risiko     | Tindakan                                                    |
|-----------|--------------------|--------------------------------------------------------------|
| > 0.7     | **High Risk 🚨**    | Wajib due diligence tambahan, proyek bisa ditolak           |
| 0.4–0.7   | **Medium Risk ⚠️**  | Perlu mitigasi risiko, analisis tambahan                    |
| < 0.4     | **Low Risk ✅**      | Lokasi aman, tidak perlu analisis tambahan                  |

---

##### 📊 Contoh Output

| Project_ID     | Lokasi     | GRI  | Risk Level                   |
|----------------|------------|------|------------------------------|
| PLTS-NTT-001   | Sumba      | 0.20 | Low Risk ✅                   |
| PLTM-SUMUT-001 | Tapanuli   | 0.39 | Low Risk ✅                   |
| PLTS-JATIM-001 | Surabaya   | 0.51 | Medium Risk ⚠️                |
| PLTM-PAPU-001  | Papua      | 0.81 | High Risk 🚨 (due diligence)  |

---
##### visualisasi data
![image](https://github.com/user-attachments/assets/e0209b24-038a-4722-8711-d60d5c852fa7)
**📊 Apa Maksud Visualisasi GRI?**
- Visualisasi GRI adalah grafik batang (bar chart) yang menunjukkan:
 1. Tingkat risiko geospasial (GRI) dari setiap proyek energi terbarukan (PLTS, PLTM).
 2. Setiap batang mewakili 1 proyek, dan tinggi batang menunjukkan nilai GRI-nya.

**Warna batang menunjukkan tingkat risikonya:**
 1. 🟥 Merah = Risiko tinggi (GRI > 0.7)
 2. 🟧 Oranye = Risiko sedang (GRI antara 0.4 – 0.7)
 3. 🟩 Hijau = Risiko rendah (GRI < 0.4)

**🎯 Tujuannya apa?**
Agar kita bisa:
1. Membandingkan proyek mana yang lebih berisiko secara lokasi
2. Menandai proyek berbahaya yang perlu due diligence tambahan
3. Mendukung keputusan investasi berbasis data lokasi dan lingkungan
---
##### 🛠️ Teknologi & Data Sumber

- **Python Libraries**: `pandas`, `matplotlib`
- **Sumber spasial resmi** (untuk penentuan skor):
  - [Ina-Geoportal](https://tanahair.indonesia.go.id)
  - [KLHK PIPPIB](https://pippib.menlhk.go.id)
  - [BNPB](https://bnpb.go.id)
  - [BMKG](https://bmkg.go.id)

---

##### 📥 Catatan

- Analisis ini **tidak menggunakan data GPS (latitude/longitude)**.
- Skor spasial diperoleh dari interpretasi **peta publik dan dokumen resmi**.
- Pendekatan ini cocok untuk seleksi proyek **green finance dan investasi ESG**.
---

# 📌 Kenapa ini penting?
Karena proyek yang bagus itu gak cuma menghasilkan uang, tapi juga:
1. 🌍 Melindungi lingkungan
2. 👥 Menguntungkan masyarakat
3. 💼 Mendorong ekonomi lokal
4. 📉 Sesuai konteks lokasi
-----

# 👋 Terima Kasih semua
Terima kasih sudah mengikuti petualangan analisis Green Finance ini dari awal sampai akhir!
Lewat proyek ini, kita belajar bareng gimana caranya menilai proyek energi terbarukan secara lengkap – bukan cuma dari sisi untung rugi 💸, tapi juga dari sisi lingkungan 🌍, sosial 👥, ekonomi lokal 📉, dan lokasi 📍.

****Semoga analisis ini bisa bantu kamu:****
- Paham pentingnya pembiayaan yang berkelanjutan
- Tahu cara membaca data & membuat keputusan berbasis bukti
- Lebih peduli pada masa depan bumi dan masyarakat kita 💚

****Sampai jumpa di proyek hijau berikutnya ✨****

****"Karena bumi butuh lebih banyak pahlawan data yang cinta lingkungan." 🌏💻****
