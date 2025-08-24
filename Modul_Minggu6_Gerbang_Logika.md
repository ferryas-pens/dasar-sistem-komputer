
# Modul Minggu 6
## Gerbang Logika

---

### 1. Pendahuluan

Komputer digital dan seluruh perangkat elektronik modern bekerja dengan prinsip **logika biner** (0 dan 1). Blok dasar dari logika biner ini adalah **gerbang logika (logic gates)**, yaitu rangkaian elektronik sederhana yang menerima satu atau lebih input biner dan menghasilkan output biner sesuai aturan logika tertentu.

Semua sistem digital – mulai dari kalkulator, prosesor komputer, hingga smartphone – pada dasarnya adalah kombinasi dari jutaan hingga miliaran gerbang logika. Karena itu, memahami gerbang logika sangat penting sebagai dasar untuk belajar **sistem komputer, arsitektur komputer, sistem digital, dan elektronika digital**.

---

### 2. Gerbang Dasar

#### a. Gerbang NOT (Inverter)

| Input (A) | Output (Y=¬A) |
|-----------|---------------|
| 0         | 1             |
| 1         | 0             |

#### b. Gerbang AND

| A | B | Output (Y=A·B) |
|---|---|----------------|
| 0 | 0 | 0              |
| 0 | 1 | 0              |
| 1 | 0 | 0              |
| 1 | 1 | 1              |

#### c. Gerbang OR

| A | B | Output (Y=A+B) |
|---|---|----------------|
| 0 | 0 | 0              |
| 0 | 1 | 1              |
| 1 | 0 | 1              |
| 1 | 1 | 1              |

---

### 3. Gerbang Turunan

#### a. Gerbang NAND (NOT AND)

| A | B | Output (Y=¬(A·B)) |
|---|---|-------------------|
| 0 | 0 | 1                 |
| 0 | 1 | 1                 |
| 1 | 0 | 1                 |
| 1 | 1 | 0                 |

#### b. Gerbang NOR (NOT OR)

| A | B | Output (Y=¬(A+B)) |
|---|---|-------------------|
| 0 | 0 | 1                 |
| 0 | 1 | 0                 |
| 1 | 0 | 0                 |
| 1 | 1 | 0                 |

#### c. Gerbang XOR (Exclusive OR)

| A | B | Output (Y=A⊕B) |
|---|---|----------------|
| 0 | 0 | 0              |
| 0 | 1 | 1              |
| 1 | 0 | 1              |
| 1 | 1 | 0              |

#### d. Gerbang XNOR (Exclusive NOR)

| A | B | Output (Y=¬(A⊕B)) |
|---|---|-------------------|
| 0 | 0 | 1                 |
| 0 | 1 | 0                 |
| 1 | 0 | 0                 |
| 1 | 1 | 1                 |

---

### 4. Gerbang Universal

- **NOT** dari NAND: `NOT(A) = NAND(A,A)`
- **AND** dari NAND: `AND(A,B) = NAND(NAND(A,B), NAND(A,B))`
- **OR** dari NAND: `OR(A,B) = NAND(NAND(A,A), NAND(B,B))`

Hal serupa berlaku untuk NOR.

---

### 5. Analisis & Sintesis Rangkaian Logika

#### a. Analisis
Diberikan rangkaian, buat tabel kebenaran untuk mengetahui fungsinya.

Contoh: Rangkaian dengan input A dan B → OR → NOT
- Fungsi: Y = ¬(A+B) = NOR

#### b. Sintesis
Diberikan fungsi, rancang rangkaiannya.

Contoh: `F = (A+B)·C`
- Gunakan OR untuk A+B
- Gunakan AND dengan C

---

### 6. Studi Kasus

#### a. Alarm Keamanan Rumah
- Variabel: Pintu (P), Jendela (J), Sensor Aktif (S).
- Alarm berbunyi jika: **S=1 dan (P=1 atau J=1)**.
- Fungsi: `F = S·(P+J)`

#### b. Kontrol Lampu 2 Saklar
- Saklar1 (S1), Saklar2 (S2).
- Lampu nyala jika hanya salah satu saklar ON.
- Fungsi: `F = S1 ⊕ S2`

---

### 7. Ringkasan & Refleksi

- Gerbang logika adalah blok dasar sistem digital.
- Ada 3 gerbang dasar (NOT, AND, OR) dan 4 gerbang turunan (NAND, NOR, XOR, XNOR).
- NAND dan NOR adalah gerbang universal.
- Semua fungsi logika bisa dibentuk dari kombinasi gerbang.

**Refleksi:**  
- Mengapa NAND/NOR lebih praktis untuk implementasi fisik di IC?  
- Bagaimana memilih antara XOR vs OR dalam desain?  
- Apa dampak jumlah gerbang pada kecepatan prosesor?  

---

### 8. Sumber Belajar Online

- [Logic Gates – W3Schools](https://www.w3schools.in/digital-electronics/logic-gates)  
- [GeeksforGeeks – Logic Gates](https://www.geeksforgeeks.org/logic-gates/)  
- [TutorialsPoint – Logic Gates](https://www.tutorialspoint.com/digital_electronics/digital_electronics_logic_gates.htm)  

---

### 9. Latihan

1. Buat tabel kebenaran untuk `F = (A+B)·C`.  
2. Implementasikan `F = A⊕B` menggunakan hanya gerbang NAND.  
3. Desain rangkaian untuk `F = ¬A·B + A·¬B`. Apakah ini XOR?  
4. Sistem lampu menyala jika minimal 2 dari 3 saklar ON. Buat ekspresi dan rangkaiannya.  
