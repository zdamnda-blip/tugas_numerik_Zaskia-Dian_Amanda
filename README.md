# TUGAS MATA KULIAH METODE NUMERIK : IMPLEMENTASI PYTHON PADA METODE MATRIKS KHUSUS DAN GAUSS-SEIDEL DALAM PENYELESAIAN SISTEM PERSAMAAN LINEAR
Nama : Zaskia Dian Amanda 
Nim : F5512510031
Kelas : Teknik Informatika A Angkatan 2025 

# PENJELASAN KINSEP PENYELESAIAN MASING-MASING SOAL 

# Soal 11.1 - Penyelesaian Sistem Persamaan Linear Tridiagonal
Pada soal ini dibahas penyelesaian sistem persamaan linear dengan tiga variabel, yaitu x1, x2, dan x3. Sistem persamaan yang diberikan berbentuk tridiagonal, artinya matriks koefisien hanya memiliki nilai pada diagonal utama, diagonal atas, dan diagonal bawah.
Bagian (a) - Thomas Algorithm
Penyelesaian pada bagian ini menggunakan Thomas Algorithm, yaitu metode langsung yang bekerja dalam dua langkah. Langkah pertama adalah Forward Decomposition, yaitu menyederhanakan matriks dengan mengeliminasi nilai di bawah diagonal utama. Langkah kedua adalah Back Substitution, yaitu menghitung nilai x3 terlebih dahulu, kemudian disubstitusi ke atas untuk mendapatkan x2 dan x1. Metode ini disebut metode langsung karena hanya perlu satu kali jalan untuk mendapatkan solusi pasti.
Bagian (b) - Gauss-Seidel
Penyelesaian pada bagian ini menggunakan metode Gauss-Seidel, yaitu metode iteratif. Setiap persamaan disederhanakan terlebih dahulu sehingga masing-masing variabel dinyatakan dalam bentuk variabel lainnya. Kemudian nilai x1, x2, dan x3 diperbarui secara berulang menggunakan nilai terbaru di setiap iterasi sampai error relatif lebih kecil dari 1%. Metode ini disebut metode tidak langsung karena membutuhkan beberapa iterasi untuk mendekati solusi yang benar.

# Soal 11.2 - Invers Matriks menggunakan LU Decomposition

Pada soal ini dicari invers matriks dari sistem persamaan soal 11.1. Metode yang digunakan adalah LU Decomposition dikombinasikan dengan unit vector. Pertama matriks A dipecah menjadi matriks L dan U menggunakan cara yang sama seperti Thomas Algorithm. Kemudian untuk mencari invers, digunakan tiga unit vector secara bergantian yaitu {1,0,0}, {0,1,0}, dan {0,0,1}. Setiap unit vector diselesaikan dengan forward substitution untuk mendapat vektor d, lalu dilanjutkan dengan back substitution untuk mendapat vektor x. Hasil dari ketiga penyelesaian tersebut disusun menjadi kolom-kolom pada matriks invers. Verifikasi dilakukan dengan mengalikan matriks A dengan inversnya, jika hasilnya matriks identitas maka invers terbukti benar.

# Soal 11.3 - Thomas Algorithm Sistem 4x4

Pada soal ini diselesaikan sistem persamaan tridiagonal berukuran 4x4 dengan variabel T1, T2, T3, dan T4. Sistem ini merupakan bagian dari algoritma Crank-Nicolson yang digunakan untuk menyelesaikan persamaan diferensial parsial. Langkah penyelesaiannya sama persis seperti soal 11.1 yaitu dimulai dari Forward Decomposition untuk menyederhanakan matriks dengan mengeliminasi nilai di bawah diagonal utama, kemudian dilanjutkan dengan Back Substitution untuk menghitung nilai variabel mulai dari T4 paling bawah lalu disubstitusi ke atas hingga didapat T1.

# Soal 11.4 - Verifikasi Cholesky Decomposition

Pada soal ini diverifikasi hasil Cholesky decomposition dari Example 11.2. Cholesky decomposition adalah metode yang digunakan khusus untuk matriks simetris, di mana matriks A dipecah menjadi matriks L dan transposenya L^T sehingga berlaku hubungan A = L x L^T. Matriks L yang digunakan adalah hasil dekomposisi dari Example 11.2 di buku. Verifikasi dilakukan dengan mengalikan matriks L dengan transposenya L^T secara manual, kemudian hasilnya dibandingkan dengan matriks A asli. Jika selisih antara keduanya sangat kecil maka dekomposisi terbukti benar dan valid.

# Soal 11.5 - Cholesky Decomposition dan Penyelesaian Sistem

Pada soal ini dilakukan Cholesky decomposition pada matriks simetris 3x3 yang sama dengan Example 11.2, namun kali ini decomposition digunakan untuk menyelesaikan sistem persamaan dengan ruas kanan {152.6, 585.6, 2488.8} guna mencari nilai a0, a1, dan a2. Cholesky decomposition memecah matriks A menjadi matriks segitiga bawah L. Setelah L diperoleh, penyelesaian dilakukan dalam dua tahap yaitu forward substitution untuk mendapat vektor d, kemudian back substitution menggunakan transpose L untuk mendapat nilai a0, a1, dan a2.

# Soal 11.6 - Cholesky Decomposition by Hand

Pada soal ini dilakukan Cholesky decomposition pada matriks simetris baru berukuran 3x3 dengan koefisien yang berbeda. Langkah pengerjaannya sama seperti soal 11.5 yaitu menghitung elemen-elemen matriks L satu per satu secara manual menggunakan rumus Cholesky. Setelah matriks L diperoleh, sistem persamaan diselesaikan dengan forward substitution untuk mendapat vektor d, kemudian dilanjutkan back substitution untuk mendapat nilai x1, x2, dan x3.

# Soal 11.7 - Cholesky Decomposition Matriks Diagonal

Pada soal ini dilakukan Cholesky decomposition pada matriks diagonal, yaitu matriks yang hanya memiliki nilai pada diagonal utamanya saja. Karena matriks bersifat diagonal maka semua elemen di luar diagonal bernilai nol, sehingga hasil dekomposisi L juga berbentuk diagonal. Nilai setiap elemen diagonal L cukup dihitung dengan mengakarkan nilai diagonal A, yaitu l11=sqrt(9)=3, l22=sqrt(25)=5, dan l33=sqrt(4)=2. Verifikasi dilakukan dengan mengalikan L dan transposenya untuk membuktikan hasilnya kembali ke matriks A.

# Soal 11.8 - Gauss-Seidel dengan Overrelaxation

Pada soal ini digunakan metode Gauss-Seidel dengan tambahan teknik overrelaxation untuk mempercepat konvergensi. Sistem persamaan yang digunakan sama dengan soal 11.1. Overrelaxation bekerja dengan menerapkan faktor lambda sebesar 1.2 pada setiap nilai baru yang dihitung, artinya nilai yang diperbarui tidak langsung digunakan melainkan dikombinasikan dengan nilai lama menggunakan rumus x = lambda x nilai_baru + (1-lambda) x nilai_lama. Nilai lambda lebih dari 1 membuat iterasi melompat lebih jauh dari nilai lama sehingga konvergensi bisa lebih cepat dibanding Gauss-Seidel biasa. Iterasi terus dilakukan sampai error relatif lebih kecil dari 5%.

# Soal 11.9 - Gauss-Seidel Sistem Konsentrasi

Pada soal ini diselesaikan sistem persamaan linear tiga variabel yaitu c1, c2, dan c3 yang merepresentasikan konsentrasi dalam satuan g/m³ pada serangkaian reaktor yang terhubung. Metode yang digunakan adalah Gauss-Seidel yaitu metode iteratif di mana setiap variabel dinyatakan dalam bentuk variabel lainnya kemudian diperbarui secara berulang menggunakan nilai terbaru di setiap langkah. Iterasi terus dilakukan sampai error relatif semua variabel lebih kecil dari 5%.

# Soal 11.10 - Jacobi Iteration

Pada soal ini digunakan sistem persamaan yang sama dengan soal 11.9 namun diselesaikan dengan metode Jacobi. Perbedaan utama antara Jacobi dan Gauss-Seidel terletak pada cara memperbarui nilai variabel. Pada Gauss-Seidel nilai terbaru langsung digunakan dalam perhitungan variabel berikutnya, sedangkan pada Jacobi semua variabel diperbarui menggunakan nilai lama secara bersamaan baru kemudian diganti setelah satu iterasi selesai. Akibatnya metode Jacobi umumnya membutuhkan lebih banyak iterasi untuk konvergen dibanding Gauss-Seidel.

# Soal 11.11 - Gauss-Seidel Sistem X

Pada soal ini diselesaikan sistem persamaan linear dengan tiga variabel x1, x2, dan x3 menggunakan metode Gauss-Seidel. Setiap persamaan disederhanakan terlebih dahulu sehingga masing-masing variabel dinyatakan dalam bentuk variabel lainnya. Kemudian nilai x1, x2, dan x3 diperbarui secara berulang menggunakan nilai terbaru hingga error relatif lebih kecil dari 5%.

# Soal 11.12 - Gauss-Seidel Tanpa dan Dengan Relaxation

Pada soal ini diselesaikan sistem persamaan yang tidak dalam bentuk diagonal dominan sehingga perlu disusun ulang terlebih dahulu agar metode Gauss-Seidel dapat konvergen. Diagonal dominan artinya nilai absolut pada diagonal utama harus lebih besar dari jumlah nilai absolut elemen lain pada baris yang sama. Setelah persamaan disusun ulang, penyelesaian dilakukan dalam dua cara. Bagian (a) menggunakan Gauss-Seidel biasa tanpa relaxation. Bagian (b) menggunakan relaxation dengan faktor lambda sebesar 0.95 yang disebut underrelaxation karena nilai lambda kurang dari 1. Underrelaxation membuat setiap pembaruan nilai bergerak lebih lambat dan hati-hati sehingga berguna untuk sistem yang sulit konvergen. Kedua cara diiterasi sampai error relatif lebih kecil dari 5%.

# Soal 11.13 - Gauss-Seidel Tanpa dan Dengan Relaxation

Pada soal ini diselesaikan sistem persamaan linear tiga variabel menggunakan metode Gauss-Seidel. Sebelum iterasi dimulai, persamaan perlu disusun ulang terlebih dahulu agar memenuhi syarat diagonal dominan yaitu nilai absolut pada diagonal utama harus lebih besar dari jumlah nilai absolut elemen lain pada baris yang sama. Setelah disusun ulang dengan benar, penyelesaian dilakukan dalam dua cara. Bagian (a) menggunakan Gauss-Seidel biasa tanpa relaxation di mana nilai terbaru langsung digunakan dalam perhitungan berikutnya hingga error relatif lebih kecil dari 5%. Bagian (b) menggunakan overrelaxation dengan faktor lambda sebesar 1.2 yang berarti setiap pembaruan nilai melompat lebih jauh dari nilai lama sehingga diharapkan konvergensi bisa lebih cepat dibanding tanpa relaxation.

# Soal 11.14 - Analisis Gauss-Seidel dengan Slope 1 dan -1

Pada soal ini dianalisis perilaku metode Gauss-Seidel ketika diterapkan pada sistem dua persamaan yang memiliki kemiringan atau slope sebesar 1 dan -1. Kedua garis tersebut adalah y sama dengan x dan y sama dengan negatif x ditambah 1. Solusi sebenarnya dari sistem ini adalah titik perpotongan kedua garis yaitu pada koordinat (0.5, 0.5). Namun ketika metode Gauss-Seidel diterapkan, iterasi tidak mendekati solusi tersebut melainkan berosilasi bolak-balik antara titik (0, 1) dan (1, 0). Hal ini terjadi karena sistem tidak memenuhi syarat konvergensi metode Gauss-Seidel sehingga iterasi tidak pernah berhenti dan tidak pernah mendekati solusi yang benar.

# Soal 11.15 - Identifikasi Sistem yang Tidak Konvergen

Pada soal ini diberikan tiga set sistem persamaan linear dan diminta untuk mengidentifikasi set mana yang tidak dapat diselesaikan dengan metode Gauss-Seidel. Syarat agar Gauss-Seidel dapat konvergen adalah sistem harus memenuhi kondisi diagonal dominan. Set One dapat konvergen setelah baris-barisnya disusun ulang sehingga diagonal menjadi dominan. Set Two tidak konvergen karena tidak memenuhi syarat diagonal dominan dan nilai iterasinya membesar terus tanpa batas atau divergen. Set Three juga tidak konvergen karena susunan persamaannya tidak dapat dibuat diagonal dominan sehingga iterasinya terus berosilasi dan tidak mendekati solusi yang benar.

# Soal 11.16a - Solusi, Invers, dan Condition Number Matriks 3x3

Pada soal ini diselesaikan sistem persamaan linear dengan matriks koefisien 3x3. Langkah pertama adalah mencari solusi x1, x2, dan x3 menggunakan eliminasi Gauss dan back substitution. Langkah kedua adalah mencari invers matriks menggunakan tiga unit vector secara bergantian yaitu {1,0,0}, {0,1,0}, dan {0,0,1}, di mana setiap unit vector diselesaikan dengan eliminasi Gauss untuk menghasilkan satu kolom pada matriks invers. Langkah ketiga adalah menghitung condition number menggunakan row-sum norm yaitu dengan mencari nilai maksimum dari jumlah nilai absolut setiap baris pada matriks A dan inversnya, kemudian mengalikan keduanya. Condition number yang besar menunjukkan bahwa matriks bersifat ill-conditioned artinya solusi sangat sensitif terhadap perubahan kecil pada data input.

# Soal 11.16b - Solusi, Invers, dan Condition Number Matriks 4x4

Pada soal ini dilakukan hal yang sama seperti soal 11.16a namun untuk matriks berukuran 4x4. Karena ukuran matriks lebih besar, dibuat fungsi eliminasi Gauss umum yang dapat menyelesaikan sistem 4 variabel untuk sembarang ruas kanan. Fungsi tersebut dipanggil sebanyak empat kali menggunakan empat unit vector berbeda untuk mendapatkan keempat kolom matriks invers. Condition number kemudian dihitung dengan cara yang sama yaitu mengalikan row-sum norm matriks A dengan row-sum norm inversnya. Soal ini juga berkaitan dengan konsep ill-conditioning di mana matriks dengan pola seperti ini cenderung memiliki condition number yang sangat besar sehingga solusinya rentan terhadap kesalahan pembulatan.

# Soal 11.17 - Sistem Persamaan Nonlinear

Pada soal ini diselesaikan sistem dua persamaan nonlinear dengan dua variabel x dan y. Persamaan pertama adalah f(x,y) = 4 - y - 2x² = 0 dan persamaan kedua adalah g(x,y) = 8 - y² - 4x = 0. Karena persamaan ini bersifat nonlinear, metode yang digunakan adalah Newton-Raphson dua variabel yang bekerja dengan cara menghitung matriks Jacobian yaitu turunan parsial dari setiap persamaan terhadap setiap variabel. Dari Jacobian tersebut dihitung koreksi dx dan dy yang digunakan untuk memperbarui nilai x dan y secara berulang hingga error sangat kecil.

Bagian (a) mencari dua pasang solusi dengan menggunakan dua tebakan awal yang berbeda. Tebakan awal pertama yaitu x=1 dan y=1 menghasilkan solusi pertama, sedangkan tebakan awal x=-1 dan y=3 menghasilkan solusi kedua. Ini menunjukkan bahwa sistem persamaan nonlinear bisa memiliki lebih dari satu solusi tergantung dari mana iterasi dimulai.

Bagian (b) mencoba berbagai kombinasi tebakan awal dengan rentang x dan y dari -6 sampai 6 untuk melihat tebakan awal mana yang mengarah ke solusi pertama dan mana yang mengarah ke solusi kedua. Hasilnya menunjukkan bahwa sebagian besar tebakan awal berhasil menemukan salah satu dari dua solusi tersebut, yang membuktikan bahwa kedua solusi memang benar-benar ada dan dapat dicapai dari berbagai titik awal yang berbeda.

Soal 11.18 - Sistem Produksi Elektronik

Pada soal ini diselesaikan sistem persamaan linear tiga variabel yang merepresentasikan jumlah produksi tiga komponen elektronik yaitu transistor, resistor, dan chip. Setiap komponen membutuhkan tiga jenis bahan baku yaitu copper, zinc, dan glass dengan jumlah yang berbeda-beda sesuai tabel yang diberikan. Total bahan yang tersedia minggu ini adalah 960 unit copper, 510 unit zinc, dan 610 unit glass. Dari informasi tersebut disusun sistem tiga persamaan linear di mana setiap persamaan mewakili total pemakaian satu jenis bahan oleh ketiga komponen. Metode yang digunakan untuk menyelesaikan sistem ini adalah eliminasi Gauss yaitu dengan mengeliminasi variabel satu per satu menggunakan operasi baris hingga matriks berbentuk segitiga atas, kemudian dilanjutkan dengan back substitution untuk mendapatkan nilai masing-masing variabel dari bawah ke atas.

# Soal 11.19 - Hilbert Matrix 10x10

Pada soal ini diselidiki sifat ill-conditioning dari matriks Hilbert berukuran 10x10. Matriks Hilbert adalah matriks simetris yang elemen-elemennya didefinisikan sebagai H[i][j] = 1/(i+j+1) sehingga nilainya semakin kecil menjauhi pojok kiri atas. Matriks ini terkenal sebagai contoh klasik matriks yang sangat ill-conditioned artinya solusi sistem persamaan yang melibatkan matriks ini sangat sensitif terhadap kesalahan pembulatan kecil sekalipun.

Ruas kanan sistem dibuat dengan menjumlahkan setiap baris matriks Hilbert sehingga solusi sebenarnya adalah semua variabel bernilai 1. Hal ini memudahkan perbandingan antara solusi yang dihitung dengan solusi yang sebenarnya untuk melihat seberapa besar pengaruh ill-conditioning terhadap akurasi hasil.

Invers matriks dihitung secara manual menggunakan eliminasi Gauss dengan sepuluh unit vector berbeda untuk mendapatkan kesepuluh kolom matriks invers. Condition number kemudian dihitung dengan mengalikan row-sum norm matriks H dengan row-sum norm inversnya. Hasilnya adalah condition number yang sangat besar yaitu sekitar 35 triliun yang menunjukkan bahwa matriks ini sangat ill-conditioned. Jumlah digit presisi yang hilang diperkirakan dengan mengambil logaritma basis 10 dari condition number, hasilnya sekitar 13 hingga 14 digit presisi hilang. Meskipun demikian solusi yang dihitung masih cukup akurat dengan error yang sangat kecil karena eliminasi Gauss bekerja dengan baik untuk ukuran matriks yang tidak terlalu besar.

# Soal 11.20 - Vandermonde Matrix 6x6

Pada soal ini diselidiki sifat ill-conditioning dari matriks Vandermonde berukuran 6x6. Matriks Vandermonde adalah matriks yang elemen-elemennya didefinisikan sebagai pangkat dari nilai-nilai x yang diberikan yaitu x1=1, x2=2, x3=3, x4=4, x5=5, dan x6=6. Setiap baris matriks berisi pangkat dari nilai x yang bersesuaian mulai dari pangkat tertinggi di kolom kiri hingga pangkat nol di kolom kanan. Matriks ini sering muncul dalam permasalahan interpolasi polinomial dan regresi.

Sama seperti soal 11.19, ruas kanan sistem dibuat dengan menjumlahkan setiap baris matriks Vandermonde sehingga solusi sebenarnya adalah semua variabel bernilai 1. Invers matriks dihitung secara manual menggunakan eliminasi Gauss dengan enam unit vector berbeda untuk mendapatkan keenam kolom matriks invers. Condition number kemudian dihitung dengan mengalikan row-sum norm matriks Vandermonde dengan row-sum norm inversnya.

Perbandingan antara soal 11.19 dan 11.20 menunjukkan perbedaan tingkat ill-conditioning antara matriks Hilbert 10x10 dan matriks Vandermonde 6x6. Matriks Vandermonde 6x6 memiliki condition number yang lebih kecil dibanding matriks Hilbert 10x10 karena ukurannya lebih kecil, namun tetap cukup besar sehingga masih terjadi kehilangan beberapa digit presisi. Jumlah digit presisi yang hilang diperkirakan dengan mengambil logaritma basis 10 dari condition number. Error solusi yang diperoleh kemudian dibandingkan dengan solusi sebenarnya untuk melihat seberapa besar pengaruh ill-conditioning terhadap akurasi hasil perhitungan.

# Soal 11.21 - Matriks Augmented

Pada soal ini dibuat matriks augmented dengan cara menggabungkan matriks A dengan matriks identitas I menjadi satu matriks baru yang disebut [A|I]. Matriks augmented ini biasa digunakan sebagai langkah awal dalam proses mencari invers matriks menggunakan metode eliminasi Gauss-Jordan, di mana operasi baris diterapkan secara bersamaan pada kedua sisi hingga bagian kiri berubah menjadi matriks identitas dan bagian kanan berubah menjadi invers matriks A.

# Soal 11.22 - Solusi, Transpose, dan Invers

Pada soal ini diselesaikan sistem persamaan linear tiga variabel yang persamaannya perlu disusun ulang terlebih dahulu ke bentuk standar. Setelah disusun, sistem diselesaikan menggunakan eliminasi Gauss dan back substitution untuk mendapatkan nilai x1, x2, dan x3. Selain itu dihitung juga transpose matriks A yaitu matriks baru yang diperoleh dengan menukar baris dan kolom matriks A, serta invers matriks A yang dihitung menggunakan unit vector seperti pada soal 11.2.

# Soal 11.23 - Perbandingan Jumlah Operasi

Pada soal ini dibandingkan jumlah operasi aritmatika yang dibutuhkan oleh metode Eliminasi Gauss dan Thomas Algorithm untuk berbagai ukuran matriks n dari 2 sampai 20. Eliminasi Gauss membutuhkan sekitar 2/3 n³ operasi sehingga jumlahnya meningkat sangat cepat seiring bertambahnya n. Sebaliknya Thomas Algorithm hanya membutuhkan sekitar 8(n-1) operasi yang meningkat secara linear. Perbandingan ini menunjukkan bahwa Thomas Algorithm jauh lebih efisien dibanding Eliminasi Gauss khususnya untuk sistem tridiagonal berukuran besar.

# Soal 11.24 - Program Thomas Algorithm

Pada soal ini dibuat program Thomas Algorithm yang menduplikasi hasil dari Example 11.1 di buku. Matriks yang digunakan sama persis dengan Example 11.1 sehingga hasil yang diperoleh seharusnya identik. Tujuan soal ini adalah membuktikan bahwa program yang dibuat sudah benar dan dapat diandalkan untuk menyelesaikan sistem tridiagonal apapun hanya dengan mengganti nilai koefisien dan ruas kanannya.

# Soal 11.25 - Program Cholesky Decomposition

Pada soal ini dibuat program Cholesky Decomposition yang menduplikasi hasil dari Example 11.2 di buku. Matriks simetris yang digunakan sama persis dengan Example 11.2 sehingga nilai elemen matriks L yang dihasilkan seharusnya sama. Tujuan soal ini adalah membuktikan bahwa program Cholesky yang dibuat sudah benar dan dapat digunakan untuk mendekomposisi matriks simetris apapun hanya dengan mengganti nilai matriksnya.

# Soal 11.26 - Program Gauss-Seidel

Pada soal ini dibuat program Gauss-Seidel yang menduplikasi hasil dari Example 11.3 di buku. Sistem persamaan dan koefisien yang digunakan sama persis dengan Example 11.3 sehingga hasil iterasi dan solusi akhir yang diperoleh seharusnya identik dengan buku. Tujuan soal ini adalah membuktikan bahwa program Gauss-Seidel yang dibuat sudah benar dan dapat digunakan untuk menyelesaikan sistem persamaan linear apapun hanya dengan mengganti nilai koefisien dan ruas kanannya.

# Soal 11.27 - Persamaan Diferensial Steady-State

Pada soal ini diselesaikan persamaan diferensial biasa yang merepresentasikan keseimbangan massa zat kimia dalam saluran satu dimensi pada kondisi steady-state. Persamaan diferensial tersebut melibatkan tiga proses yaitu difusi dengan koefisien D, adveksi dengan kecepatan fluida U, dan reaksi peluruhan orde pertama dengan laju k. Untuk mengubah persamaan diferensial menjadi sistem persamaan linear, digunakan metode beda hingga di mana turunan kedua dan turunan pertama didekati menggunakan nilai konsentrasi pada titik-titik diskret dengan jarak Δx=2. Dengan kondisi batas c(0)=80 dan c(10)=20, diperoleh empat persamaan linear untuk empat titik interior yang diselesaikan menggunakan eliminasi Gauss dan back substitution. Hasilnya adalah distribusi konsentrasi zat kimia sepanjang saluran dari x=0 sampai x=10.

# Soal 11.28 - Sistem Pentadiagonal

Pada soal ini diselesaikan sistem persamaan linear dengan struktur pentadiagonal yaitu matriks yang memiliki nilai bukan nol pada lima diagonal yaitu diagonal utama, dua superdiagonal di atas, dan dua subdiagonal di bawah. Sistem ini merupakan perluasan dari sistem tridiagonal yang hanya memiliki tiga diagonal. Pendekatan penyelesaiannya mirip dengan Thomas Algorithm namun disesuaikan untuk bandwidth yang lebih lebar yaitu lima. Matriks pentadiagonal dibangun terlebih dahulu kemudian diselesaikan menggunakan eliminasi Gauss dengan membatasi eliminasi hanya pada baris-baris yang berdekatan sesuai lebar bandwidth, dilanjutkan dengan back substitution untuk mendapatkan solusi akhir.
