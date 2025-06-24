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
Sebelum masuk ke rumus dan kodingan, yuk kenalan dulu sama jenis-jenis data yang kita pakai. Proyek ini pakai pendekatan yang menyeluruh—gak cuma lihat aspek finansial aja, tapi juga dampak lingkungan, sosial, ekonomi, dan lokasi proyek. Berikut penjelasan singkat tiap bagian:
### 📊 1. Financial Dataset
Ini data utama buat ngitung kelayakan proyek dari sisi uang dan risiko.
1. Investment_Amount - Jumlah uang yang diinvestasikan (Rp)
2. Loan_Interest_Rate - Suku bunga pinjaman (% per tahun)
3. Default_Risk_Score - Skor risiko gagal bayar (0-100)
4. Revenue_Stream - Perkiraan arus kas masuk tahunan dari proyek
5. Green_Bond_Spread - Selisih imbal hasil antara obligasi hijau vs biasa. Nilai negatif = greenium
#### 1.1 Analisis Finansial: GNPV dan Green Bond 💸
Untuk menilai apakah proyek hijau ini layak dibiayai, kita hitung sesuatu yang namanya Green Net Present Value (GNPV).
##### 🔍 Apa Itu GNPV?
GNPV itu versi “ramah lingkungan” dari NPV biasa. Bedanya, kita tambahkan manfaat lingkungan (seperti pengurangan emisi CO₂) ke dalam arus kas proyek.
##### Rumus GNPV: GNPV = ∑ [(CFₜ + Eₜ) / (1 + r)ᵗ] - I₀

keterangan :
- CFₜ: Arus kas masuk tahunan
- Eₜ: Nilai moneter dari manfaat lingkungan (misalnya dari pengurangan emisi CO₂)
- r: Tingkat diskonto (contoh: 5%)
- N: Umur proyek (misal: 10 tahun)
- I₀: Investasi awal proyek
##### ⚙️ Contoh Perhitungan Manual
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


### 🌿 2. Environmental Dataset
Ngasih gambaran tentang dampak proyek terhadap lingkungan. Cocok buat analisis keberlanjutan.
1. CO2_Reduction - Emisi CO₂ yang dikurangi (ton/tahun)
2. Energy_Output - Energi bersih yang dihasilkan (kWh/tahun)
3. Environmental_Risk_Index - Skor risiko lingkungan proyek (0–100)
4. Konteks_Lingkungan - Ringkasan isu lingkungan di lokasi proyek
5. Peringkat_Dampak - Peringkat keseluruhan dampak proyek (misalnya: Rendah, Sedang, Tinggi)
### 🧝‍♂️ 3. Social Dataset
Aspek sosial itu penting! Ini data yang menilai apakah proyek bermanfaat atau berisiko buat masyarakat sekitar.
1. Job_Creation - Jumlah pekerjaan yang diciptakan
2. Community_Involvement - Level partisipasi masyarakat (rendah–tinggi)
3. Social_Risk_Flag - Apakah ada potensi konflik sosial (ya/tidak)
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
