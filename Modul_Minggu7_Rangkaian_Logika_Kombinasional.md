
# Modul Minggu 7
## Rangkaian Logika Kombinasional

---

### 1. Pendahuluan

Rangkaian logika kombinasional adalah rangkaian digital yang output-nya hanya bergantung pada kombinasi input saat itu. Tidak ada elemen penyimpanan atau memori. 
Digunakan dalam CPU, ALU, multiplexer, decoder, adder, comparator, dan sistem kontrol digital.

---

### 2. Konsep Dasar

- Output ditentukan hanya oleh input saat itu.  
- Tidak ada feedback atau memory.  
- Hubungan input-output dapat ditentukan dengan tabel kebenaran.

---

### 3. Jenis Rangkaian Kombinasional

#### a. Encoder

| Input (D0–D7) | Output (Y2 Y1 Y0) |
|---------------|-------------------|
| 00000001      | 000               |
| 00000010      | 001               |
| 00000100      | 010               |
| 00001000      | 011               |
| 00010000      | 100               |
| 00100000      | 101               |
| 01000000      | 110               |
| 10000000      | 111               |

#### b. Decoder

| Input (A B C) | Output (D0–D7) |
|---------------|----------------|
| 000           | 00000001       |
| 001           | 00000010       |
| 010           | 00000100       |
| 011           | 00001000       |
| 100           | 00010000       |
| 101           | 00100000       |
| 110           | 01000000       |
| 111           | 10000000       |

#### c. Multiplexer (MUX)

| S1 | S0 | Output Y |
|----|----|----------|
| 0  | 0  | I0       |
| 0  | 1  | I1       |
| 1  | 0  | I2       |
| 1  | 1  | I3       |

Ekspresi Boolean:  
`Y = S1'S0'I0 + S1'S0I1 + S1S0'I2 + S1S0I3`

#### d. Demultiplexer (DEMUX)

| S1 | S0 | Output |
|----|----|---------|
| 0  | 0  | I ke O0 |
| 0  | 1  | I ke O1 |
| 1  | 0  | I ke O2 |
| 1  | 1  | I ke O3 |

#### e. Comparator (1-bit)

| A | B | A>B | A=B | A<B |
|---|---|-----|-----|-----|
| 0 | 0 | 0   | 1   | 0   |
| 0 | 1 | 0   | 0   | 1   |
| 1 | 0 | 1   | 0   | 0   |
| 1 | 1 | 0   | 1   | 0   |

#### f. Adder

Half Adder:  
| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 | 0   | 0     |
| 0 | 1 | 1   | 0     |
| 1 | 0 | 1   | 0     |
| 1 | 1 | 0   | 1     |

Full Adder:  
Sum = A⊕B⊕Cin, Carry = AB + BCin + ACin

---

### 4. Analisis & Desain

1. Tentukan jumlah input/output.  
2. Buat tabel kebenaran.  
3. Derivasi ekspresi Boolean.  
4. Sederhanakan dengan hukum Boolean/K-map.  
5. Implementasikan dengan gerbang logika.

---

### 5. Studi Kasus

#### a. Sistem Voting 3 Orang

| A | B | C | Output |
|---|---|---|--------|
| 0 | 0 | 0 | 0      |
| 0 | 0 | 1 | 0      |
| 0 | 1 | 0 | 0      |
| 0 | 1 | 1 | 1      |
| 1 | 0 | 0 | 0      |
| 1 | 0 | 1 | 1      |
| 1 | 1 | 0 | 1      |
| 1 | 1 | 1 | 1      |

Ekspresi: `F = AB + AC + BC`

#### b. Kontrol Lampu Lalu Lintas (MUX)

Menggunakan 4-to-1 MUX untuk memilih lampu arah mana yang menyala.

---

### 6. Ringkasan & Refleksi

- Rangkaian kombinasional tidak memiliki memori.  
- Jenis: encoder, decoder, multiplexer, demultiplexer, comparator, adder.  
- Banyak digunakan di CPU, ALU, dan sistem digital.

**Refleksi:**  
- Mengapa MUX disebut “data selector”?  
- Apa perbedaan peran decoder dalam memori dan tampilan 7-segmen?  
- Mengapa adder dianggap blok fundamental CPU?

---

### 7. Sumber Belajar Online

- [Combinational Circuits – GeeksforGeeks](https://www.geeksforgeeks.org/combinational-circuits-in-digital-electronics/)  
- [Multiplexer & Demultiplexer – TutorialsPoint](https://www.tutorialspoint.com/digital_electronics/digital_electronics_multiplexers_demultiplexers.htm)  
- [Encoders & Decoders – W3Schools](https://www.w3schools.in/digital-electronics/encoders-and-decoders)  

---

### 8. Latihan

1. Buat tabel kebenaran dan ekspresi Boolean untuk 2-to-4 decoder.  
2. Desain comparator 2-bit.  
3. Implementasikan fungsi voting 3 orang menggunakan K-map.  
4. Bangun Full Adder dari 2 Half Adder + OR gate.  
5. Implementasikan 4-to-1 MUX menggunakan hanya gerbang NAND.  
