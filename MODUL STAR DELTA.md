# Modul Materi Starter Bintang-Segitiga (Star Delta) pada Motor Induksi Tiga Fasa

Oct 13, 2026 · @Ahmad Zaid At Taqi

## Pendahuluan

Modul ini membahas pengasutan (starting) motor induksi tiga fasa dengan metode bintang-segitiga (star delta) sebagai dasar analisis rangkaian, simulasi, dan praktik pemasangan. Rangkaian acuan adalah gambar rangkaian daya dan rangkaian kontrol yang dilampirkan, yang menggunakan tiga kontaktor: main, star, dan delta.

### Capaian Pembelajaran

Setelah mempelajari modul ini, peserta mampu:

1. Menjelaskan prinsip dan tujuan pengasutan bintang-segitiga.
2. Menghitung perbandingan arus dan torsi start antara hubungan bintang dan hubungan segitiga.
3. Membaca rangkaian daya dan rangkaian kontrol, serta menguraikan urutan kerjanya.
4. Mensimulasikan rangkaian pada perangkat lunak simulasi kelistrikan.
5. Merakit, menguji, dan mendiagnosis gangguan rangkaian dengan memperhatikan keselamatan kerja.

### Prasyarat

- Konsep dasar sistem tiga fasa: tegangan fasa, tegangan jala-jala, dan arus jala-jala.
- Prinsip kerja kontaktor, tombol tekan, dan pengaman beban lebih.
- Simbol gambar kelistrikan sesuai standar IEC.

### Alokasi Waktu (Usulan)

| Kegiatan | Cakupan | Alokasi |
| --- | --- | --- |
| Teori dan analisis rangkaian | Bab 1 sampai Bab 3 | 2 × 50 menit |
| Simulasi | Bab 4 | 2 × 50 menit |
| Praktik dan evaluasi | Bab 5 dan Evaluasi | 4 × 50 menit |

## Bab 1. Penjelasan Star Delta

Pengasutan bintang-segitiga adalah metode menurunkan arus start motor induksi tiga fasa dengan menjalankan motor pada hubungan bintang (Y) terlebih dahulu, lalu memindahkannya ke hubungan segitiga (Δ) setelah putaran mendekati nominal.

### 1.1 Latar Belakang

Pada pengasutan langsung (direct on line, DOL), arus start motor induksi mencapai kira-kira 5 sampai 8 kali arus nominal. Arus sebesar ini menimbulkan jatuh tegangan pada jaringan, tekanan mekanik pada poros dan kopling, serta pemanasan belitan. Metode bintang-segitiga menekan arus tersebut menggunakan kontaktor saja, tanpa autotransformator atau pengatur kecepatan elektronik.

### 1.2 Prinsip Kerja

Tegangan yang diterima setiap belitan stator ditentukan oleh jenis hubungannya.

- **Hubungan bintang (Y):** ujung belitan W2, U2, dan V2 dihubungkan menjadi satu titik bintang. Setiap belitan menerima tegangan fasa, yaitu tegangan jala-jala dibagi √3.
- **Hubungan segitiga (Δ):** ujung dan awal belitan dihubungkan berurutan hingga membentuk loop tertutup. Setiap belitan menerima tegangan jala-jala penuh.

Hubungan antara besaran fasa (f) dan besaran jala-jala (L) adalah sebagai berikut.

| Besaran | Hubungan bintang (Y) | Hubungan segitiga (Δ) |
| --- | --- | --- |
| Tegangan pada belitan | V\_L / √3 | V\_L |
| Arus jala-jala | I\_L = I\_f | I\_L = √3 × I\_f |
| Impedansi belitan | Z | Z |

Untuk impedansi belitan Z yang sama, perbandingan arus jala-jala dan torsi start diturunkan sebagai berikut. Torsi motor induksi sebanding dengan kuadrat tegangan yang diterima belitan.

```latex
I_{L(\Delta)} = \sqrt{3}\,\frac{V_L}{Z} \qquad I_{L(Y)} = \frac{V_L}{\sqrt{3}\,Z}
```

```latex
\frac{I_{L(Y)}}{I_{L(\Delta)}} = \frac{1}{3} \qquad \frac{T_{Y}}{T_{\Delta}} = \left(\frac{V_L/\sqrt{3}}{V_L}\right)^{2} = \frac{1}{3}
```

Jadi, pada hubungan bintang, arus start dan torsi start masing-masing turun menjadi sepertiga dari nilainya pada hubungan segitiga.

### 1.3 Perbandingan dengan Pengasutan Langsung

| Parameter | DOL | Bintang-segitiga |
| --- | --- | --- |
| Arus start | Sekitar 5 sampai 8 × arus nominal | Sekitar 1/3 arus start DOL |
| Torsi start | Penuh | Sekitar 1/3 torsi start DOL |
| Jumlah kontaktor | 1 | 3 (main, star, delta) |
| Terminal motor yang diperlukan | 3 | 6 |
| Cocok untuk beban | Berat maupun ringan, pada motor berdaya kecil | Ringan saat start |
| Lonjakan arus saat transisi | Tidak ada | Ada, pada saat pindah ke segitiga |

### 1.4 Syarat Penerapan

- Motor memiliki enam terminal belitan (U1, V1, W1, U2, V2, W2) yang dapat diakses pada kotak terminal.
- Tegangan nominal belitan pada hubungan segitiga sama dengan tegangan jala-jala. Sebagai contoh, motor berpelat nama 380 V Δ / 660 V Y dipasang pada jaringan 380 V.
- Beban saat start ringan, misalnya pompa sentrifugal atau kipas, karena torsi start hanya sepertiga dari nilai penuh.
- Waktu pada hubungan bintang cukup agar putaran mencapai sekitar 80 sampai 90 persen putaran nominal sebelum pindah ke segitiga.

### 1.5 Contoh Perhitungan

Data berikut bersifat ilustrasi: motor 380 V dengan arus nominal 15 A dan arus start DOL sebesar 6 × arus nominal.

| Langkah | Perhitungan | Hasil |
| --- | --- | --- |
| Arus start DOL | 6 × 15 A | 90 A |
| Arus start bintang | 90 A ÷ 3 | 30 A |
| Torsi start bintang | 1/3 × torsi start DOL | Sepertiga |

### 1.6 Kelebihan dan Keterbatasan

- **Kelebihan:** konstruksi sederhana, biaya rendah, dan perawatan mudah.
- **Keterbatasan:** torsi start rendah, terdapat lonjakan arus saat transisi, memerlukan motor dengan enam terminal, dan tegangan jaringan harus sesuai dengan tegangan belitan hubungan segitiga.

## Bab 2. Komponen Rangkaian

Rangkaian pada gambar tersusun atas satu rangkaian daya (sisi kiri) dan satu rangkaian kontrol (sisi kanan) yang terdiri dari sebelas jenis komponen berikut.

| Label pada gambar | Komponen | Fungsi | Kode terminal |
| --- | --- | --- | --- |
| -X (L1, L2, L3) | Terminal masukan daya | Titik sambung sumber tiga fasa | L1, L2, L3 |
| -X (L, N) | Terminal masukan kontrol | Titik sambung fasa dan netral untuk rangkaian kontrol | L, N |
| mcb | Miniature circuit breaker | Pengaman hubung singkat; tiga kutub pada rangkaian daya, satu kutub pada rangkaian kontrol | 1-2, 3-4, 5-6 (daya); 1-2 (kontrol) |
| main | Kontaktor utama | Menyambungkan sumber ke terminal U1, V1, W1 motor | Kontak daya 1-2, 3-4, 5-6; bantu NO 13-14; bantu NC 11-12; kumparan A1-A2 |
| star | Kontaktor bintang | Menghubungkan W2, U2, V2 menjadi titik bintang | Kontak daya 1-2, 3-4, 5-6; bantu NO 13-14; bantu NC 11-12; kumparan A1-A2 |
| delta | Kontaktor segitiga | Menghubungkan ujung belitan ke fasa jala-jala hingga membentuk segitiga | Kontak daya 1-2, 3-4, 5-6; bantu NO 13-14; bantu NC 11-12; kumparan A1-A2 |
| -F | Thermal overload relay (TOR) | Mengamankan motor dari beban lebih | 1-2, 3-4, 5-6 |
| -M | Motor induksi tiga fasa | Beban penggerak | U1, V1, W1, W2, U2, V2, PE |
| off | Tombol tekan NC | Memutus rangkaian kontrol dan menghentikan motor | 11-12 |
| on | Tombol tekan NO | Memberi perintah start | 13-14 |
| -S | Tombol tekan pindah (changeover) | Memerintahkan perpindahan dari bintang ke segitiga | 11-12 (NC), 11-14 (NO) |
| off, star, delta (X1-X2) | Lampu indikator | Menandakan status siaga, bintang, dan segitiga | X1, X2 |

### Ketentuan Penomoran Terminal

- Kontak daya diberi nomor berpasangan 1-2, 3-4, dan 5-6; angka ganjil menandai sisi masuk dan angka genap sisi keluar.
- Kontak bantu NC berakhiran angka 1-2, sedangkan kontak bantu NO berakhiran angka 3-4. Angka pertama menyatakan urutan kontak, misalnya 11-12 dan 13-14.
- Kumparan kontaktor diberi kode A1 dan A2.
- Pada gambar, kontak bantu diberi label sama dengan nama kontaktor pemiliknya, misalnya kontak berlabel "delta" dioperasikan oleh kumparan delta.

## Bab 3. Alur Rangkaian

Rangkaian daya menentukan hubungan belitan motor, sedangkan rangkaian kontrol menentukan urutan kerja kontaktor. Keduanya dibaca dari gambar yang dilampirkan.

### 3.1 Rangkaian Daya

Sumber L1, L2, dan L3 masuk melalui terminal -X dan mcb tiga kutub. Setelah mcb, jalur bercabang dua: satu menuju kontaktor main, TOR -F, lalu terminal U1, V1, W1 motor; satu lagi menuju terminal 1, 3, 5 kontaktor delta.

| Dari | Ke | Keterangan |
| --- | --- | --- |
| mcb 2, 4, 6 | main 1, 3, 5 | Sumber menuju kontaktor utama |
| main 2, 4, 6 | -F 1, 3, 5 | Melewati TOR |
| -F 2, 4, 6 | -M U1, V1, W1 | Awal ketiga belitan |
| mcb 2, 4, 6 | delta 1, 3, 5 | Cabang pada sisi hulu kontaktor main |
| delta 2 dan star 2 | -M W2 | Ujung belitan W |
| delta 4 dan star 4 | -M U2 | Ujung belitan U |
| delta 6 dan star 6 | -M V2 | Ujung belitan V |
| star 1, 3, 5 | Saling dihubungkan | Membentuk titik bintang |

**Hubungan bintang.** Saat kontaktor main dan star menutup, W2, U2, dan V2 saling terhubung melalui kontak star. Terminal U1, V1, W1 menerima L1, L2, L3 dari kontaktor main.

**Hubungan segitiga.** Saat kontaktor main dan delta menutup, kontaktor delta menyambungkan fasa jala-jala ke ujung belitan lain, sehingga terbentuk loop tertutup.

| Fasa jala-jala | Awal belitan (via main) | Ujung belitan lain (via delta) |
| --- | --- | --- |
| L1 | U1 | W2 |
| L2 | V1 | U2 |
| L3 | W1 | V2 |

**Larangan.** Kontaktor star dan delta tidak boleh menutup bersamaan. Terminal 2, 4, 6 keduanya bertemu pada W2, U2, V2, sehingga penutupan bersamaan menghubung-singkatkan L1, L2, dan L3.

### 3.2 Rangkaian Kontrol

Rangkaian kontrol memperoleh fasa L melalui mcb satu kutub, lalu kontak NC tombol off. Setelah itu terdapat satu titik percabangan: tombol on (NO) dan kontak bantu main 13-14 (NO) dipasang paralel sebagai penahan, dan hasilnya mengaliri kumparan main serta terminal 11 pada -S.

| Beban | Jalur arus dari L ke N |
| --- | --- |
| Kumparan main | mcb → off (NC) → on (NO) paralel main (NO 13-14) → kumparan main A1-A2 |
| Kumparan star | titik percabangan → -S (11-12) → delta (NC 11-12) → kumparan star |
| Kumparan delta | titik percabangan → -S (11-14) → star (NC 11-12) → kumparan delta |
| Lampu off | main (NC 11-12) → lampu off |
| Lampu star | star (NO 13-14) → lampu star |
| Lampu delta | delta (NO 13-14) → lampu delta |

Kontak NC delta yang diserikan dengan kumparan star, dan kontak NC star yang diserikan dengan kumparan delta, membentuk pengunci silang (interlock) listrik. Pengunci ini mencegah larangan pada subbab 3.1.

### 3.3 Urutan Kerja

1. **Kondisi awal.** mcb dalam keadaan ON dan tidak ada kumparan yang aktif. Kontak NC main menutup sehingga lampu off menyala.
2. **Tombol on ditekan.** Kumparan main aktif. Kontak 13-14 main menutup dan menahan arus pada kumparan main; kontak NC main membuka sehingga lampu off padam.
3. **Fase bintang.** Arus mengalir melalui -S (11-12) dan kontak NC delta ke kumparan star. Kontaktor star menutup, lampu star menyala, dan motor berputar pada hubungan bintang dengan arus start sekitar sepertiga arus start DOL.
4. **Perpindahan.** Setelah putaran mendekati nominal, -S ditekan. Kontak 11-12 membuka, kumparan star padam, dan kontak NC star kembali menutup.
5. **Fase segitiga.** Kontak 11-14 pada -S menutup, dan arus mengalir melalui kontak NC star ke kumparan delta. Kontaktor delta menutup, lampu delta menyala, lampu star padam, dan motor berputar pada hubungan segitiga.
6. **Penghentian.** Tombol off ditekan. Semua kumparan padam, seluruh kontak kembali ke posisi awal, dan motor berhenti.

&#91;embedded content: keadaan rangkaian · 3 keadaan, 3 perintah\]

Diagram merangkum tiga keadaan rangkaian; tombol off dapat menghentikan motor dari keadaan bintang maupun segitiga.

### 3.4 Catatan Analisis Gambar

- Kumparan delta pada gambar tidak memiliki kontak penahan. Jika -S berupa tombol tekan dengan pegas pengembali, -S harus ditahan selama motor berjalan pada hubungan segitiga; bila dilepas, kontaktor delta padam dan rangkaian kembali ke hubungan bintang.
- Kontak bantu TOR (95-96) tidak digambarkan pada rangkaian kontrol. Pada instalasi sesungguhnya, kontak NC tersebut perlu diserikan agar beban lebih memutus kumparan main.
- Cabang lampu indikator disambung pada fasa L di sisi hulu mcb kontrol, sehingga lampu off tetap menyala saat mcb kontrol dibuka.

## Bab 4. Simulasi

Simulasi memverifikasi urutan kerja dan pengunci silang rangkaian sebelum dirakit pada panel, sehingga kesalahan penyambungan dapat diperbaiki tanpa risiko terhadap peralatan. Prosedur berikut berlaku pada perangkat lunak simulasi kelistrikan, misalnya CADe SIMU, yang tampilan simbolnya menyerupai gambar acuan.

### 4.1 Tujuan

- Memastikan rangkaian daya membentuk hubungan bintang dan hubungan segitiga dengan benar.
- Memastikan urutan kerja kontaktor sesuai subbab 3.3.
- Mengamati fungsi kontak penahan dan pengunci silang.

### 4.2 Komponen Simulasi

| Komponen | Jumlah | Keterangan |
| --- | --- | --- |
| Sumber tiga fasa dan netral | 1 | L1, L2, L3, N |
| mcb tiga kutub | 1 | Rangkaian daya |
| mcb satu kutub | 1 | Rangkaian kontrol |
| Kontaktor tiga kutub | 3 | main, star, delta; masing-masing dengan kontak bantu 1 NO dan 1 NC |
| Thermal overload relay (TOR) | 1 | -F |
| Motor induksi tiga fasa enam terminal | 1 | -M |
| Tombol tekan NC | 1 | off |
| Tombol tekan NO | 1 | on |
| Tombol tekan pindah (changeover) | 1 | -S |
| Lampu indikator | 3 | off, star, delta |

### 4.3 Prosedur

1. Gambar rangkaian daya mengikuti tabel koneksi pada subbab 3.1.
2. Gambar rangkaian kontrol mengikuti tabel jalur arus pada subbab 3.2.
3. Beri label pada kontak bantu sesuai nama kontaktor pemiliknya (main, star, delta) agar kontak dan kumparan saling berpasangan.
4. Periksa ulang rangkaian: kontak NC delta seri dengan kumparan star, dan kontak NC star seri dengan kumparan delta.
5. Jalankan simulasi, tutup mcb, lalu lakukan skenario uji pada subbab 4.4 secara berurutan.
6. Catat hasil pengamatan pada kolom yang tersedia.

### 4.4 Skenario Uji

| No | Aksi | Hasil yang diharapkan | Hasil pengamatan |
| --- | --- | --- | --- |
| 1 | mcb ditutup, tanpa aksi lain | Semua kumparan padam, lampu off menyala, motor diam |  |
| 2 | -S ditekan sebelum on | Tidak ada kumparan yang aktif |  |
| 3 | on ditekan lalu dilepas | main dan star aktif, lampu star menyala, lampu off padam, motor berputar pada hubungan bintang; main tetap aktif setelah on dilepas |  |
| 4 | -S ditekan dan ditahan | star padam, delta aktif, lampu delta menyala, lampu star padam, motor berputar pada hubungan segitiga |  |
| 5 | -S dilepas saat delta aktif | delta padam dan star aktif kembali (menunjukkan delta tanpa kontak penahan) |  |
| 6 | off ditekan | Semua kumparan padam, lampu off menyala, motor berhenti |  |

### 4.5 Analisis Hasil

Jawablah pertanyaan berikut berdasarkan hasil simulasi.

1. Mengapa kumparan star tidak dapat aktif ketika kontaktor delta sedang aktif?
2. Apa akibat penutupan kontaktor star dan delta secara bersamaan pada rangkaian daya?
3. Apa fungsi kontak bantu main 13-14 pada rangkaian kontrol?
4. Bagaimana rangkaian dimodifikasi agar -S cukup ditekan satu kali?

**Pengembangan.** Pada praktik industri, perpindahan bintang ke segitiga umumnya dilakukan otomatis dengan relai waktu tunda ON (timer). Tombol -S pada gambar melakukan fungsi tersebut secara manual.

## Bab 5. Praktik

Praktik merakit, menguji, dan mengukur rangkaian starter bintang-segitiga pada panel dengan mengikuti gambar acuan dan hasil simulasi pada Bab 4.

### 5.1 Tujuan

- Merakit rangkaian daya dan rangkaian kontrol starter bintang-segitiga sesuai gambar.
- Menguji urutan kerja kontaktor secara aman.
- Mengukur arus pada hubungan bintang dan hubungan segitiga, lalu membandingkannya dengan teori.

### 5.2 Keselamatan dan Kesehatan Kerja

- Kenakan alat pelindung diri: sepatu isolasi, kacamata pelindung, dan pakaian kerja.
- Rakit dan ubah kabel hanya saat mcb OFF dan sumber telah dipastikan tidak bertegangan dengan alat ukur.
- Periksa pelat nama motor sebelum merakit, dan pastikan tegangan belitan pada hubungan segitiga sama dengan tegangan jala-jala.
- Atur TOR pada arus nominal motor.
- Jangan menyentuh terminal atau penghantar saat rangkaian bertegangan.
- Laporkan setiap gangguan atau kelainan kepada instruktur sebelum melanjutkan.

### 5.3 Alat dan Bahan

| Alat atau bahan | Keterangan | Jumlah |
| --- | --- | --- |
| Panel atau papan praktik | Dilengkapi rel dan terminal blok | 1 |
| mcb | Tiga kutub dan satu kutub | 1 dan 1 |
| Kontaktor tiga kutub | Kumparan sesuai tegangan kontrol; kontak bantu 1 NO dan 1 NC | 3 |
| Thermal overload relay | Rentang arus mencakup arus nominal motor | 1 |
| Tombol tekan | NC (off), NO (on), changeover (-S) | 1 untuk masing-masing |
| Lampu indikator | Sesuai tegangan kontrol | 3 |
| Motor induksi tiga fasa | Enam terminal pada kotak terminal | 1 |
| Kabel | Luas penampang sesuai kemampuan hantar arus | Secukupnya |
| Perkakas tangan | Obeng, tang kupas, tang crimping | 1 set |
| Multimeter | Pengukuran kontinuitas dan tegangan | 1 |
| Tang ampere (clamp meter) | Pengukuran arus fasa | 1 |

### 5.4 Langkah Kerja

**A. Persiapan**

1. Catat data pelat nama motor: tegangan, arus nominal, dan hubungan belitan.
2. Pastikan mcb OFF dan sumber tidak bertegangan.
3. Atur TOR sesuai arus nominal motor.

**B. Perakitan rangkaian daya**

4. Sambungkan L1, L2, L3 ke mcb, kontaktor main, TOR, lalu terminal U1, V1, W1 motor.
5. Sambungkan cabang dari keluaran mcb ke terminal 1, 3, 5 kontaktor delta.
6. Sambungkan terminal 2, 4, 6 kontaktor delta ke W2, U2, V2 motor.
7. Hubungkan terminal 1, 3, 5 kontaktor star satu sama lain, lalu sambungkan terminal 2, 4, 6 kontaktor star ke W2, U2, V2 yang sama dengan sambungan delta.

**C. Perakitan rangkaian kontrol**

8. Rakit rangkaian kontrol sesuai tabel jalur arus pada subbab 3.2, termasuk kontak penahan main dan pengunci silang NC delta dan NC star.

**D. Pemeriksaan tanpa tegangan**

9. Ukur kontinuitas antarfasa pada sisi keluaran mcb saat semua kontaktor tidak aktif; hasilnya harus terbuka.
10. Tekan kontaktor star secara manual, lalu pastikan W2, U2, dan V2 saling kontinu.
11. Tekan kontaktor delta secara manual, lalu pastikan terminal 1 ke W2, 3 ke U2, dan 5 ke V2 kontinu.
12. Ukur tiap kumparan pada A1-A2; kumparan tidak boleh hubung singkat maupun terbuka.

**E. Pengujian**

13. Nyalakan mcb kontrol saja dengan mcb daya OFF. Lakukan skenario uji pada subbab 4.4 dan amati urutan kontaktor serta lampu.
14. Nyalakan mcb daya. Tekan on, lalu ukur arus salah satu fasa dengan tang ampere pada fase bintang.
15. Setelah putaran stabil, tekan dan tahan -S. Ukur arus pada fase segitiga.
16. Tekan off. Matikan mcb daya dan mcb kontrol, lalu lepaskan kabel dan rapikan alat.

**Lembar data pengamatan**

| Kondisi | Arus jala-jala (A) | Tegangan jala-jala (V) | Keterangan |
| --- | --- | --- | --- |
| Bintang, saat start |  |  |  |
| Bintang, putaran stabil |  |  |  |
| Segitiga, putaran stabil |  |  |  |

Bandingkan arus start pada hubungan bintang dengan perhitungan teori sepertiga arus start langsung (subbab 1.2) dan uraikan penyebab selisihnya.

### 5.5 Pencarian Gangguan

| Gejala | Kemungkinan penyebab | Tindakan |
| --- | --- | --- |
| main tidak aktif saat on ditekan | mcb kontrol OFF, kontak NC off terbuka, kumparan putus, atau terminal longgar | Ukur tegangan pada A1-A2; periksa kontinuitas tombol off dan sambungan |
| main padam saat on dilepas | Kontak penahan main 13-14 belum terpasang atau salah terminal | Periksa pemasangan 13-14 paralel dengan tombol on |
| star tidak aktif | Kontak NC delta terbuka atau salah terminal; -S 11-12 tidak menutup | Periksa kontinuitas NC delta dan -S |
| delta tidak aktif setelah -S ditekan | Kontak NC star tidak menutup kembali; sambungan -S 11-14 salah | Periksa NC star dan sambungan 11-14 |
| mcb daya trip saat star atau delta aktif | Hubung singkat akibat salah sambung antara terminal star dan delta | Lakukan pemeriksaan kontinuitas tanpa tegangan (langkah 9 sampai 11) |
| Arus berlebih atau motor mendengung pada segitiga | Urutan sambungan belitan segitiga salah | Cocokkan dengan pasangan U1-W2, V1-U2, W1-V2 |
| Arah putar terbalik | Urutan fasa tertukar | Tukar dua fasa pada sisi masukan sebelum percabangan ke main dan delta |

### 5.6 Sistematika Laporan

Laporan praktik memuat judul, tujuan, alat dan bahan, gambar rangkaian, data pengamatan, analisis, dan kesimpulan.

## Evaluasi dan Rangkuman

### Soal Latihan

1. Jelaskan alasan arus start motor induksi pada hubungan bintang lebih kecil daripada pada hubungan segitiga.
2. Sebuah motor 380 V memiliki arus start langsung 84 A. Hitunglah arus start jala-jala bila motor diasut dengan metode bintang-segitiga.
3. Sebutkan syarat motor yang dapat diasut dengan metode bintang-segitiga.
4. Jelaskan akibat penutupan kontaktor star dan delta secara bersamaan pada rangkaian daya gambar acuan.
5. Tuliskan pasangan terminal motor yang membentuk hubungan segitiga pada gambar acuan.
6. Uraikan jalur arus yang mengaktifkan kumparan delta pada rangkaian kontrol.
7. Sebutkan dua keterbatasan rangkaian pada gambar acuan beserta usulan perbaikannya.

### Kunci Jawaban

| No | Jawaban ringkas |
| --- | --- |
| 1 | Pada hubungan bintang, tegangan tiap belitan adalah V\_L / √3, sehingga arus jala-jala turun menjadi sepertiga dari arus pada hubungan segitiga. |
| 2 | 84 A ÷ 3 = 28 A. |
| 3 | Motor berenam terminal; tegangan belitan hubungan segitiga sama dengan tegangan jala-jala; beban start ringan; waktu pada hubungan bintang cukup untuk mencapai putaran mendekati nominal. |
| 4 | Terminal 2, 4, 6 kedua kontaktor bertemu pada W2, U2, V2, sehingga L1, L2, L3 terhubung singkat; mcb akan trip dan kontak dapat rusak. |
| 5 | U1-W2 (L1), V1-U2 (L2), W1-V2 (L3). |
| 6 | L → mcb → off (NC) → on (NO) paralel main (NO 13-14) → -S (11-14) → NC star (11-12) → kumparan delta → N. |
| 7 | Kumparan delta tanpa kontak penahan: tambahkan kontak penahan atau gunakan selektor atau timer. Kontak bantu TOR tidak digambarkan: serikan kontak NC 95-96 pada rangkaian kontrol. |

**Kunci analisis simulasi (subbab 4.5).**

| No | Jawaban ringkas |
| --- | --- |
| 1 | Kontak NC delta membuka saat kontaktor delta aktif, sehingga jalur kumparan star terputus. |
| 2 | Terjadi hubung singkat antarfasa, seperti pada kunci nomor 4 di atas. |
| 3 | Menahan kumparan main tetap aktif setelah tombol on dilepas (self-holding). |
| 4 | Pasang kontak bantu NO tambahan milik delta paralel dengan kontak 11-14 pada -S, atau gunakan selektor dengan posisi terkunci, atau relai waktu. |

### Rangkuman

- Pengasutan bintang-segitiga menurunkan arus start dan torsi start menjadi sepertiga dari nilai pada hubungan segitiga.
- Rangkaian daya acuan memerlukan tiga kontaktor: main untuk sisi awal belitan, star untuk titik bintang, dan delta untuk menutup loop segitiga.
- Pengunci silang NC delta dan NC star mencegah hubung singkat antarfasa.
- Urutan kerja: on, hubungan bintang, -S, hubungan segitiga, off.
- Simulasi dan pemeriksaan kontinuitas tanpa tegangan wajib dilakukan sebelum rangkaian diberi tegangan pada praktik.
