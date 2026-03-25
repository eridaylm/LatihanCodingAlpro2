# Latihan Coding Pekan 1.2: Review Struktur Kontrol: Percabangan & Perulangan 

---

## ⚽ Nomor 1

### 📝 Soal
Seorang manager klub di English Premier League memiliki klausul berikut dalam kontraknya: Bersedia dipecat jika kalah berturut-turut dalam 5 kali pertandingan. Buatlah program dalam bahasa Go untuk menentukan apakah seorang manager klub English Premier League itu akan dipecat atau tidak. 

### 📥 Input & Output
- **Masukan (Input):** Lima buah `string` yang dipisahkan spasi. Nilai valid: `"menang"`, `"kalah"`, atau `"draw"`.
- **Keluaran (Output):** String `"dipecat"` atau `"tidak dipecat"`.

### 🧪 Contoh
| Input | Result |
| :--- | :--- |
| `kalah kalah kalah kalah kalah` | `dipecat` |
| `kalah kalah kalah kalah menang` | `tidak dipecat` |
| `menang draw kalah draw menang` | `tidak dipecat` |

### 💻 Code
```go
package main
import "fmt"

func main() {
    count := 0
    for i := 0; i < 5; i++ {
        var result string
        fmt.Scan(&result)
        if result == "kalah" {
            count++
        } else {
            count = 0
        }
    }
    if count >= 5 {
        fmt.Println("dipecat")
    } else {
        fmt.Println("tidak dipecat")
    }
}
```

---

## 🔤 Nomor 2

### 📝 Soal
Buatlah program dalam bahasa Go untuk menentukan apakah suatu alfabet termasuk vokal atau konsonan. Masukan berupa sebuah alfabet dari 'a' hingga 'z' atau dari 'A' hingga 'Z'. Keluaran berupa string "vokal" jika alfabet termasuk vokal atau "konsonan" jika termasuk konsonan.

### 📥 Input & Output
- **Masukan:** Sebuah alfabet dari 'a'-'z' atau 'A'-'Z'.
- **Keluaran:** String `"vokal"` atau `"konsonan"`.

### 🧪 Test Cases
| Input | Result |
| :--- | :--- |
| `a` | `vokal` |
| `E` | `vokal` |
| `w` | `konsonan` |

### 💻 Implementasi Code (Golang)
```go
package main
import (
    "fmt"
    "strings"
)

func main() {
    var char string
    fmt.Scan(&char)
    
    char = strings.ToLower(char)
    
    if char == "a" || char == "e" || char == "i" || char == "o" || char == "u" {
        fmt.Println("vokal")
    } else {
        fmt.Println("konsonan")
    }
}
```

---

## 🏠 Nomor 3

### 📝 Soal
Buatlah program dalam bahasa Go untuk menentukan apakah seseorang akan berangkat dari rumahnya atau diam saja di rumahnya berdasarkan pohon keputusan dalam gambar di bawah.

Masukan terdiri dari 2 baris string, Baris 1 berupa "ya" yang menyatakan hujan turun atau "tidak" yang menyatakan tidak turun hujan. Baris 2 berupa string "ya" yang menyatakan punya payung atau "tidak" yang menyatakan tidak punya payung. Keluaran berupa string "berangkat" atau "diam di rumah" bergantung kepada nilai kondisinya.

### 📥 Input & Output
- **Masukan:** - Baris 1: `"ya"` (hujan) atau `"tidak"` (tidak hujan)
  - Baris 2: `"ya"` (punya payung) atau `"tidak"` (tidak punya payung)
- **Keluaran:** String `"berangkat"` atau `"diam di rumah"`.

### 🧪 Test Cases
| Baris 1 | Baris 2 | Result |
| :--- | :--- | :--- |
| `tidak` | `ya` | `berangkat` |
| `tidak` | `tidak` | `berangkat` |
| `ya` | `tidak` | `diam di rumah` |

### 💻 Implementasi Code (Golang)
```go
package main

import "fmt"

func main() {
    var hujan, punyaPayung string
    fmt.Scan(&hujan)
    fmt.Scan(&punyaPayung)
    
    if hujan == "ya" && punyaPayung == "tidak" {
        fmt.Println("diam di rumah")
    } else {
        fmt.Println("berangkat")
    }
}
```
---

## 🚀 Nomor 4

### 📝 Soal
Di planet X yang berjarak 10 tahun cahaya dari planet Bumi syarat untuk mendapatkan SIM adalah minimal berumur 10 tahun, fasih berbahasa golang, dan nilai tes kecakapan mengemudinya tepat 100. Masukan berupa umur, fasih berbahasa golang, dan nilai tes. Umur dan nilai tes dalam integer, fasih golang dalam boolean. Keluaran berupa boolean true jika bisa mendapatkan SIM, atau false jika belum bisa.

### 📥 Input & Output
- **Masukan:** `umur` (int), `fasih_golang` (bool), `nilai_tes` (int).
- **Keluaran:** Boolean (`true` atau `false`).

### 🧪 Test Cases
| Input | Result |
| :--- | :--- |
| `10 true 100` | `true` |
| `9 true 100` | `false` |

### 💻 Implementasi Code (Golang)
```go
package main
import "fmt"

func main() {
    var umur, nilai int
    var fasih bool
    fmt.Scan(&umur, &fasih, &nilai)
    fmt.Println(umur >= 10 && fasih && nilai == 100)
}
```
## 🛒 Nomor 5

### 📝 Soal
Buatlah program dalam bahasa Go untuk menentukan apakah seseorang akan pergi ke minimarket atau tidak.

Masukan terdiri dari 2 baris string:
- Baris 1 `"ya"` berarti kehabisan sampo, `"tidak"` berarti tidak kehabisan sampo  
- Baris 2 `"ya"` berarti hujan turun, `"tidak"` berarti tidak hujan  

Seseorang akan pergi ke minimarket jika **kehabisan sampo DAN tidak hujan**.

---

### 📥 Input & Output
- **Masukan:**
  - Baris 1: `"ya"` atau `"tidak"` (kehabisan sampo)
  - Baris 2: `"ya"` atau `"tidak"` (hujan)
- **Keluaran:**
  - `"pergi ke minimarket"` atau `"tidak pergi ke minimarket"`

---

### 🧪 Test Cases

| Baris 1 | Baris 2 | Result |
| :--- | :--- | :--- |
| ya | ya | tidak pergi ke minimarket |
| ya | tidak | pergi ke minimarket |
| tidak | tidak | tidak pergi ke minimarket |
| tidak | ya | tidak pergi ke minimarket |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var kehabisanSampo, hujan string
    fmt.Scan(&kehabisanSampo)
    fmt.Scan(&hujan)
    
    if kehabisanSampo == "ya" && hujan == "tidak" {
        fmt.Println("pergi ke minimarket")
    } else {
        fmt.Println("tidak pergi ke minimarket")
    }
}
```

## ➕ Nomor 6

### 📝 Soal
Adik sedang belajar menjumlahkan 3 bilangan bulat. Buatlah program dalam bahasa Go untuk menentukan apakah hasil penjumlahan adik benar atau salah.

Masukan terdiri dari 4 baris:
- Tiga baris pertama adalah bilangan yang akan dijumlahkan
- Baris ke-4 adalah hasil penjumlahan dari adik

Keluaran berupa:
- `"benar"` jika hasil penjumlahan sesuai
- `"salah"` jika tidak sesuai

---

### 📥 Input & Output
- **Masukan:**
  - Baris 1: bilangan pertama (int)
  - Baris 2: bilangan kedua (int)
  - Baris 3: bilangan ketiga (int)
  - Baris 4: hasil dari adik (int)
- **Keluaran:**
  - `"benar"` atau `"salah"`

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 11 22 33 66 | benar |
| 12 34 56 101 | salah |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var a, b, c, hasil int
    fmt.Scan(&a)
    fmt.Scan(&b)
    fmt.Scan(&c)
    fmt.Scan(&hasil)
    
    if a+b+c == hasil {
        fmt.Println("benar")
    } else {
        fmt.Println("salah")
    }
}
```

## ⚡ Nomor 7

### 📝 Soal
Buatlah program dalam bahasa Go untuk menghitung dan mencetak tagihan listrik pelanggan berdasarkan ketentuan berikut:

| Unit Pemakaian | Biaya per Unit |
| :--- | :--- |
| < 200 | 12 usd |
| ≥ 200 dan < 400 | 15 usd |
| ≥ 400 dan < 600 | 18 usd |
| ≥ 600 | 20 usd |

Ketentuan tambahan:
- Jika tagihan **melebihi 400 usd**, maka dikenai **biaya tambahan 20%**
- Biaya minimum tagihan adalah **100 usd**

Masukan berupa jumlah unit listrik yang dikonsumsi.

Keluaran berupa jumlah total uang yang harus dibayar pelanggan.

---

### 📥 Input & Output
- **Masukan:**
  - Jumlah unit listrik (int)
- **Keluaran:**
  - Total tagihan (int)

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 800 | 19200 |
| 100 | 1440 |
| 20 | 240 |

---

### 💻 Implementasi Code (Golang)

```go
package main

import "fmt"

func main() {
    var unit int
    fmt.Scan(&unit)
    
    var biayaPerUnit int
    switch {
    case unit < 200:
        biayaPerUnit = 12
    case unit < 400:
        biayaPerUnit = 15
    case unit < 600:
        biayaPerUnit = 18
    default:
        biayaPerUnit = 20
    }
    
    tagihan := unit * biayaPerUnit
    
    if tagihan > 400 {
        tagihan = tagihan + tagihan*20/100
    }
    
    if tagihan < 100 {
        tagihan = 100
    }
    
    fmt.Println(tagihan)
}
```

## ⚔️ Nomor 8

### 📝 Soal
Buatlah program dalam bahasa Go untuk menentukan siapa yang akan menang dalam pertempuran antara pasukan Viking dengan pasukan Saxon.

Ketentuan:
- Pasukan dengan jumlah kekuatan lebih besar akan menang
- Setiap **1 prajurit Viking setara dengan 4 prajurit Saxon**

Masukan terdiri dari:
- Baris 1: jumlah prajurit Viking
- Baris 2: jumlah prajurit Saxon

Keluaran berupa:
- `"viking menang"`
- `"saxon menang"`
- `"imbang"`

---

### 📥 Input & Output
- **Masukan:**
  - Jumlah Viking (int)
  - Jumlah Saxon (int)
- **Keluaran:**
  - String hasil pertempuran

---

### 🧪 Test Cases

| Viking | Saxon | Result |
| :--- | :--- | :--- |
| 5 | 18 | viking menang |
| 10 | 41 | saxon menang |
| 1 | 4 | imbang |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var viking, saxon int
    fmt.Scan(&viking)
    fmt.Scan(&saxon)
    
    vikingStrength := viking * 4
    
    if vikingStrength > saxon {
        fmt.Println("viking menang")
    } else if vikingStrength < saxon {
        fmt.Println("saxon menang")
    } else {
        fmt.Println("imbang")
    }
}
```

## 🗳️ Nomor 9

### 📝 Soal
Buatlah program dalam bahasa Go untuk memilih ketua kelas dari 2 kandidat.

Ketentuan:
- Seseorang terpilih jika jumlah yang memilihnya **lebih besar dari kandidat lain**
- Jumlah total pemilih minimal **60% dari jumlah siswa**
- Kedua kandidat ikut memvoting

Masukan terdiri dari 3 baris:
1. Jumlah siswa di kelas (int)
2. Jumlah pemilih kandidat A (int)
3. Jumlah pemilih kandidat B (int)

Keluaran berupa:
- `"Kandidat A menang"`
- `"Kandidat B menang"`
- `"Tidak ada pemenang"`

---

### 📥 Input & Output
- **Masukan:**
  - Baris 1: total siswa (int)
  - Baris 2: jumlah pemilih A (int)
  - Baris 3: jumlah pemilih B (int)
- **Keluaran:** String hasil pemilihan

---

### 🧪 Test Cases

| Total Siswa | Kandidat A | Kandidat B | Result |
| :--- | :--- | :--- | :--- |
| 46 | 40 | 4 | Kandidat A menang |
| 46 | 10 | 30 | Kandidat B menang |
| 46 | 1 | 15 | Tidak ada pemenang |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var totalSiswa, suaraA, suaraB int
    fmt.Scan(&totalSiswa)
    fmt.Scan(&suaraA)
    fmt.Scan(&suaraB)
    
    totalSuara := suaraA + suaraB
    minimalPemilih := totalSiswa * 60 / 100
    
    if totalSuara >= minimalPemilih && suaraA > suaraB {
        fmt.Println("Kandidat A menang")
    } else if totalSuara >= minimalPemilih && suaraB > suaraA {
        fmt.Println("Kandidat B menang")
    } else {
        fmt.Println("Tidak ada pemenang")
    }
}
```

## 🌳 Nomor 10

### 📝 Soal
Buatlah program dalam bahasa Go untuk menentukan jenis verteks pada pohon graf.

Ketentuan:
- `A` → akar  
- `B`, `E` → verteks dalam  
- `C`, `D`, `F`, `G` → daun  

Masukan terdiri dari sebuah string: `"A"` hingga `"G"`.

Keluaran berupa:
- `"akar"`  
- `"verteks dalam"`  
- `"daun"`  

---

### 📥 Input & Output
- **Masukan:** String (A–G)  
- **Keluaran:** String jenis verteks

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| A | akar |
| B | verteks dalam |
| C | daun |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var vertex string
    fmt.Scan(&vertex)
    
    if vertex == "A" {
        fmt.Println("akar")
    } else if vertex == "B" || vertex == "E" {
        fmt.Println("verteks dalam")
    } else {
        fmt.Println("daun")
    }
}
```

## 🔢 Nomor 11

### 📝 Soal
Buatlah program dalam bahasa Go untuk menjumlahkan bilangan-bilangan **ganjil kelipatan 3** menggunakan struktur perulangan `while` (looping tak hingga yang dihentikan dengan kondisi).

Ketentuan:
- Masukan terdiri dari serangkaian bilangan bulat
- Pembacaan berhenti saat terbaca bilangan negatif
- Bilangan negatif **tidak dihitung**
- Keluaran: hasil penjumlahan semua bilangan ganjil kelipatan 3

---

### 📥 Input & Output
- **Masukan:** Serangkaian bilangan bulat (baris per baris)  
- **Keluaran:** Hasil penjumlahan bilangan ganjil kelipatan 3 (int)

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 5 4 3 6 9 0 4 21 5 -1 | 3 + 9 + 21 + 5 = 38 |
| 33 0 2 3 -6 3 | 33 + 3 + 3 = 39 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    sum := 0
    
    for {
        var num int
        fmt.Scan(&num)
        
        if num < 0 {
            break
        }
        
        if num%2 != 0 && num%3 == 0 {
            sum += num
        }
    }
    
    fmt.Println(sum)
}
```
## 🔤 Nomor 12

### 📝 Soal
Buatlah program dalam bahasa Go untuk memeriksa apakah terdapat huruf `'k'` atau `'q'` pada 10 huruf yang diinputkan.

Ketentuan:
- Masukan terdiri dari **10 huruf berbeda-beda**
- Keluaran berupa **boolean**:
  - `true` jika huruf `'k'` atau `'q'` ditemukan
  - `false` jika tidak ditemukan

---

### 📥 Input & Output
- **Masukan:** String sepanjang 10 karakter  
- **Keluaran:** `true` atau `false`

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| qwertyuiop | true |
| asdfghjklz | true |
| qkaaaaaaaa | true |
| pppppppppp | false |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var s string
    fmt.Scan(&s)
    
    found := false
    for i := 0; i < len(s); i++ {
        if s[i] == 'k' || s[i] == 'q' {
            found = true
            break
        }
    }
    fmt.Println(found)
}
```
## 🕵️‍♂️ Nomor 13

### 📝 Soal
Buatlah program dalam bahasa Go untuk menghitung jumlah **pertemuan rahasia** antara dua mata-mata dalam setahun.

Ketentuan:
- Mereka bertemu setiap hari kelipatan `x` **dan** kelipatan `y`
- Jumlah hari dalam setahun = 365 (hari 1–365)
- Masukan: dua bilangan bulat positif `x` dan `y`  
- Keluaran: jumlah pertemuan dalam setahun

---

### 📥 Input & Output
- **Masukan:** Dua bilangan bulat positif (x y)  
- **Keluaran:** Jumlah hari pertemuan (int)

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 2 3 | 60 |
| 4 5 | 18 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
	var x, y int
	fmt.Scan(&x, &y)

	jumlahPertemuan := 0

	for hari := 1; hari <= 365; hari++ {
		if hari%x == 0 && hari%y == 0 {
			jumlahPertemuan++
		}
	}

	fmt.Println(jumlahPertemuan)
}
```
## ⚽ Nomor 14

### 📝 Soal
Setiap klub sepakbola peserta English Premier League harus memainkan 38 pertandingan setiap musimnya.  

Buatlah program dalam bahasa Go untuk menghitung:
- Jumlah **point** klub
- Jumlah **gol memasukkan**
- Jumlah **gol kemasukan**
- **Selisih gol** (gol memasukkan - gol kemasukan)

Ketentuan:
- Point menang = 3, draw = 1, kalah = 0  
- Masukan: hasil pertandingan 38 pertandingan  
  - Misal: `4 0` → menang 4-0  
  - `1 1` → draw  
  - `1 2` → kalah  

Keluaran: total point, gol memasukkan, gol kemasukan, selisih gol.

---

### 📥 Input & Output
- **Masukan:** 38 baris, masing-masing dua integer (gol memasukkan dan gol kemasukan)  
- **Keluaran:** empat angka: `total_point total_gol_masukkan total_gol_kemasukan selisih_gol`

---

### 🧪 Test Cases

| Input (beberapa baris) | Result |
| :--- | :--- |
| 4 0<br>1 1<br>1 2<br>… (38 baris) | 66 66 36 30 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    points := 0
    goalsFor := 0
    goalsAgainst := 0
    
    for i := 0; i < 38; i++ {
        var gf, ga int
        fmt.Scan(&gf, &ga)
        
        goalsFor += gf
        goalsAgainst += ga
        
        if gf > ga {
            points += 3
        } else if gf == ga {
            points += 1
        }
    }
    
    goalDifference := goalsFor - goalsAgainst
    fmt.Println(points, goalsFor, goalsAgainst, goalDifference)
}
```
## 🅿️ Nomor 15

### 📝 Soal
Buatlah program dalam bahasa Go untuk menghitung **total uang parkir** yang terkumpul oleh juru parkir di depan Algomaret.

Ketentuan:
- Masukan berupa rangkaian pasangan:
  - Kode kendaraan (`m` = motor, `b` = mobil)
  - Besaran uang parkir (int)  
  - Contoh: `m 15000` → motor membayar Rp 15.000  
            `b 30000` → mobil membayar Rp 30.000
- Pembacaan diakhiri dengan sentinel: `x 0`
- Keluaran: jumlah total uang parkir motor dan mobil

---

### 📥 Input & Output
- **Masukan:** beberapa baris, masing-masing `char int`  
- **Keluaran:** dua angka: `total_motor total_mobil`

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| m 25000<br>b 35000<br>m 45000<br>x 0 | 70000 35000 |
| m 10000<br>b 20000<br>m 30000<br>x 0 | 40000 20000 |
| m 10000<br>b 20000<br>x 0 | 10000 20000 |

---

### 💻 Implementasi Code (Golang)

```go
package main

import "fmt"

func main() {
    var kode string
    var uang int
    
    totalMotor := 0
    totalMobil := 0
    
    for {
        fmt.Scan(&kode, &uang)
        if kode == "x" && uang == 0 {
            break
        }
        
        if kode == "m" {
            totalMotor += uang
        } else if kode == "b" {
            totalMobil += uang
        }
    }
    
    fmt.Println(totalMobil, totalMotor)
}
```
## 🔢 Nomor 16

### 📝 Soal
Buatlah program dalam bahasa Go yang dapat membaca sejumlah bilangan bulat positif dan menentukan **bilangan terbesar** dan **terkecil** dari bilangan-bilangan tersebut.

Ketentuan:
- Masukan berupa bilangan positif
- Pembacaan berhenti saat muncul **0** sebagai sentinel
- Keluaran: bilangan terbesar dan bilangan terkecil

---

### 📥 Input & Output
- **Masukan:** Beberapa baris, masing-masing bilangan positif  
- **Keluaran:** Dua angka: `terbesar terkecil`

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 2 3 4 5 9 4 8 0 | 9 2 |
| 44 32 11 99 0 | 99 11 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
    var num int
    fmt.Scan(&num)
    
    min := num
    max := num
    
    for {
        fmt.Scan(&num)
        if num == 0 {
            break
        }
        
        if num < min {
            min = num
        }
        if num > max {
            max = num
        }
    }
    
    fmt.Println(max, min)
}
```
## 🍎 Nomor 17

### 📝 Soal
Seorang petani mengambil sebanyak `n` sampel buah-buahan dari kebunnya yang terdiri dari **apel**, **jeruk**, dan **mangga**.  

Buatlah program dalam bahasa Go untuk menghitung berapa banyak masing-masing buah yang diambil.

---

### 📥 Input & Output
- **Masukan:**
  - Baris 1: bilangan `n` (jumlah sampel)  
  - Baris 2–n+1: nama buah (`"apel"`, `"jeruk"`, atau `"mangga"`)
- **Keluaran:** Tiga angka: jumlah **apel**, jumlah **jeruk**, jumlah **mangga**

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 5<br>mangga<br>jeruk<br>jeruk<br>jeruk<br>apel | 1 3 1 |
| 2<br>mangga<br>jeruk | 0 1 1 |

---

### 💻 Implementasi Code (Golang)

```go
package main

import (
	"fmt"
	"strings"
)

func main() {
	var n int
	fmt.Scan(&n)

	apel := 0
	jeruk := 0
	mangga := 0

	for i := 0; i < n; i++ {
		var buah string
		fmt.Scan(&buah)

		buah = strings.ToLower(buah)

		if buah == "apel" {
			apel++
		} else if buah == "jeruk" {
			jeruk++
		} else if buah == "mangga" {
			mangga++
		}
	}

	fmt.Println(apel, jeruk, mangga)
}
```
## 🔢 Nomor 18

### 📝 Soal
Buatlah program dalam bahasa Go untuk mencetak barisan bilangan berdasarkan pola berikut:

- Jika sukunya **ganjil** → cetak `2^i`  
- Jika sukunya **genap** → cetak `2^-i`  

Barisan dicetak mulai dari bilangan bulat `n` hingga `m` dengan `n < m`.  
Setiap angka dibulatkan **2 digit di belakang koma**.

---

### 📥 Input & Output
- **Masukan:**  
  - Baris 1: integer `n`  
  - Baris 2: integer `m`
- **Keluaran:**  
  - Barisan bilangan sesuai pola, tiap angka dibulatkan 2 digit di belakang koma

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 1<br>5 | 2.00 0.25 8.00 0.06 32.00 |
| -1<br>1 | 0.50 1.00 2.00 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import (
	"fmt"
	"math"
)

func main() {
	var n, m int
	fmt.Scan(&n, &m)

	suku := 1
	for i := n; i <= m; i++ {
		var hasil float64
		if suku%2 != 0 {
			hasil = math.Pow(2, float64(i))
		} else {
			hasil = math.Pow(2, float64(-i))
		}

		if i == m {
			fmt.Printf("%.2f", hasil)
		} else {
			fmt.Printf("%.2f ", hasil)
		}
		suku++
	}
	fmt.Println()
}
```

## 🕵️‍♀️ Nomor 19

### 📝 Soal
Buatlah program dalam bahasa Go untuk menghitung jumlah **pertemuan rahasia** antara dua orang mata-mata dalam setahun.

Ketentuan:
- Mereka bertemu setiap hari kelipatan `x`, `y`, dan `z`
- Jumlah hari dalam setahun = 365 (hari 1–365)
- Masukan: tiga bilangan bulat positif `x`, `y`, dan `z`
- Keluaran: jumlah pertemuan dalam setahun

---

### 📥 Input & Output
- **Masukan:** Tiga bilangan bulat positif (x y z)  
- **Keluaran:** Jumlah hari pertemuan (int)

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 2 3 4 | 30 |
| 4 5 7 | 2 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
	var x, y, z int
	fmt.Scan(&x, &y, &z)

	jumlahPertemuan := 0

	for hari := 1; hari <= 365; hari++ {
		if hari%x == 0 && hari%y == 0 && hari%z == 0 {
			jumlahPertemuan++
		}
	}

	fmt.Println(jumlahPertemuan)
}
```

## 🕵️‍♂️ Nomor 20

### 📝 Soal
Buatlah program dalam bahasa Go untuk menghitung jumlah **pertemuan rahasia** antara dua mata-mata dalam setahun.

Ketentuan:
- Mereka bertemu setiap hari **kelipatan `x` atau kelipatan `y`**
- Jumlah hari dalam setahun = 365 (hari 1–365)
- Masukan: dua bilangan bulat positif `x` dan `y`
- Keluaran: jumlah hari pertemuan

---

### 📥 Input & Output
- **Masukan:** Dua bilangan bulat positif (x y)  
- **Keluaran:** Jumlah hari pertemuan (int)

---

### 🧪 Test Cases

| Input | Result |
| :--- | :--- |
| 2 3 | 243 |
| 4 5 | 146 |

---

### 💻 Implementasi Code (Golang)

```go
package main
import "fmt"

func main() {
	var x, y int
	fmt.Scan(&x, &y)

	jumlahPertemuan := 0

	for hari := 1; hari <= 365; hari++ {
		if hari%x == 0 || hari%y == 0 {
			jumlahPertemuan++
		}
	}

	fmt.Println(jumlahPertemuan)
}
```