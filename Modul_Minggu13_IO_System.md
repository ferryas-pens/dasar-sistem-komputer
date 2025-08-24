
# Modul Minggu 13
## Sistem Input/Output (I/O)

---

## 1. Pendahuluan

Sistem Input/Output (I/O) adalah penghubung utama antara komputer dengan dunia luar. 
Tanpa I/O, CPU dan memori hanyalah mesin yang beroperasi dalam isolasi, tanpa kemampuan untuk menerima data dari pengguna atau memberikan hasil keluarannya.

Contoh perangkat I/O:
- **Input**: keyboard, mouse, scanner, mikrofon.  
- **Output**: monitor, printer, speaker.  
- **Storage**: hard disk, SSD, USB.  
- **Communication**: kartu jaringan, modem.  

I/O berfungsi sebagai "jembatan komunikasi" yang memungkinkan interaksi manusia dan lingkungan dengan sistem komputer.

---

## 2. Fungsi Sistem I/O

- **Transfer Data**: memindahkan data antara CPU/memori dengan perangkat.  
- **Sinkronisasi**: menyamakan kecepatan CPU (GHz) dengan I/O (kHz–MHz).  
- **Kontrol Perangkat**: mengirim sinyal start/stop/acknowledge.  
- **Error Handling**: mendeteksi dan menangani kesalahan transfer data.  
- **Interupsi**: memberi sinyal CPU saat ada peristiwa eksternal.

**Diagram umum sistem I/O:**

```
   +---------+         +---------+
   |  CPU    | <-----> | Memory  |
   +---------+         +---------+
        |                   ^
        v                   |
   +---------+    Data   +---------+
   |   CU    | <-------> | I/O Ctrl| <----> [ Perangkat ]
   +---------+           +---------+
```

---

## 3. Teknik Transfer Data

### 3.1 Programmed I/O
- CPU langsung membaca/menulis data dari perangkat.  
- CPU aktif menunggu (busy-wait).  
- Sederhana tapi **tidak efisien**.

### 3.2 Interrupt-Driven I/O
- CPU memberi perintah, lalu melanjutkan pekerjaan lain.  
- Saat perangkat siap, perangkat mengirim interrupt.  
- CPU berhenti sebentar untuk melayani interrupt.

### 3.3 Direct Memory Access (DMA)
- Perangkat dapat mentransfer data langsung ke memori tanpa CPU.  
- DMA controller mengatur transfer data.  
- Sangat efisien untuk transfer data besar (disk, jaringan).  

**Diagram DMA:**

```
[ CPU ] ←→ [ Memory ]
    ↑
    │
 [ DMA Controller ] ←→ [ Perangkat I/O ]
```

---

## 4. Pemetaan I/O

### 4.1 Isolated I/O
- Ruang alamat terpisah untuk instruksi I/O.  
- Instruksi khusus untuk I/O (IN, OUT).  

### 4.2 Memory-Mapped I/O
- Perangkat I/O dipetakan ke alamat memori.  
- CPU menggunakan instruksi load/store biasa.  
- Lebih fleksibel, digunakan pada CPU modern.

**Perbandingan:**

| Aspek          | Isolated I/O        | Memory-Mapped I/O |
|----------------|---------------------|-------------------|
| Instruksi      | Khusus (IN/OUT)     | Load/Store umum   |
| Kesederhanaan  | Lebih sederhana     | Lebih kompleks    |
| Fleksibilitas  | Rendah              | Tinggi            |
| Contoh CPU     | x86 lama            | ARM, RISC-V       |

---

## 5. Struktur Sistem I/O

1. **Controller**  
   - Mengendalikan perangkat I/O.  
   - Mengubah sinyal CPU menjadi format perangkat.

2. **Buffer**  
   - Menyimpan data sementara.  
   - Mengurangi perbedaan kecepatan CPU dan perangkat.

3. **Port I/O**  
   - Jalur komunikasi antara CPU dan perangkat.

**Diagram internal I/O controller:**

```
   [ CPU ] ←→ [ I/O Controller ] ←→ [ Perangkat ]
                  |   |
              [ Buffer ][ Control Logic ]
```

---

## 6. Interrupt dalam I/O

### 6.1 Polling
- CPU mengecek status perangkat secara berkala.  
- Memboroskan siklus CPU.

### 6.2 Interrupt
- Perangkat memberi sinyal CPU bila siap.  
- CPU melompat ke **Interrupt Service Routine (ISR)**.

### 6.3 Vectored Interrupt
- Perangkat memberi alamat ISR spesifik.  
- CPU langsung tahu rutin mana yang dipanggil.

**Diagram interrupt:**

```
[ Perangkat ] --INT--> [ CPU ]
                        |
                   [ Interrupt Vector Table ]
                        |
                   [ Service Routine ]
```

---

## 7. Studi Kasus

### 7.1 Keyboard
- Setiap tombol ditekan → menghasilkan kode scan.  
- Mengirim interrupt ke CPU.  
- CPU membaca buffer keyboard.

### 7.2 Printer
- Memiliki buffer internal.  
- CPU kirim data → printer cetak.  
- Printer kirim interrupt "ready" bila siap menerima data baru.

### 7.3 Hard Disk
- Menggunakan DMA.  
- Data dipindahkan langsung ke RAM.  
- CPU hanya mengontrol awal/akhir transfer.

---

## 8. Ringkasan & Refleksi

### Ringkasan
- Sistem I/O memungkinkan komputer berinteraksi dengan dunia luar.  
- Tiga teknik utama: Programmed I/O, Interrupt-driven, DMA.  
- Pemetaan I/O bisa isolated atau memory-mapped.  
- Interrupt meningkatkan efisiensi.  
- DMA mempercepat transfer data besar.

### Refleksi Mahasiswa
- Mengapa DMA lebih efisien untuk transfer besar?  
- Apa kelebihan memory-mapped I/O?  
- Bagaimana CPU menangani multiple interrupt?  

---

## 9. Sumber Belajar Online

- [Input Output Organization – GeeksforGeeks](https://www.geeksforgeeks.org/input-output-organization-in-computer-architecture/)  
- [DMA in Computer Architecture – TutorialsPoint](https://www.tutorialspoint.com/computer_organization/direct_memory_access.htm)  
- [I/O System Basics – W3Schools](https://www.w3schools.in/computer-organization/io-system)

---

## 10. Latihan

1. Jelaskan perbedaan Programmed I/O, Interrupt I/O, dan DMA.  
2. Gambarkan diagram alur DMA.  
3. Apa perbedaan Memory-Mapped I/O dan Isolated I/O?  
4. Berikan contoh bagaimana interrupt keyboard bekerja.  
5. Diskusikan kelebihan vectored interrupt.

---

## 11. Evolusi Sistem I/O

### 11.1 Generasi Awal
- CPU melakukan polling langsung ke perangkat.  
- Tidak efisien.

### 11.2 Interrupt I/O
- Diperkenalkan untuk mengurangi beban CPU.  

### 11.3 DMA (1960-an)
- Digunakan pada komputer mainframe dan minicomputer.  
- Memungkinkan transfer data cepat.

### 11.4 Bus Modern (PCIe, USB, SATA)
- Standar I/O modern memungkinkan bandwidth besar.  
- USB-C: mendukung data, video, daya sekaligus.  
- PCIe: digunakan untuk GPU, NVMe SSD.

**Diagram evolusi:**

```
Polling → Interrupt → DMA → Bus Standard (PCIe/USB)
```

---

