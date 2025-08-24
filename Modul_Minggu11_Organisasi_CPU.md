
# Modul Minggu 11
## Organisasi CPU

---

## 1. Pendahuluan

CPU (**Central Processing Unit**) sering disebut sebagai **otak komputer** karena bertanggung jawab mengendalikan semua operasi. 
Fungsi utama CPU adalah **menjalankan instruksi** dari program. 
Tahapan utamanya adalah: fetch, decode, execute, write-back.

---

## 2. Struktur Dasar CPU

- **ALU (Arithmetic Logic Unit)**: operasi aritmatika & logika.  
- **CU (Control Unit)**: mengatur aliran instruksi & data.  
- **Register**: penyimpanan cepat di CPU.  
- **Bus**: jalur komunikasi (data, alamat, kontrol).

**Diagram dasar CPU:**

```
          +------------------+
          |   Control Unit   |
          +--------+---------+
                   |
    +--------------+-------------+
    |                            |
+---v---+                    +---v---+
|  ALU  | <---- Data ---->   |Register|
+-------+                    +-------+
         \                  /
          \                /
            ---- BUS -----
```

---

## 3. Siklus Instruksi

1. **Fetch**: ambil instruksi dari memori.  
2. **Decode**: interpretasi instruksi.  
3. **Execute**: jalankan instruksi.  
4. **Write-back**: simpan hasil ke register/memori.

**Diagram Siklus Instruksi:**

```
[ Fetch ] → [ Decode ] → [ Execute ] → [ Write Back ]
     ^                                           |
     +-------------------------------------------+
```

---

## 4. Register dalam CPU

- **PC (Program Counter)**: alamat instruksi berikutnya.  
- **IR (Instruction Register)**: instruksi saat ini.  
- **ACC (Accumulator)**: hasil operasi ALU.  
- **MAR (Memory Address Register)**: alamat memori aktif.  
- **MDR (Memory Data Register)**: data dari/ke memori.  
- **General Purpose Register**: AX, BX, CX, DX.

**Contoh register x86:**

| Register | Fungsi                  |
|----------|-------------------------|
| EAX      | Accumulator             |
| EBX      | Base register           |
| ECX      | Counter                 |
| EDX      | Data register           |

---

## 5. Organisasi Jalur Data

- **Single Bus**: sederhana, bottleneck.  
- **Dual Bus**: lebih cepat.  
- **Multiple Bus**: throughput tinggi.

**Diagram Single Bus:**

```
[Register] --+    
             |-- BUS -- [ALU] -- [Memori]
[CU] --------+
```

---

## 6. Pipeline CPU

Tahapan umum 5-stage: IF, ID, EX, MEM, WB.

**Contoh Pipeline:**

| Cycle | IF | ID | EX | MEM | WB |
|-------|----|----|----|-----|----|
| 1     | I1 |    |    |     |    |
| 2     | I2 | I1 |    |     |    |
| 3     | I3 | I2 | I1 |     |    |
| 4     | I4 | I3 | I2 | I1  |    |
| 5     | I5 | I4 | I3 | I2  | I1 |

Masalah: data hazard, control hazard, structural hazard.

---

## 7. Interrupt & Exception

- **Interrupt**: sinyal eksternal (keyboard, I/O).  
- **Exception**: error internal (divide by zero).

---

## 8. Arsitektur CPU: CISC vs RISC

**CISC**: instruksi kompleks (x86).  
**RISC**: instruksi sederhana, pipeline efisien (ARM, MIPS).

**Perbandingan:**

| Aspek       | RISC          | CISC          |
|-------------|---------------|---------------|
| Instruksi   | Sederhana     | Kompleks      |
| Panjang     | Seragam       | Variabel      |
| Pipeline    | Mudah         | Sulit         |
| Contoh CPU  | ARM, MIPS     | x86, VAX      |

---

## 9. Studi Kasus

- **Von Neumann**: instruksi & data berbagi memori.  
- **Simulasi instruksi**: ADD R1, R2, R3 → Fetch, Decode, Execute, Write-back.  
- **Pipeline RISC vs Eksekusi CISC**.

---

## 10. Ringkasan & Refleksi

### Ringkasan
- CPU = ALU + CU + Register + Bus.  
- Siklus instruksi: fetch–decode–execute–write back.  
- Pipeline → throughput tinggi.  
- RISC vs CISC → dua filosofi desain.

### Refleksi
- Mengapa pipeline meningkatkan kinerja?  
- Peran register dalam eksekusi?  
- Bagaimana trade-off RISC vs CISC?

---

## 11. Sumber Belajar Online

- [CPU Organization – GeeksforGeeks](https://www.geeksforgeeks.org/cpu-central-processing-unit/)  
- [Instruction Cycle – TutorialsPoint](https://www.tutorialspoint.com/instruction-cycle-in-computer-organization)  
- [RISC vs CISC – W3Schools](https://www.w3schools.in/risc-and-cisc-architecture)

---

## 12. Latihan

1. Gambarkan diagram CPU sederhana.  
2. Jelaskan tahap siklus instruksi.  
3. Bandingkan single bus vs multiple bus.  
4. Simulasikan pipeline 3 instruksi.  
5. Diskusikan RISC vs CISC.

---

## 13. Evolusi CPU

### Intel 4004 (1971)
- CPU pertama, 4-bit, 740 kHz, 2.300 transistor.  
- Digunakan di kalkulator.

### Intel 8086 (1978)
- 16-bit, 29.000 transistor, awal arsitektur x86.  
- Mendukung hingga 1 MB memori.

### Intel 80386 (1985)
- 32-bit, 275.000 transistor.  
- Mendukung protected mode, multitasking.

### Intel Pentium (1993)
- Superscalar, pipeline lanjut.  
- 60 MHz, 3,1 juta transistor.

### Intel Core (2006)
- Masuk era multi-core.  
- Core Duo: prosesor dual-core pertama laptop.

### Intel Core i9 (2017–sekarang)
- Hingga 24 core, >5 GHz.  
- Cache besar, fabrikasi 7 nm.  
- Dipakai di gaming, AI, HPC.

### ARM Cortex
- Berbasis RISC, hemat daya.  
- Varian: Cortex-A (aplikasi), Cortex-M (mikrokontroler), Cortex-R (real-time).  
- Dipakai di smartphone, IoT, Apple M1/M2.

**Perbandingan Intel vs ARM:**

| Aspek         | Intel (x86)           | ARM (RISC)              |
|---------------|-----------------------|-------------------------|
| Filosofi      | CISC                  | RISC                    |
| Konsumsi daya | Tinggi                | Rendah                  |
| Target        | PC, Server            | Mobile, IoT, Embedded   |
| Performa      | Tinggi (GHz, core)    | Efisien, hemat daya     |
| Ekosistem     | Windows, Linux        | Android, iOS, Embedded  |

---
