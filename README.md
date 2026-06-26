# Simulasi Model Ising 2D via Algoritma Metropolis

## Deskripsi Proyek
Repositori ini berisi implementasi dan analisis komputasional dari Model Ising 2 Dimensi (2D) menggunakan algoritma Metropolis Monte Carlo. Proyek ini merupakan studi kasus komprehensif untuk mengamati bagaimana perilaku kolektif partikel memicu terjadinya magnetisasi spontan serta transisi fasa makroskopis pada tiga rentang suhu termodinamika yang berbeda. Hasil simulasi dianalisis menggunakan Jupyter Notebook dan dipublikasikan sebagai portofolio web menggunakan GitHub Pages.

## Struktur Repositori
*   `notebooks/`: Folder ini menyimpan berkas analisis Jupyter Notebook (.ipynb) yang berisi implementasi algoritma dan pembuatan grafik.
*   `docs/`: Folder ini menyimpan dokumen statis HTML hasil konversi dari notebook, termasuk berkas `index.html` utama untuk keperluan publikasi web (deployment).

## Skenario Simulasi & Parameter
Simulasi dijalankan pada sistem kisi berukuran $20 \times 20$ menggunakan konfigurasi acak awal (Hot Start) untuk merepresentasikan entropi maksimum sistem. Setiap kasus menjalankan minimal 200.000 langkah Monte Carlo untuk mencapai kesetimbangan termal, dengan pengambilan data rata-rata magnetisasi setiap 100 langkah.

Terdapat tiga studi kasus yang dianalisis dalam proyek ini:
1.  **Fase Feromagnetik (T = 1.0):** Simulasi sistem di bawah suhu kritis ($T < T_c$). Pada fase ini, spin berorientasi searah secara spontan membentuk domain magnetik seragam dengan nilai mutlak magnetisasi mendekati satu ($|M| \approx 1$).
2.  **Transisi Fasa & Kritikalitas (T = 2.27):** Simulasi pada titik suhu kritis teoritis ($T_c \approx 2.27$). Pada fase ini, diamati terjadinya fluktuasi kritis yang memicu pembentukan pola domain fraktal dan runtuhnya keteraturan jarak jauh.
3.  **Fase Paramagnetik (T = 4.0):** Simulasi pada rentang suhu tinggi ($T > T_c$). Energi termal mendominasi sistem sehingga orientasi spin menjadi acak dan magnetisasi rata-rata menuju nol.

## Metodologi Komputasi
Program Python dalam proyek ini mengedepankan efisiensi komputasi dengan spesifikasi algoritma berikut:
*   Menerapkan **kondisi batas periodik** (periodic boundary conditions) menggunakan operasi modulo.
*   Perhitungan **selisih energi lokal** ($\Delta E$) alih-alih menghitung ulang energi total seluruh kisi, menggunakan persamaan matematis: $\Delta E = 2s_{i,j}\sum s_{tetangga}$.
*   Kriteria penerimaan pembalikan arah spin dievaluasi melalui probabilitas penerimaan Metropolis: $\mathcal{R} = e^{-\Delta E/T}$.

## Akses Portofolio Web
Visualisasi keadaan akhir kisi spin (peta warna biner) dan kurva riwayat magnetisasi untuk ketiga kasus dapat diakses melalui GitHub Pages dari branch main yang bersumber dari direktori `/docs`.

## Referensi dan Sumber Data
Landau, D. P., dkk. A Guide to Monte Carlo Simulations in Statistical Physics (Bab 17.2: Aturan Implementasi).
Rifani, Agus. Modul Pembelajaran: Simulasi Model Magnet dan Transisi Fasa.

## Penggunaan AI
Pada pengerjaan case-based ini, kami menggunakan Gemini PRO 3.1 untuk menyusun kerangka sintaksis algoritma Metropolis pada kode simulasi Python, mengoptimalkan format UI/UX untuk halaman web HTML, serta membantu merapikan susunan paragraf analisis fisis.

## Penggunaan Aplikasi Lain
Jupyter Software untuk menyediakan lingkungan eksekusi kode secara interaktif, penulisan analisis berbasis teks formal, dan penampilan visualisasi kurva magnetisasi secara inline.
Visual Studio Code (VS Code) digunakan sebagai editor kode utama untuk menyusun, mengedit, dan merapikan struktur sintaks HTML dan CSS halaman web ini dengan lebih efisien.
Google Colab dimanfaatkan sebagai platform komputasi berbasis cloud untuk menguji dan mengeksekusi algoritma simulasi Python secara cepat tanpa membebani kinerja memori perangkat lokal.
