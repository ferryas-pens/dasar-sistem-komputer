
# Modul Minggu 10
## Memori & Penyimpanan

---

## 1. Pendahuluan & Sejarah Memori

Komputer modern tidak dapat berjalan tanpa **memori**. Setiap instruksi CPU harus diambil dari memori, setiap data harus disimpan sebelum diproses. 
Performa komputer sangat dipengaruhi oleh kecepatan dan jenis memori.

### Sejarah Singkat Perkembangan Memori

1. **Punch Card (1890-an)**  
   Media awal penyimpanan data berbasis kertas dengan lubang.  
   Digunakan oleh Herman Hollerith untuk sensus AS.

2. **Magnetic Core Memory (1950-an – 1970-an)**  
   Terbuat dari cincin magnet kecil. Non-volatile, menjadi standar RAM komputer generasi awal.

3. **Semiconductor Memory (1970-an – sekarang)**  
   Digantikan oleh RAM berbasis transistor.  
   - **DRAM** (Dynamic RAM)  
   - **SRAM** (Static RAM)  

4. **ROM & Flash Memory**  
   Digunakan untuk firmware & penyimpanan jangka panjang.

5. **SSD (Solid State Drive)**  
   Menggantikan HDD mekanik dengan NAND flash.

6. **Memori Generasi Baru**  
   - MRAM, FRAM, NVRAM.  
   - 3D XPoint (Optane).

---

## 2. Konsep Dasar Memori

### 2.1 Satuan Penyimpanan

- **Bit**: unit terkecil (0/1).  
- **Nibble**: 4 bit.  
- **Byte**: 8 bit.  
- **Word**: jumlah bit sesuai arsitektur CPU (32-bit, 64-bit).

### 2.2 Addressing

- Setiap lokasi memori memiliki **alamat unik**.  
- CPU mengakses data melalui alamat ini.  
- Arsitektur 32-bit → 2^32 alamat (≈4GB).  
- Arsitektur 64-bit → 2^64 alamat.

### 2.3 Alignment & Endianness

- **Alignment**: data disimpan di alamat kelipatan tertentu.  
- **Big-endian**: byte paling signifikan disimpan di alamat terkecil.  
- **Little-endian**: byte paling signifikan di alamat terbesar.

---

## 3. Jenis Memori Utama

### 3.1 RAM (Random Access Memory)

#### a. DRAM (Dynamic RAM)

- Menyimpan data dalam kapasitor.  
- Butuh refresh berkala.  
- Murah, kapasitas besar.  
- Digunakan sebagai **main memory**.

#### b. SRAM (Static RAM)

- Menyimpan data dalam flip-flop.  
- Cepat, tidak butuh refresh.  
- Mahal, kapasitas kecil.  
- Digunakan sebagai **cache CPU**.

**Perbandingan DRAM vs SRAM**:

| Aspek        | DRAM                 | SRAM               |
|--------------|----------------------|--------------------|
| Penyimpanan  | Kapasitor            | Flip-Flop          |
| Refresh      | Perlu                | Tidak              |
| Kecepatan    | Lebih lambat         | Lebih cepat        |
| Biaya        | Murah                | Mahal              |
| Aplikasi     | RAM utama            | Cache CPU          |

---

### 3.2 ROM (Read Only Memory)

- Data permanen (non-volatile).  
- Digunakan untuk firmware.

Jenis ROM:  
- PROM: diprogram sekali.  
- EPROM: dihapus UV.  
- EEPROM: dihapus elektrik.  
- Flash: variasi EEPROM, digunakan di USB/SSD.

---

## 4. Hirarki Memori

Komputer menggunakan **hirarki memori** untuk menyeimbangkan kecepatan dan kapasitas.

**Urutan dari cepat ke lambat:**  
1. Register CPU  
2. Cache (L1, L2, L3)  
3. RAM  
4. SSD/HDD  
5. Tape/Optical/Cloud

**Diagram Hirarki Memori:**

```
Cepat ─► Register ─► Cache ─► RAM ─► SSD/HDD ─► Tape/Cloud ◄─ Lambat
Kecil ─►        ─►        ─►     ─►       ─►          ─► Besar
```

---

## 5. Penyimpanan Sekunder

### 5.1 HDD (Hard Disk Drive)

- Mekanik: piringan berputar.  
- Murah, kapasitas besar.  
- Lambat, rawan kerusakan.

### 5.2 SSD (Solid State Drive)

- NAND Flash.  
- Cepat, tahan guncangan.  
- Mahal per GB.

**Perbandingan HDD vs SSD**:

| Aspek       | HDD                  | SSD                |
|-------------|----------------------|--------------------|
| Teknologi   | Mekanik (disk)       | NAND Flash         |
| Kecepatan   | Lambat (ms)          | Cepat (µs)         |
| Ketahanan   | Mudah rusak          | Lebih awet         |
| Kapasitas   | Murah, besar         | Mahal per GB       |

### 5.3 Optical Storage

- CD, DVD, Blu-ray.  
- Digunakan untuk distribusi software, film.

### 5.4 Magnetic Tape

- Arsip jangka panjang.  
- Murah, kapasitas sangat besar.  
- Lambat.

---

## 6. Teknologi Memori Modern

1. **MRAM**: berbasis magnet, tahan lama.  
2. **FRAM**: menggunakan bahan ferroelektrik.  
3. **NVRAM**: RAM non-volatile.  
4. **3D XPoint (Intel Optane)**: kombinasi kecepatan RAM dan kapasitas SSD.

---

## 7. Studi Kasus

### 7.1 Perbandingan Waktu Akses

| Jenis Memori | Waktu Akses |
|--------------|-------------|
| Register     | < 1 ns      |
| Cache L1     | 1–2 ns      |
| Cache L2/L3  | 5–15 ns     |
| DRAM (RAM)   | 50–70 ns    |
| SSD          | ~100 µs     |
| HDD          | 5–10 ms     |

### 7.2 Cache Hit & Miss

- **Cache Hit**: data ditemukan di cache.  
- **Cache Miss**: data tidak ada di cache, harus diambil dari RAM.  

Formula **AMAT (Average Memory Access Time):**  
```
AMAT = Hit Time + Miss Rate × Miss Penalty
```

### 7.3 Virtual Memory

- RAM terbatas → OS gunakan sebagian HDD/SSD sebagai memori virtual.  
- Mekanisme paging.  
- Kelemahan: lambat, bisa terjadi thrashing.

---

## 8. Ringkasan & Refleksi

- Memori adalah inti sistem komputer.  
- Hirarki memori: trade-off kecepatan & kapasitas.  
- RAM: DRAM, SRAM.  
- ROM: PROM, EPROM, EEPROM, Flash.  
- HDD vs SSD: kapasitas vs kecepatan.  
- Teknologi baru menjembatani gap CPU–memori.

**Refleksi Mahasiswa:**  
- Mengapa kita tidak bisa membuat RAM sebesar HDD?  
- Bagaimana cache meningkatkan performa CPU?  
- Apa trade-off utama antara kapasitas, harga, dan kecepatan?

---

## 9. Sumber Belajar Online

- [Computer Memory – GeeksforGeeks](https://www.geeksforgeeks.org/types-of-computer-memory/)  
- [RAM vs ROM – TutorialsPoint](https://www.tutorialspoint.com/digital_electronics/digital_electronics_memory.htm)  
- [Memory Hierarchy – W3Schools](https://www.w3schools.in/operating-system/memory-hierarchy)  

---

## 10. Latihan

1. Bandingkan DRAM dan SRAM dari sisi biaya, kecepatan, aplikasi.  
2. Jelaskan perbedaan PROM, EPROM, EEPROM, Flash.  
3. Gambarkan hirarki memori komputer.  
4. Buat tabel perbandingan HDD vs SSD.  
5. Hitung AMAT bila hit time=1ns, miss rate=5%, miss penalty=50ns.

---

