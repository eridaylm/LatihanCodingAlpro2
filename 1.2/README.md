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