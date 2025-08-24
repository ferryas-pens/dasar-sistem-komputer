
# Modul Minggu 5
## Aljabar Boolean & Peta Karnaugh (K-map)

---

### 1. Pendahuluan

Aljabar Boolean adalah dasar dari **logika digital** yang dipakai untuk merancang **rangkaian kombinasional** (adder, encoder/decoder, MUX/DEMUX) hingga **rangkaian sekuensial** (flip-flop, register, counter). Dengan menguasai aljabar Boolean, kita dapat:
- Memodelkan fungsi logika sebagai ekspresi matematika.
- Menyederhanakan (minimisasi) ekspresi agar rangkaian menjadi **lebih sederhana, lebih cepat, dan lebih hemat biaya**.
- Mentransformasikan fungsi logika menjadi implementasi gerbang yang efisien.

---

### 2. Variabel & Operator Boolean

- Nilai Boolean: `0` (false), `1` (true).
- Operator dasar: AND (`·`), OR (`+`), NOT (`¬` atau `'`).
- Operator turunan: NAND, NOR, XOR, XNOR.

Contoh ekspresi:  
`F(A, B, C) = A·B + ¬A·C`

---

### 3. Hukum Dasar Aljabar Boolean

- Identitas: `A+0=A`, `A·1=A`  
- Komplemen: `A+¬A=1`, `A·¬A=0`  
- Komutatif, Asosiatif, Distributif  
- De Morgan: `¬(A·B)=¬A+¬B`, `¬(A+B)=¬A·¬B`  

---

### 4. Bentuk Kanonik

- **SOP (Sum of Products)** → penjumlahan suku hasil kali.  
- **POS (Product of Sums)** → perkalian suku penjumlahan.  
- Minterm dan Maxterm digunakan untuk membuat bentuk kanonik.

---

### 5. Peta Karnaugh (K-map)

K-map adalah metode visual untuk menyederhanakan fungsi Boolean.

#### 5.1 K-map 2 Variabel

|     | B=0 | B=1 |
|-----|-----|-----|
| A=0 |     |     |
| A=1 |     |     |

Contoh fungsi `F=Σm(1,3)` → isi tabel:

|     | B=0 | B=1 |
|-----|-----|-----|
| A=0 |  0  |  1  |
| A=1 |  0  |  1  |

Hasil: `F=B`.

#### 5.2 K-map 3 Variabel

Kolom diurutkan dengan kode Gray: 00,01,11,10.

|     | 00 | 01 | 11 | 10 |
|-----|----|----|----|----|
| A=0 |    |    |    |    |
| A=1 |    |    |    |    |

Contoh `F=Σm(1,2,3,7)` → isi tabel:

|     | 00 | 01 | 11 | 10 |
|-----|----|----|----|----|
| A=0 |  0 |  1 |  1 |  1 |
| A=1 |  0 |  0 |  1 |  0 |

Salah satu hasil minimal: `F=C(A'+B)`.

#### 5.3 K-map 4 Variabel

Baris = AB (Gray: 00,01,11,10), kolom = CD (Gray: 00,01,11,10).

| AB\CD | 00 | 01 | 11 | 10 |
|-------|----|----|----|----|
| 00    |    |    |    |    |
| 01    |    |    |    |    |
| 11    |    |    |    |    |
| 10    |    |    |    |    |

Contoh `F=Σm(0,1,2,3,8,9,10,11)`:

| AB\CD | 00 | 01 | 11 | 10 |
|-------|----|----|----|----|
| 00    |  1 |  1 |  1 |  1 |
| 01    |  1 |  1 |  1 |  1 |
| 11    |  0 |  0 |  0 |  0 |
| 10    |  0 |  0 |  0 |  0 |

Hasil: `F=A'`.

---

### 6. Studi Kasus

Pengendali lampu otomatis:  
`F = P + (¬L · T)` dengan variabel Presence (P), Light (L), Timer (T).

K-map 3 variabel:

|     | 00 | 01 | 11 | 10 |
|-----|----|----|----|----|
| A=0 |  0 |  0 |  1 |  0 |
| A=1 |  1 |  1 |  1 |  1 |

Hasil: `F = P + ¬L·T`.

---

### 7. Latihan

1. Buat K-map 3 variabel untuk `F=Σm(0,2,3,6,7)` dan sederhanakan.  
2. Buat K-map 4 variabel untuk `F=Σm(1,3,5,7,9,11,13,15)` dan sederhanakan.  
3. Gunakan don't-care `d(0,1,8,9)` untuk fungsi `F=Σm(2,3,10,11)` dan minimalkan.  

---

### 8. Sumber Belajar

- [Boolean Algebra – GeeksforGeeks](https://www.geeksforgeeks.org/boolean-algebra/)  
- [K-map Simplification – TutorialsPoint](https://www.tutorialspoint.com/digital_electronics/digital_electronics_k_map.htm)  
- [Logic Gates – W3Schools](https://www.w3schools.in/digital-electronics/logic-gates)  

---
