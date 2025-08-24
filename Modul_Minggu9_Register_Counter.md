
# Modul Minggu 9
## Register & Counter

---

## 1. Pendahuluan

Register dan counter adalah aplikasi utama dari flip-flop (dibahas di Minggu 8).  
- **Register**: kumpulan flip-flop untuk menyimpan data.  
- **Counter**: kumpulan flip-flop untuk menghitung urutan biner.  

Digunakan pada CPU, memori, timer, komunikasi digital.

---

## 2. Register

### 2.1 Register Paralel

Register n-bit = n flip-flop D.  
Input/Output paralel.  

**Diagram Register 4-bit PIPO:**

```
D3 ───►[D FF]──► Q3
D2 ───►[D FF]──► Q2
D1 ───►[D FF]──► Q1
D0 ───►[D FF]──► Q0
         │
        CLK
```

### 2.2 Shift Register

- **SISO**: Serial In Serial Out.  
- **SIPO**: Serial In Parallel Out.  
- **PISO**: Parallel In Serial Out.  
- **PIPO**: Parallel In Parallel Out.  

**Diagram Shift Register SIPO 4-bit:**

```
Serial In → [D FF] → [D FF] → [D FF] → [D FF] → Q3 Q2 Q1 Q0
```

### 2.3 Ring Register

- Ring Register: output terakhir kembali ke input awal.  
- Urutan state 4-bit: 1000 → 0100 → 0010 → 0001 → 1000.

### 2.4 Johnson Counter (Twisted Ring)

- Output terakhir di-invert lalu kembali ke input awal.  
- Urutan 4-bit: 0000 → 1000 → 1100 → 1110 → 1111 → 0111 → 0011 → 0001 → 0000.

### 2.5 Aplikasi Register

- Buffer data.  
- Penyimpanan hasil sementara CPU.  
- Shift register dalam komunikasi serial.  
- Ring counter untuk lampu lalu lintas.  

---

## 3. Counter

### 3.1 Ripple Counter (Asynchronous)

Setiap flip-flop dipicu output flip-flop sebelumnya.  
Ada delay propagasi.

**Tabel 3-bit Ripple Up Counter:**

| Clock | Q2 | Q1 | Q0 |
|-------|----|----|----|
| 0     | 0  | 0  | 0  |
| 1     | 0  | 0  | 1  |
| 2     | 0  | 1  | 0  |
| 3     | 0  | 1  | 1  |
| 4     | 1  | 0  | 0  |
| 5     | 1  | 0  | 1  |
| 6     | 1  | 1  | 0  |
| 7     | 1  | 1  | 1  |

### 3.2 Synchronous Counter

Semua flip-flop dipicu clock yang sama.  
Lebih cepat & stabil.

### 3.3 Up, Down, Up/Down Counter

- Up: 0 → N.  
- Down: N → 0.  
- Up/Down: bisa keduanya.

### 3.4 Ring & Johnson Counter

Ring dan Johnson termasuk variasi shift register.

---

## 4. Analisis & Desain

### 4.1 State Table & State Diagram

**Counter Mod-4:**

| State Sekarang | State Berikut |
|----------------|---------------|
| 00             | 01            |
| 01             | 10            |
| 10             | 11            |
| 11             | 00            |

**State Diagram:**

```
 [00] → [01] → [10] → [11] → kembali [00]
```

### 4.2 Counter Mod-10 (Decade)

Menghitung 0–9, reset saat 10.  
Digunakan pada jam digital.

---

## 5. Studi Kasus

### 5.1 Register 4-bit Shift Left

Input 1011 digeser tiap clock.

### 5.2 Counter 4-bit Up

Menghitung 0–15.

### 5.3 Ring Counter 4-bit

Urutan: 1000 → 0100 → 0010 → 0001.

### 5.4 Johnson Counter 4-bit

Urutan: 0000 → 1000 → 1100 → 1110 → 1111 → 0111 → 0011 → 0001.

---

## 6. Ringkasan & Refleksi

- Register = penyimpanan data.  
- Counter = pencacah state.  
- Register: PIPO, SISO, SIPO, PISO, Ring, Johnson.  
- Counter: Ripple, Synchronous, Up, Down, Mod-N.  

**Refleksi:**  
- Mengapa synchronous counter lebih cepat dari ripple counter?  
- Bagaimana shift register dipakai dalam komunikasi serial?  
- Apa beda ring counter vs Johnson counter?  

---

## 7. Sumber Belajar Online

- [Registers in Digital Electronics – GeeksforGeeks](https://www.geeksforgeeks.org/registers-in-digital-electronics/)  
- [Counters in Digital Electronics – TutorialsPoint](https://www.tutorialspoint.com/digital_electronics/digital_electronics_counters.htm)  
- [Shift Registers – W3Schools](https://www.w3schools.in/digital-electronics/shift-register)  

---

## 8. Latihan

1. Rancang register PIPO 8-bit.  
2. Buat tabel keadaan counter 3-bit asynchronous.  
3. Rancang synchronous counter Mod-6.  
4. Desain ring counter 4-bit.  
5. Simulasikan shift register SISO dengan input 1011.  
