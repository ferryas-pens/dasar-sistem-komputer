
# Modul Minggu 2
## Generasi Komputer & Arsitektur Von Neumann

---

### 1. Pendahuluan

Pada pertemuan kedua ini, kita akan mempelajari dua hal penting dalam sejarah dan konsep dasar sistem komputer:  

1. **Generasi komputer** – perjalanan panjang dari komputer generasi pertama hingga generasi kelima.  
2. **Arsitektur Von Neumann** – model arsitektur komputer yang menjadi dasar sebagian besar komputer modern.  

Pemahaman atas kedua topik ini sangat penting, karena akan menjadi fondasi bagi mahasiswa untuk memahami mata kuliah lanjutan seperti **arsitektur komputer**, **sistem operasi**, dan **organisasi komputer**.  

---

### 2. Generasi Komputer

Sejarah komputer dibagi ke dalam **lima generasi utama**, masing-masing ditandai dengan perubahan besar dalam teknologi perangkat keras dan perangkat lunak.  

#### a. Generasi Pertama (1940–1956): Tabung Vakum
- Teknologi utama: *vacuum tube*.  
- Ukuran sangat besar, konsumsi daya tinggi, cepat panas.  
- Contoh: **ENIAC**, **UNIVAC I**.  
- Kelemahan: boros listrik, rentan rusak.  
- Bahasa: hanya bahasa mesin (kode biner).  

#### b. Generasi Kedua (1956–1963): Transistor
- Teknologi utama: **transistor**.  
- Lebih kecil, hemat daya, lebih cepat.  
- Bahasa tingkat tinggi (COBOL, FORTRAN).  
- Contoh: IBM 1401, IBM 7090.  

#### c. Generasi Ketiga (1964–1971): IC (Integrated Circuit)
- Teknologi utama: **IC**.  
- Ukuran lebih kecil, harga lebih murah, performa meningkat.  
- Sistem operasi mulai digunakan.  
- Contoh: IBM System/360.  

#### d. Generasi Keempat (1971–Sekarang): Mikroprosesor
- Teknologi utama: **mikroprosesor**.  
- Contoh: Intel 4004 (mikroprosesor pertama).  
- Perangkat: PC, laptop, smartphone.  
- Software: GUI, jaringan, internet.  

#### e. Generasi Kelima (Sekarang & Masa Depan): AI dan Komputasi Modern
- Teknologi utama: **AI, cloud computing, quantum computing**.  
- Ciri khas: komputer dapat *belajar* dan *mengambil keputusan*.  
- Contoh: Google AI, IBM Watson, komputer kuantum.  

---

### 3. Arsitektur Von Neumann

#### a. Latar Belakang
Diperkenalkan oleh **John von Neumann (1945)**.  
Ide dasarnya: program dan data disimpan dalam memori yang sama.  

#### b. Komponen Utama
1. **CPU**: ALU dan CU.  
2. **Memori Utama**: menyimpan data & instruksi.  
3. **Input/Output**: perangkat masukan/keluaran.  
4. **Bus Sistem**: jalur komunikasi antar komponen.  

#### c. Prinsip Dasar
- Program disimpan di memori.  
- CPU menjalankan siklus fetch-decode-execute.  
- Data & instruksi berbagi memori yang sama.  

---

### 4. Perbandingan Von Neumann vs Harvard Architecture

| Aspek | Von Neumann | Harvard |
|-------|-------------|---------|
| Memori | Satu memori untuk data & instruksi | Memori terpisah untuk data & instruksi |
| Jalur Bus | Satu jalur bus | Jalur bus terpisah |
| Kelebihan | Sederhana, murah | Lebih cepat, efisien |
| Kekurangan | Bottleneck | Desain lebih kompleks |

---

### 5. Peran Arsitektur Komputer Modern

- PC, laptop, smartphone → Von Neumann.  
- Mikrokontroler (Arduino, ARM) → Harvard.  
- Superkomputer → paralelisme berbasis Von Neumann.  
- Masa depan → hibrid (AI chip, neuromorphic, quantum).  

---

### 6. Studi Kasus & Diskusi Kelas

- **Studi Kasus 1**: Mengapa smartphone masih menggunakan prinsip Von Neumann?  
- **Studi Kasus 2**: Mengapa Harvard lebih cocok untuk mikrokontroler?  

**Pertanyaan Diskusi**:  
1. Apakah bottleneck Von Neumann masih relevan di era multi-core?  
2. Bagaimana arsitektur komputer masa depan akan berubah?  

---

### 7. Ringkasan & Refleksi

- Komputer berkembang: tabung vakum → transistor → IC → mikroprosesor → AI.  
- Von Neumann = fondasi komputer modern.  
- Harvard = alternatif untuk embedded system.  
- Pemahaman ini penting untuk mata kuliah lanjutan.  

**Refleksi Mahasiswa**:  
- Bagaimana komputer generasi keenam akan didefinisikan?  
- Jika komputer kuantum berkembang, apakah Von Neumann ditinggalkan?  

---

### 8. Sumber Belajar Online

- [Computer Generations – TutorialsPoint](https://www.tutorialspoint.com/computer_fundamentals/computer_generations.htm)  
- [Von Neumann Architecture – GeeksforGeeks](https://www.geeksforgeeks.org/von-neumann-architecture/)  
- [Computer Basics – W3Schools](https://www.w3schools.in/computer-fundamentals/computer-basics)  

---

### 9. Latihan

1. Jelaskan perbedaan komputer generasi pertama dan keempat.  
2. Sebutkan kelebihan dan kekurangan Von Neumann Architecture.  
3. Mengapa bottleneck terjadi pada arsitektur Von Neumann?  
4. Bandingkan aplikasi Von Neumann (PC) dan Harvard (mikrokontroler).  
5. Diskusikan kemungkinan komputer generasi keenam.  
