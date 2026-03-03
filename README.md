CAPSTONE PROJECT_WEEK 4
1. Judul dan Deskripsi Proyek
Judul: Analisis Transkriptomik Efek Irbesartan terhadap Perbaikan Diabetic Kidney Disease (DKD).
Deskripsi: Proyek ini bertujuan untuk mengeksplorasi perubahan ekspresi gen pada model ginjal diabetik dan bagaimana pemberian obat Irbesartan dapat memulihkan fungsi sel melalui regulasi ritme sirkadian dan jalur siklus sel.
2. Problem Statement (Rumusan Masalah)
Penyakit Ginjal Diabetik (Diabetic Kidney Disease/DKD) merupakan komplikasi mikrovaskular utama pada penderita diabetes melitus dan menjadi penyebab utama gagal ginjal stadium akhir di seluruh dunia. Meskipun terapi standar seperti penggunaan Angiotensin II Receptor Blockers (ARB) telah lama diterapkan untuk mengontrol proteinuria dan tekanan darah, pemahaman mengenai mekanisme perbaikan fungsional pada tingkat molekuler masih terbatas. Kondisi hiperglisemia kronis pada DKD diketahui dapat mengganggu ritme sirkadian seluler—jam biologis internal yang mengatur metabolisme dan homeostasis sel. Gangguan pada ritme sirkadian ini memicu disregulasi siklus sel yang mempercepat kerusakan jaringan ginjal. Oleh karena itu, terdapat kebutuhan mendesak untuk:
a. Mengidentifikasi profil ekspresi gen (Differentially Expressed Genes/DEG) yang mengalami gangguan pada kondisi DKD.
b. Menganalisis bagaimana intervensi obat, dalam hal ini Irbesartan, mampu memulihkan jalur ritme sirkadian dan regulasi siklus sel.
c. Memvalidasi secara bioinformatika apakah pemulihan gen-gen sirkadian berkorelasi dengan perbaikan kerusakan histopatologis pada ginjal.
3. Dataset dan Metadata
Model Hewan: Tikus db/db (model diabetes) dan tikus db/m (kontrol normal).
Kelompok Perlakuan:
1. Kelompok Normal (Control).
2. Kelompok Diabetes (DKD Model).
3. Kelompok Diabetes + Irbesartan.
Fokus Data: Profil ekspresi gen dari jaringan korteks ginjal.
4. Metode Analisis (Workflow)
Akuisisi Data dan Desain Eksperimen → Pre-processing Data (Cleaning & Exploratory) → Identifikasi DEG → Visualisasi Data Gen Spesifik → Analisis Fungsional dan Jalur (Interpretasi Biologis)
Penjelasan:
a. Akuisisi Data dan Desain Eksperimen
Data ekspresi gen diperoleh dari jaringan korteks ginjal tikus melalui teknologi Microarray atau RNA-Seq. Kelompok sampel dibagi menjadi tiga grup utama: kontrol normal (db/m), model DKD (db/db), dan kelompok perlakuan (DKD + Irbesartan).
b. Pre-processing Data (Cleaning & Exploratory)
Data mentah diproses menggunakan transformasi log2 untuk menstabilkan varian dan mendekati asumsi model linear. Dilakukan pengecekan distribusi nilai ekspresi menggunakan Boxplot untuk memastikan data telah ternormalisasi dengan baik antar sampel. Selain itu, digunakan UMAP untuk memvisualisasikan pemisahan sampel secara global dan mendeteksi adanya efek batch.
c. Identifikasi Differentially Expressed Genes (DEG)
Analisis dilakukan menggunakan paket limma (Linear Models for Microarray Data) di lingkungan RStudio dengan gen diidentifikasi sebagai DEG jika memenuhi ambang batas statistik: 1) Adjusted P-value (FDR) < 0,05 untuk mengontrol penemuan positif palsu dan 2) Log2 Fold Change (log2FC) > 1 (untuk gen up-regulated) atau < -1 (untuk gen down-regulated).
d. Visualisasi Data Gen Spesifik
Digunakan Volcano Plot untuk memetakan distribusi gen berdasarkan signifikansi statistik (-log10 P-value) dan besarnya perubahan ekspresi (log2FC) serta Heatmap dengan dilakukan hierarchical clustering pada top 50 gen paling signifikan untuk melihat pola ekspresi yang berbeda antar kelompok perlakuan.
e. Analisis Fungsional dan Jalur (Interpretasi Biologis)
Dilakukan Gene Ontology (GO) Enrichment menggunakan alat g:Profiler untuk mengidentifikasi kategori Biological Process (BP), Molecular Function (MF), dan Cellular Component (CC), khususnya terkait ritme sirkadian dan siklus sel. Selain itu, dilakukan KEGG Pathway Mapping untuk memetakan gen yang signifikan ke dalam jalur metabolisme dan persinyalan seperti Circadian Rhythm, Cell Cycle, dan PPAR Signaling Pathway untuk memahami mekanisme aksi Irbesartan. 
5. Hasil dan Visualisasi (BLM SELESAI)
a. Daftar 10 Gen dengan Ekspresi Diferensial Paling Signifikan
<img width="852" height="258" alt="Screenshot 2026-03-03 121442" src="https://github.com/user-attachments/assets/177dede0-e949-465b-bcb2-ec0e912d582e" />

b. Boxplot
c. UMAP
d. Volcano Plot
e. Heatmap
7. Analisis Gene Ontology (GO) & KEGG (BLM SELESAI)
GO: Fokus pada proses metabolisme sirkadian dan pembelahan sel.
KEGG: Jalur persinyalan *Cell Cycle* dan *PPAR Signaling Pathway* (sesuai temuan di paper).
8. Kesimpulan (BLM SELESAI)
Irbesartan tidak hanya menurunkan tekanan darah tetapi juga memperbaiki jam biologis seluler di ginjal yang terganggu akibat kondisi diabetes.
