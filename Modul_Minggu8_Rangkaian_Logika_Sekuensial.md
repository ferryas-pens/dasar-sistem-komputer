
# Modul Minggu 8
## Rangkaian Logika Sekuensial: Latch & Flip-Flop

---

### 1. Pendahuluan

Rangkaian digital terbagi menjadi dua kelompok besar:  
1. **Rangkaian Kombinasional** → output hanya bergantung pada input saat itu.  
2. **Rangkaian Sekuensial** → output bergantung pada **input saat ini + keadaan sebelumnya**.  

Rangkaian sekuensial menggunakan elemen penyimpanan (memori), sehingga dapat menyimpan **state**. Karena sifat inilah, rangkaian sekuensial digunakan dalam:  
- Register penyimpanan data,  
- Counter (pencacah),  
- Memory cell,  
- CPU pipeline.  

Dua elemen fundamental dalam rangkaian sekuensial adalah **Latch** dan **Flip-Flop**.  

---

### 2. Konsep Dasar

- **Latch**: elemen memori sederhana, bekerja secara **level-triggered** → output mengikuti input ketika enable aktif.  
- **Flip-Flop**: elemen memori lebih stabil, bekerja secara **edge-triggered** → output berubah hanya pada tepi naik atau tepi turun dari clock.  

Latch lebih sederhana tetapi rentan terhadap **glitch**, sementara flip-flop lebih banyak digunakan karena stabilitas sinkronisasi dengan clock.  

---

### 3. Jenis Latch

#### a. SR Latch (Set-Reset Latch)

| S | R | Q (next) | Keterangan |
|---|---|----------|------------|
| 0 | 0 | Q(prev)  | Tidak berubah |
| 0 | 1 | 0        | Reset |
| 1 | 0 | 1        | Set |
| 1 | 1 | ?        | Invalid |

Masalah: kondisi S=1 dan R=1 tidak terdefinisi.

#### b. D Latch (Data Latch)

| EN | D | Q (next) |
|----|---|----------|
| 0  | X | Q(prev)  |
| 1  | 0 | 0        |
| 1  | 1 | 1        |

---

### 4. Jenis Flip-Flop

#### a. SR Flip-Flop
- Sama dengan SR Latch, tetapi dikendalikan oleh clock.  
- Masalah kondisi terlarang masih ada.  

#### b. D Flip-Flop

| CLK Edge | D | Q(next) |
|----------|---|---------|
| ↑        | 0 | 0       |
| ↑        | 1 | 1       |
| -        | X | Q(prev) |

#### c. JK Flip-Flop

| J | K | Q(next) | Keterangan |
|---|---|---------|------------|
| 0 | 0 | Q(prev) | Tidak berubah |
| 0 | 1 | 0       | Reset |
| 1 | 0 | 1       | Set |
| 1 | 1 | ¬Q      | Toggle |

#### d. T Flip-Flop (Toggle)

| T | CLK Edge | Q(next) |
|---|----------|---------|
| 0 | ↑        | Q(prev) |
| 1 | ↑        | ¬Q      |

---

### 5. Analisis & Aplikasi

- **Register**: kumpulan D Flip-Flop untuk menyimpan data biner paralel.  
- **Counter**: menghitung urutan biner sesuai clock. Bisa sinkron/asinkron.  
- **Shift Register**: menggeser data ke kiri/kanan, digunakan pada komunikasi serial.  

---

### 6. Studi Kasus

#### a. Register 4-bit dengan D Flip-Flop
- Input: D0..D3, Output: Q0..Q3.  
- Semua Flip-Flop dikendalikan clock.  

#### b. Counter 2-bit dengan T Flip-Flop
- Dua T Flip-Flop, T=1 selalu.  
- Menghitung urutan: 00 → 01 → 10 → 11 → 00.  

---

### 7. Ringkasan & Refleksi

- Rangkaian sekuensial menyimpan informasi (state).  
- Latch: level-triggered, rawan glitch.  
- Flip-Flop: edge-triggered, stabil.  
- Jenis Flip-Flop: SR, D, JK, T.  
- Aplikasi: register, counter, shift register, memory.  

**Refleksi:**  
- Mengapa flip-flop lebih sering dipakai dibanding latch?  
- Apa perbedaan JK vs T Flip-Flop?  
- Bagaimana clock memengaruhi sinkronisasi sistem digital?  

---

### 8. Sumber Belajar Online

- [SR Latch & Flip-Flops – GeeksforGeeks](https://www.geeksforgeeks.org/latches-and-flip-flops-in-digital-electronics/)  
- [Flip-Flops – TutorialsPoint](https://www.tutorialspoint.com/digital_electronics/digital_electronics_flip_flops.htm)  
- [Sequential Circuits – W3Schools](https://www.w3schools.in/digital-electronics/sequential-circuits)  

---

### 9. Latihan

1. Buat tabel kebenaran SR Latch berbasis NOR.  
2. Desain D Latch dari SR Latch + gerbang tambahan.  
3. Buat tabel kebenaran JK Flip-Flop.  
4. Rancang counter 2-bit sinkron menggunakan T Flip-Flop.  
5. Bandingkan sensitivitas clock antara latch dan flip-flop.  
