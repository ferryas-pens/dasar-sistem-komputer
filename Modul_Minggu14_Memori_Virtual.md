
# Modul Minggu 14
## Sistem Memori Virtual

---

## 1. Pendahuluan

Memori utama (RAM) memiliki kapasitas terbatas, sementara aplikasi modern membutuhkan ruang memori yang jauh lebih besar. 
Sistem **memori virtual** memungkinkan komputer memberikan ilusi kepada setiap proses bahwa ia memiliki ruang alamat memori yang besar, 
meskipun RAM fisik terbatas. 

Dengan memori virtual, program dapat berjalan meski ukuran totalnya lebih besar dari RAM fisik, karena sebagian data disimpan di **disk (swap area)**.

---

## 2. Konsep Dasar Memori Virtual

- **Virtual Address Space**: ruang alamat logis yang terlihat oleh program.  
- **Physical Address Space**: alamat sebenarnya di RAM.  
- **Mapping**: translasi alamat virtual → fisik.  

**Diagram sederhana:**

```
[ Virtual Address ] → [ MMU ] → [ Physical Address ]
```

---

## 3. Paging

### 3.1 Konsep
- Virtual memory dibagi dalam **page** (ukuran tetap, misal 4 KB).  
- RAM dibagi dalam **frame** (ukuran sama dengan page).  
- **Page Table** menyimpan pemetaan page → frame.  

### 3.2 Contoh
- Page 0 → Frame 5  
- Page 1 → Frame 2  
- Page 2 → tidak ada (page fault)

**Diagram Paging:**

```
Virtual Address Space        Physical Memory
+---------+                  +---------+
| Page 0  | → Frame 5  --->  | Frame 5 |
| Page 1  | → Frame 2  --->  | Frame 2 |
| Page 2  | → Page Fault     | Frame 8 |
+---------+                  +---------+
```

---

## 4. Page Table & TLB

- **Page Table**: struktur data berisi informasi pemetaan page ke frame.  
- **TLB (Translation Lookaside Buffer)**: cache untuk mempercepat translasi alamat.  

**Perbandingan:**

| Aspek        | Page Table          | TLB                  |
|--------------|--------------------|----------------------|
| Lokasi       | Memori utama       | Cache khusus di CPU  |
| Kecepatan    | Lebih lambat       | Sangat cepat         |
| Fungsi       | Mapping lengkap    | Cache entry populer  |

---

## 5. Page Fault

- Terjadi bila page yang dibutuhkan tidak ada di RAM.  
- OS akan memuat page dari disk (swap).  
- Prosesnya:  
  1. CPU mengakses page.  
  2. TLB miss → Page Table miss.  
  3. Page Fault → OS ambil page dari disk.  
  4. Update Page Table.  
  5. Ulangi instruksi.  

**Diagram alur page fault:**

```
CPU → TLB → Page Table → Page Ada? 
   |         |
   |         NO → Page Fault → Load from Disk
   |
   YES → Physical Address
```

---

## 6. Segmentation

- Memori dibagi dalam segmen logis: code, data, stack.  
- Setiap segmen punya **base address** & **limit**.  

**Contoh tabel segmentasi:**

| Segmen  | Base Address | Limit |
|---------|--------------|-------|
| Code    | 1000         | 4000  |
| Data    | 5000         | 2000  |
| Stack   | 8000         | 1000  |

---

## 7. Paging vs Segmentation

| Aspek           | Paging              | Segmentation       |
|-----------------|---------------------|-------------------|
| Ukuran blok     | Tetap (fixed)       | Variabel (dinamis)|
| Sifat           | Fisik (teknis)      | Logis (programmer)|
| Fragmentasi     | Internal            | Eksternal         |
| Kompleksitas    | Lebih sederhana     | Lebih kompleks    |

---

## 8. Virtual Memory pada OS Modern

- **Windows**: menggunakan paging dengan swap file (`pagefile.sys`).  
- **Linux**: menggunakan paging, swap partition/file.  
- **MacOS**: mekanisme serupa, swap otomatis.  

**Diagram memori virtual modern:**

```
[ Program ] → [ Virtual Address Space ] → [ MMU ] → [ RAM / Disk ]
```

---

## 9. Thrashing

- Terjadi bila terlalu banyak page fault.  
- CPU sibuk memindahkan page daripada mengeksekusi instruksi.  
- Penyebab: RAM terlalu kecil, terlalu banyak proses.  
- Solusi: tambah RAM, batasi multiprogramming, algoritma penggantian page lebih baik.

---

## 10. Algoritma Penggantian Page

1. **FIFO (First In First Out)**  
   - Page yang paling lama masuk diganti lebih dulu.  

2. **LRU (Least Recently Used)**  
   - Page yang paling lama tidak digunakan diganti.  

3. **Optimal**  
   - Page yang tidak akan dipakai paling lama di masa depan diganti.  
   - Teoritis, tidak bisa diimplementasikan sempurna.

**Tabel simulasi LRU:**

| Akses | Frame (3 slot) | Page Fault? |
|-------|----------------|-------------|
| 1     | 1              | Ya          |
| 2     | 1,2            | Ya          |
| 3     | 1,2,3          | Ya          |
| 1     | 1,2,3          | Tidak       |
| 4     | 4,2,3          | Ya          |

---

## 11. Studi Kasus

- Program berukuran 8 GB dijalankan pada laptop dengan RAM 4 GB.  
- Dengan memori virtual, program tetap bisa berjalan:  
  - 4 GB pertama disimpan di RAM.  
  - Sisanya disimpan di disk (swap).  
- OS secara dinamis memindahkan page antara RAM dan disk.

---

## 12. Ringkasan & Refleksi

### Ringkasan
- Memori virtual memberikan ilusi RAM besar.  
- Paging → memori dibagi blok tetap.  
- Segmentation → memori dibagi blok logis.  
- TLB mempercepat translasi.  
- Page fault dan thrashing → tantangan utama.

### Refleksi
- Mengapa memori virtual dibutuhkan?  
- Bagaimana TLB mempercepat translasi alamat?  
- Apa penyebab thrashing dan cara mencegahnya?  

---

## 13. Sumber Belajar Online

- [Virtual Memory – GeeksforGeeks](https://www.geeksforgeeks.org/virtual-memory-in-operating-system/)  
- [Paging in OS – TutorialsPoint](https://www.tutorialspoint.com/operating_system/os_virtual_memory.htm)  
- [Memory Management Basics – W3Schools](https://www.w3schools.in/operating-system/memory-management)

---

## 14. Latihan

1. Jelaskan perbedaan alamat virtual vs fisik.  
2. Gambarkan diagram paging sederhana.  
3. Apa itu page fault? Bagaimana OS menanganinya?  
4. Bandingkan paging dan segmentation.  
5. Diskusikan penyebab dan solusi thrashing.  

---

## 15. Evolusi Sistem Memori Virtual

- **1960-an**: konsep pertama memori virtual di mainframe.  
- **1970-an**: paging diperkenalkan di Multics, kemudian UNIX.  
- **1980-an**: PC mulai menggunakan memori virtual (Windows 3.x).  
- **2000-an**: semua OS modern (Windows, Linux, MacOS) mengimplementasikan paging.  
- **Sekarang**: dukungan hardware (MMU, TLB besar, algoritma cerdas).  

**Diagram evolusi:**

```
Mainframe → Multics/UNIX → PC (Windows 3.x) → OS Modern (Linux, MacOS, Windows)
```

---
