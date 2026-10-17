# Data Visualization: Faktor yang Berkaitan dengan Kelulusan Mahasiswa

Tugas Studi Kasus Mata Kuliah **Data Mining**
Dio Raditya Putra Pratama | 2318044

## Deskripsi Project
Project ini mengeksplorasi dataset kelulusan mahasiswa secara visual menggunakan **Python (Matplotlib dan Seaborn)** di Google Colab. Tujuannya mencari pola, distribusi, hubungan antarvariabel, dan tren yang berkaitan dengan status kelulusan (Tepat Waktu / Terlambat).

## Dataset
`dataset_kelulusan_mahasiswa.csv` berisi 500 mahasiswa dari 5 jurusan (Informatika, Sistem Informasi, Teknik Elektro, Teknik Sipil, Teknik Industri) dengan 13 kolom.

| Kelompok | Kolom |
|---|---|
| Identitas dan akademik | id_mahasiswa, jenis_kelamin, jurusan, semester, ipk, tugas_terkumpul, nilai_uts, nilai_uas |
| Perilaku | kehadiran_persen, jam_belajar_per_minggu |
| Aktivitas luar kuliah | aktif_organisasi, kerja_paruh_waktu |
| Target | status_kelulusan (359 Tepat Waktu, 141 Terlambat) |

Sumber dataset: [https://drive.google.com/file/d/1H_MI6jQPUgD1XaXbOoxpvbNnrEk0XcXr/view?usp=sharing]

## Persiapan Data
Missing value (37 sel) diisi median per jurusan, outlier dibatasi dengan IQR (capping), dan ditambahkan kolom `tepat_waktu` (1/0) untuk perhitungan persentase dan korelasi.

## Teknik Visualisasi dan Insight

| No | Visualisasi | Insight utama |
|---|---|---|
| 1 | Histogram IPK | Mahasiswa tepat waktu bermedian IPK 3,17, mahasiswa terlambat 2,72 |
| 2 | Boxplot kehadiran dan jam belajar | Median kehadiran 85,6% vs 69,6%, jam belajar 12,6 vs 9,7 jam per minggu |
| 3 | Scatter plot kehadiran vs IPK | Korelasi 0,66, mahasiswa terlambat menumpuk di kehadiran dan IPK rendah |
| 4 | Line chart per semester | IPK stabil 3,0-3,1, persentase tepat waktu 68%-77% tanpa tren jelas |
| 5 | Bar chart per jurusan | Teknik Sipil 76,5% tertinggi, Teknik Industri 67,6% terendah |
| 6 | Bar chart aktivitas luar kuliah | Tanpa organisasi dan kerja 75,4%, aktif organisasi sekitar 68% |
| 7 | Heatmap korelasi | IPK (0,66) dan kehadiran (0,60) paling berkorelasi dengan kelulusan |

### Ringkasan
![Ringkasan visualisasi](hasil_visualisasi/08_ringkasan_dashboard.png)

### Beberapa Hasil Visualisasi
![Histogram IPK](hasil_visualisasi/01_histogram_ipk.png)
![Scatter kehadiran vs IPK](hasil_visualisasi/03_scatter_kehadiran_ipk.png)
![Heatmap korelasi](hasil_visualisasi/07_heatmap_korelasi.png)

## Kesimpulan
1. IPK dan kehadiran adalah variabel yang paling terkait dengan kelulusan tepat waktu (korelasi 0,66 dan 0,60).
2. Jam belajar, nilai UTS/UAS, dan tugas berkaitan positif dengan kelulusan, tetapi lebih lemah (0,27 sampai 0,45).
3. Semester dan jurusan tidak banyak membedakan kelulusan.
4. Aktivitas di luar kuliah berkaitan dengan persentase tepat waktu yang sedikit lebih rendah, selisihnya kecil.
5. Hasil ini menunjukkan keterkaitan, bukan sebab-akibat.

**Link Google Colab:** [https://colab.research.google.com/drive/1J8zYWhJxoDUmQqI--ls_fsfptcxXv8_l?usp=sharing]
