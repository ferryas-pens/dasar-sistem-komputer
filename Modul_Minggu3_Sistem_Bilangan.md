
# Modul Minggu 3
## Sistem Bilangan dalam Komputer

---

### 1. Pendahuluan

Komputer adalah mesin digital. Artinya, komputer hanya mengenal dua kondisi: **0** dan **1**. Seluruh data, instruksi, gambar, video, bahkan musik yang kita simpan dan olah di komputer pada akhirnya direpresentasikan dalam bentuk bilangan biner.

Untuk memahami bagaimana komputer bekerja, mahasiswa perlu menguasai **sistem bilangan**. Ini adalah salah satu fondasi penting dalam ilmu komputer, karena semua operasi logika, aritmatika, dan representasi data bergantung pada sistem bilangan.

Pertemuan ini akan membahas:
1. Jenis-jenis sistem bilangan (desimal, biner, oktal, heksadesimal).  
2. Teknik konversi antar sistem bilangan.  
3. Representasi bilangan dalam komputer (signed, unsigned, complement, floating point).  
4. Operasi aritmatika biner (penjumlahan, pengurangan, overflow).  
5. Studi kasus penerapan sistem bilangan dalam pemrograman dan arsitektur komputer.  

---

### 2. Jenis-Jenis Sistem Bilangan

Sistem bilangan ditentukan oleh **basis (radix)**, yaitu jumlah simbol unik yang digunakan.  

#### a. Desimal (Basis 10)
- Basis = 10, digit: 0–9.  
- Contoh: 253₁₀ = (2×10²) + (5×10¹) + (3×10⁰).  

#### b. Biner (Basis 2)
- Basis = 2, digit: 0 dan 1.  
- Contoh: 1011₂ = (1×2³) + (0×2²) + (1×2¹) + (1×2⁰) = 11₁₀.  

#### c. Oktal (Basis 8)
- Basis = 8, digit: 0–7.  
- Contoh: 125₈ = (1×8²) + (2×8¹) + (5×8⁰) = 85₁₀.  

#### d. Heksadesimal (Basis 16)
- Basis = 16, digit: 0–9 dan A–F.  
- Contoh: 2F₁₆ = (2×16¹) + (15×16⁰) = 47₁₀.  

---

### 3. Konversi Antar Sistem Bilangan

#### a. Desimal → Biner
Metode: pembagian berulang dengan 2.  
Contoh: 25₁₀ = 11001₂.  

#### b. Biner → Desimal
Metode: ekspansi posisi digit.  
Contoh: 10110₂ = 22₁₀.  

#### c. Desimal → Oktal
Metode: pembagian berulang dengan 8.  
Contoh: 125₁₀ = 175₈.  

#### d. Desimal → Heksadesimal
Metode: pembagian berulang dengan 16.  
Contoh: 255₁₀ = FF₁₆.  

#### e. Biner ↔ Oktal
Kelompokkan biner per 3 digit.  
Contoh: 101101₂ = 55₈.  

#### f. Biner ↔ Heksadesimal
Kelompokkan biner per 4 digit.  
Contoh: 11111111₂ = FF₁₆.  

---

### 4. Representasi Bilangan dalam Komputer

#### a. Bilangan Signed vs Unsigned
- **Unsigned**: 0 s.d. 2ⁿ–1.  
- **Signed**: bisa positif & negatif.  

#### b. Complement
- One’s complement: inversi semua bit.  
- Two’s complement: inversi semua bit + tambah 1.  
  - Contoh: 5₁₀ = 00000101₂ → –5 = 11111011₂.  

#### c. Floating Point (IEEE 754)
- Format: `(-1)^sign × mantissa × 2^exponent`.  
- Contoh: 0.75₁₀ = 1.1₂ × 2⁻¹.  

---

### 5. Operasi Aritmatika Biner

#### a. Penjumlahan
```
  1011 (11)
+ 1101 (13)
------
11000 (24)
```

#### b. Pengurangan (two’s complement)
```
  1010 (10)
- 0011 (3)
= 0111 (7)
```

#### c. Overflow
- Terjadi jika hasil melebihi kapasitas bit.  
- Contoh: 8-bit signed → rentang –128 s.d. +127.  

---

### 6. Studi Kasus: Sistem Bilangan di Dunia Nyata

1. **Alamat Memori**: ditulis dalam heksadesimal (mis. 0x7FFF).  
2. **Pemrograman**: C/C++ menggunakan 0b (biner), 0x (heksadesimal).  
3. **Jaringan Komputer**: IP address → representasi biner ditulis desimal.  

---

### 7. Ringkasan & Refleksi

- Empat sistem utama: desimal, biner, oktal, heksadesimal.  
- Konversi antar basis wajib dikuasai.  
- Bilangan negatif direpresentasikan dengan **two’s complement**.  
- Floating point untuk bilangan real.  
- Hati-hati dengan **overflow**.  

**Refleksi**:  
- Mengapa komputer lebih memilih two’s complement?  
- Mengapa heksadesimal lebih praktis dibanding biner?  

---

### 8. Sumber Belajar Online

- [Programiz – Number System](https://www.programiz.com/c-programming/number-system)  
- [W3Schools – Binary, Octal, Hex](https://www.w3schools.com/cs/cs_numbers_bin_oct_hex.php)  
- [GeeksforGeeks – Number System](https://www.geeksforgeeks.org/number-system-in-computer-organization/)  

---

### 9. Latihan

1. Konversi 45₁₀ ke biner, oktal, heksadesimal.  
2. Konversi 110101₂ ke desimal.  
3. Tunjukkan representasi –25₁₀ dalam two’s complement 8-bit.  
4. Hitung: 101101₂ + 11011₂.  
5. Apa yang terjadi jika menambahkan 10000000₂ (–128) dan 11111111₂ (–1) dalam 8-bit signed?  
