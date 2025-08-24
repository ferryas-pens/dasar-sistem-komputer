
# Modul Minggu 4
## Representasi Data & Kode

---

### 1. Pendahuluan

Komputer hanyalah mesin elektronik yang bekerja dengan sinyal digital berupa **0** dan **1**. Namun dalam kehidupan sehari-hari, kita berinteraksi dengan data dalam berbagai bentuk: angka, huruf, gambar, suara, hingga video. Agar semua jenis data ini bisa diproses oleh komputer, diperlukan **sistem representasi data**.  

Representasi data adalah **cara mengubah informasi dari dunia nyata menjadi bentuk biner yang dapat dimengerti oleh komputer**.  

Pertemuan ini akan membahas:  
1. Representasi angka (BCD, Gray Code, dll).  
2. Representasi karakter (ASCII, Unicode, EBCDIC).  
3. Representasi simbol & data non-angka (gambar, suara, video).  
4. Error detection & correction.  
5. Studi kasus nyata terkait encoding data.  

---

### 2. Representasi Angka

#### a. Binary Coded Decimal (BCD)
- Setiap digit desimal (0–9) direpresentasikan dengan 4-bit biner.  
- Contoh: 259₁₀ → 0010 0101 1001 (BCD).  
- Kelebihan: mudah ditampilkan. Kekurangan: boros memori.  

#### b. Excess-3 Code
- Setiap digit desimal direpresentasikan dengan BCD + 3.  
- Contoh: 5 → 1000 (karena 5+3=8).  

#### c. Gray Code
- Hanya satu bit berubah antara dua angka berturut-turut.  
- Digunakan pada sensor & komunikasi.  
- Contoh: 0=0000, 1=0001, 2=0011, 3=0010.  

---

### 3. Representasi Karakter

#### a. ASCII (American Standard Code for Information Interchange)
- Standar 7-bit (128 karakter).  
- Extended ASCII: 8-bit (256 karakter).  
- Contoh: A=65, a=97, 0=48.  

#### b. Unicode
- Mendukung semua bahasa di dunia.  
- Format: UTF-8, UTF-16, UTF-32.  
- Contoh: "A"=U+0041, "你"=U+4F60, "😊"=U+1F60A.  

#### c. EBCDIC
- Digunakan IBM mainframe.  
- Kini jarang dipakai, tetapi penting secara historis.  

---

### 4. Representasi Simbol & Data Non-Angka

#### a. Boolean
- True=1, False=0.  

#### b. Gambar
- Bitmap: array pixel.  
- RGB: tiap pixel berisi nilai merah, hijau, biru.  

#### c. Suara
- Representasi melalui **sampling**.  
- PCM (Pulse Code Modulation).  

#### d. Video
- Rangkaian frame + suara.  
- Dikompresi dengan codec (H.264, VP9, AV1).  

---

### 5. Error Detection & Correction

#### a. Parity Bit
- Bit tambahan untuk cek jumlah bit 1 (even/odd parity).  
- Contoh: 1010001 → parity genap = 10100011.  

#### b. Checksum
- Jumlah biner dari data.  
- Digunakan pada jaringan & penyimpanan.  

#### c. Hamming Code
- Dapat mendeteksi dan memperbaiki 1-bit error.  
- Prinsip: menambahkan bit paritas di posisi tertentu.  

---

### 6. Studi Kasus

1. **Teks Rusak (Garbled Text)**  
   - File Unicode dibuka dengan ASCII → karakter non-Inggris berubah jadi simbol aneh.  
   - Contoh: "你好吗" → `æå¥½`.  

2. **Angka 123**  
   - BCD → 0001 0010 0011.  
   - ASCII → "1"(00110001), "2"(00110010), "3"(00110011).  
   - Biner murni → 1111011₂.  

---

### 7. Ringkasan & Refleksi

- Komputer merepresentasikan angka, huruf, gambar, suara, video dalam biner.  
- BCD, Excess-3, Gray digunakan untuk angka.  
- ASCII dan Unicode untuk teks.  
- Multimedia butuh format khusus.  
- Parity, checksum, Hamming → menjaga data tetap akurat.  

**Refleksi Mahasiswa:**  
- Mengapa Unicode lebih baik dibanding ASCII?  
- Bagaimana komputer membedakan teks, gambar, dan suara?  
- Apa yang terjadi jika parity bit tidak sesuai?  

---

### 8. Sumber Belajar Online

- [Character Encoding – GeeksforGeeks](https://www.geeksforgeeks.org/character-encoding/)  
- [ASCII Table – TutorialsPoint](https://www.tutorialspoint.com/ascii-table-in-c)  
- [Unicode Standard – Unicode.org](https://home.unicode.org/)  

---

### 9. Latihan

1. Representasikan angka 359 dalam BCD.  
2. Konversi desimal 9 menjadi Gray Code.  
3. Cari nilai ASCII untuk huruf ‘Z’ dan ‘z’.  
4. Apa Unicode untuk karakter ‘Ω’?  
5. Tambahkan parity bit (genap) pada data 1011010.  
6. Mengapa teks bisa rusak jika encoding salah?  
