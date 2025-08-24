
# Modul Minggu 12
## Unit Kontrol (Control Unit)

---

## 1. Pendahuluan

Control Unit (CU) adalah komponen inti dalam CPU yang bertugas mengatur aliran instruksi dan data di dalam prosesor. 
CU tidak melakukan perhitungan aritmatika atau logika secara langsung, tetapi memastikan bahwa semua bagian CPU bekerja sesuai urutan yang benar.

Tanpa CU, CPU tidak akan tahu instruksi apa yang harus diambil, bagaimana mendekode instruksi, dan kapan mengeksekusinya. 
CU adalah "pengatur lalu lintas" dari semua aktivitas internal CPU.

---

## 2. Fungsi Control Unit

- Mengambil instruksi dari memori.  
- Mendekode instruksi menjadi sinyal kontrol.  
- Mengirim sinyal ke ALU, register, dan perangkat I/O.  
- Mengatur siklus instruksi (fetch–decode–execute–write back).  
- Menangani interupsi.  

**Diagram sederhana CU:**

```
[ Memory ] → (Fetch) → [ Control Unit ] → (Decode) → [ ALU / Register / I/O ]
```

---

## 3. Jenis Control Unit

### 3.1 Hardwired Control Unit
- Dibangun menggunakan rangkaian logika tetap (kombinasional + sekuensial).  
- Cepat, efisien, cocok untuk CPU RISC.  
- Kekurangan: sulit dimodifikasi jika ada perubahan instruksi.

### 3.2 Microprogrammed Control Unit
- Menggunakan microprogram (sekumpulan microinstruction) disimpan di ROM.  
- Fleksibel, mudah diubah.  
- Cocok untuk CPU CISC.  
- Lebih lambat dibanding hardwired.

**Perbandingan Hardwired vs Microprogrammed:**

| Aspek        | Hardwired CU        | Microprogrammed CU |
|--------------|---------------------|--------------------|
| Kecepatan    | Sangat cepat        | Lebih lambat       |
| Fleksibilitas| Rendah              | Tinggi             |
| Kompleksitas | Sederhana           | Lebih kompleks     |
| Contoh CPU   | RISC (ARM, MIPS)    | CISC (x86)         |

---

## 4. Komponen Control Unit

1. **Decoder**: menerjemahkan opcode instruksi.  
2. **Sequencer**: menentukan urutan langkah eksekusi.  
3. **Control Signal Generator**: menghasilkan sinyal kontrol.  
4. **Clock Generator**: sinkronisasi semua operasi CPU.  

**Diagram internal CU:**

```
        +----------------+
Instr → |    Decoder     | → Control Signals
        +----------------+
                ↓
        +----------------+
        |   Sequencer    |
        +----------------+
```

---

## 5. Siklus Instruksi dengan Control Unit

1. CU mengambil instruksi (Fetch).  
2. CU mendekode instruksi (Decode).  
3. CU mengirim sinyal ke ALU/memori (Execute).  
4. CU menyimpan hasil ke register (Write Back).  

**Diagram:**

```
[ PC ] → [ MAR ] → [ Memory ]
   ↓           ↓
 [ IR ] ← [ MDR ] ←→ [ CU ] → Sinyal → [ ALU / Register ]
```

---

## 6. Microinstruction & Control Word

- **Microinstruction**: instruksi tingkat rendah dalam CU.  
- **Control Word**: pola bit yang menentukan sinyal kontrol.  
- Disimpan dalam **Control Store** (ROM/EEPROM).  

**Contoh Control Word:**

| Bit | Fungsi        |
|-----|---------------|
| 0   | Load PC       |
| 1   | Increment PC  |
| 2   | Load IR       |
| 3   | Read Memory   |
| 4   | Write Memory  |
| 5   | Enable ALU    |

---

## 7. Studi Kasus

### 7.1 Hardwired CU (RISC)
- Instruksi sederhana, pipeline efisien.  
- Cocok untuk ARM, MIPS.

### 7.2 Microprogrammed CU (CISC)
- Instruksi kompleks (misal x86).  
- Instruksi `ADD [AX], BX` → dipecah menjadi banyak microinstruction.  

### 7.3 Contoh Eksekusi Instruksi ADD
Instruksi: `ADD R1, R2, R3`  
1. Fetch: CU ambil instruksi.  
2. Decode: CU pahami bahwa operasi adalah penjumlahan.  
3. Execute: CU aktifkan ALU untuk menambah R2 + R3.  
4. Write-back: hasil disimpan ke R1.  

---

## 8. Ringkasan & Refleksi

### Ringkasan
- CU mengatur jalannya instruksi di CPU.  
- Ada dua jenis CU: hardwired & microprogrammed.  
- Hardwired: cepat, sederhana.  
- Microprogrammed: fleksibel, tapi lebih lambat.  

### Refleksi
- Mengapa CPU modern sering menggabungkan keduanya?  
- Apa kelebihan microprogrammed CU pada CISC?  
- Mengapa RISC lebih cocok dengan hardwired CU?  

---

## 9. Sumber Belajar Online

- [Control Unit in Computer Architecture – GeeksforGeeks](https://www.geeksforgeeks.org/control-unit-in-computer-architecture/)  
- [Microprogrammed vs Hardwired Control Unit – TutorialsPoint](https://www.tutorialspoint.com/computer_organization/microprogrammed_vs_hardwired_control_unit.htm)  
- [Control Unit Basics – W3Schools](https://www.w3schools.in/computer-organization/control-unit)

---

## 10. Latihan

1. Gambarkan diagram CU sederhana.  
2. Bandingkan kelebihan/kekurangan hardwired vs microprogrammed CU.  
3. Buat contoh microinstruction untuk operasi `ADD R1, R2`.  
4. Jelaskan peran decoder dalam CU.  
5. Diskusikan mengapa CU penting dalam pipeline.  

---

## 11. Evolusi Control Unit dalam CPU

### Generasi Awal (1950–1970)
- Menggunakan **hardwired CU**.  
- Instruksi sederhana, cocok untuk komputer generasi awal.  

### Generasi Mikroprosesor (1970–1990)
- CPU x86 memperkenalkan **microprogrammed CU** untuk mendukung instruksi kompleks.  

### CPU Modern (2000–sekarang)
- Menggabungkan hardwired + microprogrammed.  
- Contoh: Intel Core i9 menggunakan CU hybrid untuk efisiensi pipeline.  
- ARM Cortex tetap menggunakan CU hardwired untuk efisiensi daya.  

**Diagram Konsep Hybrid CU:**

```
            +-------------------+
Instruksi → | Hardwired Control | → Instruksi sederhana
            +-------------------+
                       ↓
            +-------------------+
            | Microprogrammed   | → Instruksi kompleks
            +-------------------+
```

---

