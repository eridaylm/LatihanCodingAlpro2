# Latihan Coding Pekan 1: Review Struktur Kontrol

---

## 📚 Nomor 1

### 📝 Soal
Buatlah function dalam bahasa Go bernama `dendaPerpustakaan` untuk menghitung denda bagi peminjam buku perpustakaan karena terlambat mengembalikan buku pinjaman. Jika terlambat hingga 10 hari, maka harus membayar sebesar Rp 2.500 per harinya. Jika terlambat lebih dari 10 hari, maka harus membayar denda Rp 5.000 per harinya. Fungsi memiliki satu parameter berupa jumlah hari keterlambatan dalam bilangan bulat dan mengembalikan nilai berupa jumlah uang denda dengan tipe bilangan bulat.

### 📥 Input & Output
Masukan terdiri bilangan bulat yang menyatakan jumlah hari keterlambatan.  
Keluaran berupa jumlah uang denda.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 1 | 2500 |
| 10 | 25000 |

### 💻 Implementasi Code (Golang)

```go
//buat fungsi saja
func dendaPerpustakaan(hariTerlambat int) int {
    if hariTerlambat <= 0 {
        return 0
    }
    if hariTerlambat <= 10 {
        return hariTerlambat * 2500
    }
    return hariTerlambat * 5000
}
```
---
## 🔤 Nomor 2

### 📝 Soal
Buatlah fungsi dalam bahasa Go untuk mengembalikan nilai berupa karakter terakhir dari suatu string. Fungsi dipanggil dalam program dengan masukan dan keluaran sebagai berikut:

### 📥 Input & Output
Masukan berupa sebuah string.  
Keluaran berupa karakter terakhir dari string.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| Telkom | m |
| University | y |
| sinergi | i |

### 💻 Implementasi Code (Golang)

```go
// Buatlah fungsi saja

func lastChar(teks string) byte {
    // Mengembalikan karakter yang berada di indeks terakhir dari string
	return teks[len(teks)-1]
}
```
---
## 🟦 Nomor 3

### 📝 Soal
Buatlah fungsi dalam bahasa Go bernama kelilingPersegi untuk menghitung keliling persegi. Fungsi memiliki sebuah parameter berupa sisi persegi dengan tipe bilangan bulat dan mengembalikan nilai berupa bilangan bulat.

Fungsi akan dipanggil dalam sebuah program dengan masukan dan keluaran sebagai berikut:

### 📥 Input & Output
Masukan berupa sebuah bilangan bulat yang menyatakan sisi persegi.  
Keluaran adalah keliling persegi dengan sisi sesuai masukan.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 5 | 20 |
| 10 | 40 |

### 💻 Implementasi Code (Golang)

```go
// Buatlah fungsi saja

func kelilingPersegi(sisi int) int {
    /* fungsi mengembalikan keliling persegi */
	var keliling int
	keliling = 4*sisi
	return keliling
}
```
---
## ➗ Nomor 4

### 📝 Soal
Buatlah fungsi dalam bahasa GO bernama penjumlahanPecahan untuk menjumlahkan bilangan pecahan. Jika penyebutnya sama, maka tampilkan hasil penjumlahan bagian pembilang. Jika penyebutnya tidak sama, maka cetak bilangan 0.

pembilang1penyebut1+pembilang2penyebut2

Fungsi akan memiliki 4 parameter berupa bilangan bulat. Bilangan pertama menyatakan pembilang pertama, bilangan kedua menyatakan penyebut pertama, bilangan ketiga menyatakan pembilang kedua, dan bilangan keempat menyatakan penyebut kedua. Fungsi mengembalikan nilai berupa hasil penjumlahan atau bilangan 0.

Fungsi akan dipanggil dalam program dengan masukan dan keluaran sebagai berikut:

### 📥 Input & Output
Masukan berupa empat buah bilangan bulat dengan urutan sebagaimana deskripsi di atas.  
Keluaran berupa hasil penjumlahan pada bagian pembilang atau bilangan 0 sesuai kondisinya.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 1 2 3 2 | 4 |
| 1 3 2 4 | 0 |
| 1 1 1 1 | 2 |

### 💻 Implementasi Code (Golang)

```go
// Buatlah fungsi saja

func penjumlahanPecahan(pembilang1, penyebut1, pembilang2, penyebut2 int) int {
    var hasil int
    
    if penyebut1 == penyebut2 {
        hasil = pembilang1 + pembilang2
    } else {
        hasil = 0
    }
    
    return hasil
}
```

---

## 🕵️‍♂️ Nomor 5

### 📝 Soal
Buatlah fungsi pertemuan untuk menghitung jumlah pertemuan rahasia antara dua orang mata-mata dalam setahun. Mereka akan bertemu pada setiap hari kelipatan x atau kelipatan y, dengan x dan y adalah bilangan bulat positif dan nilai x kurang dari y. Jumlah hari dalam setahun diasumsikan 365, sehingga hari bernilai dari 1 hingga 365.

41

Fungsi dipanggil dalam program dengan masukan dan keluaran sebagai berikut:

### 📥 Input & Output
Masukan berupa bilangan bulat positif x dan y, dengan x, y > 0 dan x < y.  
Keluaran berupa jumlah pertemuan dalam setahun.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 2 3 | 243 |
| 4 5 | 146 |

### 💻 Implementasi Code (Golang)

```go
// implementasikan fungsinya saja

func pertemuan(x, y int) int {
/* mengembalikan jumlah pertemuan sesuai ketentuan soal */
    jumlah := 0
    for hari := 1; hari <= 365; hari++ {
        if hari%x == 0 || hari%y == 0 {
            jumlah++
        }
    }
    return jumlah
}
```
---
## 🕵️‍♀️ Nomor 6

### 📝 Soal
Buatlah fungsi kirimPesanRahasia untuk membaca pesan rahasia yang terdapat pada sebuah string. Pesan rahasianya dapat dilihat pada karakter ke-1, ke-5, ke-9, dan ke-13 dari string.

Masukan berupa sebuah string pesan.  
Keluaran adalah string yang menyatakan pesan rahasia yang dikirim, atau string kosong jika kondisinya tidak memenuhi.

Catatan: 

String memiliki indeks berawal pada nilai 0. Sehingga, karakter ke-1 berada di string indeks ke-0, karakter ke-2 berada di indeks ke-1, dan seterusnya.  
Untuk mengetahui panjang string, gunakan fungsi primitif len. Contoh: len("hxaalhoksiengh") akan mengembalikan 14.  
Untuk mengubah tipe data byte menjadi string, dapat menggunakan typecasting. Contoh: jika variabel x bertipe data string dengan nilai "telkom", maka string(x[0]) dapat digunakan untuk mengonversi x[0], yang bertipe data byte, menjadi string.

### 📥 Input & Output
Masukan berupa sebuah string pesan.  
Keluaran adalah string yang menyatakan pesan rahasia yang dikirim, atau string kosong jika kondisinya tidak memenuhi.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| diatidakakanmenerimanya | diam |
| membaraituapisangatpanas | mati |
| bimbangawaslah | bawa |
| telkom |  |

### 💻 Implementasi Code (Golang)

```go
// implementasikan fungsinya saja

func kirimPesanRahasia(pesan string) string {
// mengembalikan pesan rahasia pada karakter ke-1, ke-5, ke-9, dan ke-13 dari string masukan.
    if len(pesan) >= 13 {
        return string(pesan[0]) + string(pesan[4]) + string(pesan[8]) + string(pesan[12])
    }
    return ""
}
```
---

## 💰 Nomor 7

### 📝 Soal
Seorang pelajar SMK Informatika memiliki kebiasaan menabung yang unik. Ia menabung setiap hari yang merupakan kelipatan dari 2 atau 3. Jumlah uang yang ditabung setiap hari tersebut adalah hasil penambahan dari jumlah tabungan sebelumnya dengan sejumlah uang tetap.

Buatlah sebuah fungsi bernama totalTabungan yang menghitung jumlah total tabungan yang terkumpul selama sejumlah hari tertentu.

Masukan terdiri dari bilangan bulat x yang menyatakan uang yang ditabung pertama kali, y yang menyatakan Jumlah uang tetap, dan z banyaknya hari tabungan.  
Keluaran berupa total tabungannya selama z hari.

Petunjuk:  
Jika pelajar menabung pertama kali sebesar Rp 1.000 dan uang tetap yang ditabungkan setiap kali menabung adalah Rp 500, maka dalam 5 hari, tabungan yang terkumpul adalah sebesar Rp 4.500. Hal ini dihitung berdasarkan aturan menabung hanya pada hari-hari yang merupakan kelipatan dari 2 atau 3. Berikut adalah tabel rincian prosesnya:

Hari	Uang Ditabung	Keterangan  
1	-	Tidak menabung (1 bukan kelipatan 2 atau 3).  
2	1000	2 merupakan kelipatan 2. Menabung pertama kali.  
3	1500	3 merupakan kelipatan 3. Menabung sebesar 1000 + 500 = 1500.  
4	2000	4 merupakan kelipatan 2. Menabung sebesar 1500 + 500 = 2000.  
5	-	Tidak menabung (5 bukan kelipatan 2 atau 3).  
Total	0 + 1000 + 1500 + 2000 + 0 = 4500  

### 📥 Input & Output
Masukan terdiri dari bilangan bulat x yang menyatakan uang yang ditabung pertama kali, y yang menyatakan Jumlah uang tetap, dan z banyaknya hari tabungan.  
Keluaran berupa total tabungannya selama z hari.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 1000 100 3 | 2100 |
| 1000 500 5 | 4500 |

### 💻 Implementasi Code (Golang)

```go
func totalTabungan(x, y, z int)int{
    tabunganSekarang := x
    total := 0
    
    for hari := 1; hari <= z; hari ++ {
        if hari%2 == 0 || hari%3 == 0 {
            total += tabunganSekarang
            tabunganSekarang += y
        }
    }
    
    return total
}
```

---
## 🔁 Nomor 8

### 📝 Soal
Create a modulusLoop function to calculate the modulus (remain) after dividing an integer n by m without using the modulus operator.

The function is called in the program with the following input and output:

Inputs are two integers n and m, with n >= 0 and m > 0.

Output is the modulus result of the two input numbers.

### 📥 Input & Output
Inputs are two integers n and m, with n >= 0 and m > 0.  
Output is the modulus result of the two input numbers.

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 5 2 | 1 |
| 4 2 | 0 |

### 💻 Implementasi Code (Golang)

```go
// Create the function only

func modulusLoop(n, m int) int {
    var result, reminder int
    result = n
    reminder = m
    
    for result >= reminder {
        result = result - reminder
        reminder = m
    }
    
    return result
}
```