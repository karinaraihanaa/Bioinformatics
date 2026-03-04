CAPSTONE PROJECT_WEEK 4
1. Judul dan Deskripsi Proyek
<br> Judul: Analisis Transkriptomik Efek Irbesartan terhadap Perbaikan Diabetic Kidney Disease (DKD).
Deskripsi: Proyek ini bertujuan untuk mengeksplorasi perubahan ekspresi gen pada model ginjal diabetik dan bagaimana pemberian obat Irbesartan dapat memulihkan fungsi sel melalui regulasi ritme sirkadian dan jalur siklus sel.
2. Problem Statement (Rumusan Masalah)
<br> Penyakit Ginjal Diabetik (Diabetic Kidney Disease/DKD) merupakan komplikasi mikrovaskular utama pada penderita diabetes melitus dan menjadi penyebab utama gagal ginjal stadium akhir di seluruh dunia. Meskipun terapi standar seperti penggunaan Angiotensin II Receptor Blockers (ARB) telah lama diterapkan untuk mengontrol proteinuria dan tekanan darah, pemahaman mengenai mekanisme perbaikan fungsional pada tingkat molekuler masih terbatas. Kondisi hiperglisemia kronis pada DKD diketahui dapat mengganggu ritme sirkadian seluler—jam biologis internal yang mengatur metabolisme dan homeostasis sel. Gangguan pada ritme sirkadian ini memicu disregulasi siklus sel yang mempercepat kerusakan jaringan ginjal. Oleh karena itu, terdapat kebutuhan mendesak untuk:
<br> a. Mengidentifikasi profil ekspresi gen (Differentially Expressed Genes/DEG) yang mengalami gangguan pada kondisi DKD.
<br> b. Menganalisis bagaimana intervensi obat, dalam hal ini Irbesartan, mampu memulihkan jalur ritme sirkadian dan regulasi siklus sel.
<br> c. Memvalidasi secara bioinformatika apakah pemulihan gen-gen sirkadian berkorelasi dengan perbaikan kerusakan histopatologis pada ginjal.
3. Dataset dan Metadata
<br> Model Hewan: Tikus db/db (model diabetes) dan tikus db/m (kontrol normal).
<br> Kelompok Perlakuan:
<br> 1. Kelompok Normal (Control).
<br> 2. Kelompok Diabetes (DKD Model).
<br> 3. Kelompok Diabetes + Irbesartan.
<br> Fokus Data: Profil ekspresi gen dari jaringan korteks ginjal.
4. Metode Analisis (Workflow)
<br> Akuisisi Data dan Desain Eksperimen → Pre-processing Data (Cleaning & Exploratory) → Identifikasi DEG → Visualisasi <br> Data Gen Spesifik → Analisis Fungsional dan Jalur (Interpretasi Biologis)
<br> Penjelasan:
<br> a. Akuisisi Data dan Desain Eksperimen
<br> Data ekspresi gen diperoleh dari jaringan korteks ginjal tikus melalui teknologi Microarray atau RNA-Seq. Kelompok sampel dibagi menjadi tiga grup utama: kontrol normal (db/m), model DKD (db/db), dan kelompok perlakuan (DKD + Irbesartan).
<br> b. Pre-processing Data (Cleaning & Exploratory)
<br> Data mentah diproses menggunakan transformasi log2 untuk menstabilkan varian dan mendekati asumsi model linear. <br> Dilakukan pengecekan distribusi nilai ekspresi menggunakan Boxplot untuk memastikan data telah ternormalisasi dengan baik antar sampel. Selain itu, digunakan UMAP untuk memvisualisasikan pemisahan sampel secara global dan mendeteksi adanya efek batch.
<br> c. Identifikasi Differentially Expressed Genes (DEG)
<br> Analisis dilakukan menggunakan paket limma (Linear Models for Microarray Data) di lingkungan RStudio dengan gen diidentifikasi sebagai DEG jika memenuhi ambang batas statistik: 1) Adjusted P-value (FDR) < 0,05 untuk mengontrol penemuan positif palsu dan 2) Log2 Fold Change (log2FC) > 1 (untuk gen up-regulated) atau < -1 (untuk gen down-regulated).
<br> d. Visualisasi Data Gen Spesifik
<br> Digunakan Volcano Plot untuk memetakan distribusi gen berdasarkan signifikansi statistik (-log10 P-value) dan besarnya perubahan ekspresi (log2FC) serta Heatmap dengan dilakukan hierarchical clustering pada top 50 gen paling signifikan untuk melihat pola ekspresi yang berbeda antar kelompok perlakuan.
<br> e. Analisis Fungsional dan Jalur (Interpretasi Biologis)
<br> Dilakukan Gene Ontology (GO) Enrichment menggunakan alat g:Profiler untuk mengidentifikasi kategori Biological Process (BP), Molecular Function (MF), dan Cellular Component (CC), khususnya terkait ritme sirkadian dan siklus sel. Selain itu, dilakukan KEGG Pathway Mapping untuk memetakan gen yang signifikan ke dalam jalur metabolisme dan persinyalan seperti Circadian Rhythm, Cell Cycle, dan PPAR Signaling Pathway untuk memahami mekanisme aksi Irbesartan. 
5. Hasil dan Visualisasi
<br> a. Daftar 10 Gen dengan Ekspresi Diferensial Paling Signifikan
<br> <img width="852" height="258" alt="Screenshot 2026-03-03 121442" src="https://github.com/user-attachments/assets/177dede0-e949-465b-bcb2-ec0e912d582e" />
<br> Nilai logFC positif yang tinggi di semua gen mengindikasikan bahwa pemberian Irbesartan memicu peningkatan ekspresi (up-regulation) gen secara signifikan pada jaringan ginjal. Gen-gen ini kemungkinan merupakan gen-gen kunci dalam pemulihan ritme sirkadian dan regulasi siklus sel dari kondisi diabetes. Misalnya, gen dengan ID 14772385 memiliki nilai logFC sebesar 6,5 yang artinya ekspresi meningkat hingga 90,5 kali lipat (2^6,5).
<br> b. Volcano Plot
<br> <img width="420" height="360" alt="image" src="https://github.com/user-attachments/assets/8d6ff46e-eaf5-45ac-a210-bd3ff877232a" />
<br> Konsentrasi titik-titik di sisi kanan atas menunjukkan adanya respons molekuler yang masif (ekspresi di atas 10-9- kali lipat) dari gen-gen yang teraktivasi oleh terapi Irbesartan, membuktikan bahwa obat ini bekerja secara efektif pada tingkat transkriptomik untuk memperbaiki kerusakan ginjal diabetik.
<br> c. Mean-Difference Plot
<br> <img width="420" height="360" alt="image" src="https://github.com/user-attachments/assets/91f76381-5ab2-45d8-bfeb-e5c1b10fe787" />
<br> Pola gen signifikan di atas garis nol mengonfirmasi bahwa efek utama Irbesartan dalam penelitian ini adalah menginduksi kembali ekspresi gen-gen fungsional yang biasanya menurun pada kondisi penyakit ginjal diabetik.
<br> d. UMAP
<br> <img width="440" height="360" alt="image" src="https://github.com/user-attachments/assets/911d41ec-9e7e-4a3b-9b64-477375255572" />
<br> Ditunjukkan pemisahan kelompok sampel secara jelas berdasarkan profil ekspresi gen globalnya. Pemisahan kelompok perlakuan Irbesartan dari kelompok model DKD membuktikan bahwa intervensi obat ini memberikan perubahan genetik yang signifikan dan konsisten, yang mendasari perbaikan histopatologis pada ginjal tikus db/db.
7. Analisis Gene Ontology (GO) & KEGG
<br> <img width="1907" height="943" alt="gProfiler_mmusculus_2026-03-04_01-14-47" src="https://github.com/user-attachments/assets/cc8e1077-1a6f-468a-8f39-c8b4e5f463f8" />
<br> <img width="410" height="91" alt="Screenshot 2026-03-04 082335" src="https://github.com/user-attachments/assets/dac03053-fee8-449f-9eca-80665d8c5ba3" />
<br> <img width="412" height="93" alt="Screenshot 2026-03-04 082314" src="https://github.com/user-attachments/assets/bb4f2ba9-6b76-4e01-a4cb-30fd0ba345b7" />
<br> <img width="407" height="92" alt="Screenshot 2026-03-04 082256" src="https://github.com/user-attachments/assets/be46389b-57f5-4f59-a3ba-5ad9f5b22c26" />
<br> <img width="10" height="10" alt="circadian rythm" src="https://github.com/user-attachments/assets/2a293f6f-654d-409e-a581-8210a85f9757" />
<br> <img width="10" height="10" alt="p53 signaling pathway" src="https://github.com/user-attachments/assets/25b82c07-c67c-43d4-b505-4d9491d286cc" />
<br> GO: Fokus pada proses metabolisme sirkadian dan pembelahan sel.
<br> KEGG: Jalur persinyalan *Cell Cycle* dan *PPAR Signaling Pathway* (sesuai temuan di paper).
9. Kesimpulan (BLM SELESAI)
<br> Irbesartan tidak hanya menurunkan tekanan darah tetapi juga memperbaiki jam biologis seluler di ginjal yang terganggu akibat kondisi diabetes.
