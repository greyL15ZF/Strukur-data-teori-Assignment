# <h1 align="center">Latihan</h1>
<p align="center">Muhammad Iqbal</p>
<p align="center">2311110013</p>


### <p align="justify">1. Kode di bawah ini belum efisien. Buatlah kode yang efisien dan jelaskan!
#### Kode 1
```C++
#include <iostream>

using namespace std;

bool cekDuplikat(int arr[]) {
    int panjangArr = 4;
    for (int i = 0; i < panjangArr; i++) {
        for (int j = i + 1; j < panjangArr; j++) {
            if (arr[i] == arr[j]) {
                return true;
            }
        }
    }
    return false;
}

int main(void) {
    int arrA[] = {2, 1, 3, 1};
    cout << cekDuplikat(arrA);
    return 0;
}
```

## Jawab

#### Full Screenshoot Kode
![image](https://github.com/greyL15ZF/Strukur-data-teori-Assignment/assets/157208590/19c12b3f-3f78-4c14-b916-ff34df3643fd)


#### Kode Program 2
```C++
#include <iostream>
#include <unordered_set>

using namespace std;

bool cekDuplikat(int arr[], int panjangArr) {
    unordered_set<int> elemenSet;
    for (int i = 0; i < panjangArr; i++) {
        if (elemenSet.find(arr[i]) != elemenSet.end()) {
            return true;
        }
        elemenSet.insert(arr[i]);
    }
    return false;
}

int main(void) {
    int arrA[] = {2, 1, 3, 1};
    int panjangArr = sizeof(arrA) / sizeof(arrA[0]);
    cout << cekDuplikat(arrA, panjangArr);
    return 0;
}
```

#### Output
![image](https://github.com/greyL15ZF/Strukur-data-teori-Assignment/assets/157208590/f235b702-5abe-4457-9fc7-b8e8840252b1)

### Perbedaan kode
#### Pendekatan dan Struktur
- <p align="justify">Kode 2: Menggunakan unordered_set untuk melacak elemen-elemen yang sudah ditemui, memungkinkan pencarian elemen dengan waktu rata-rata O(1).
- <p align="justify">Kode 1: Menggunakan dua loop bersarang untuk membandingkan setiap elemen dengan elemen lainnya, menghasilkan kompleksitas waktu O(n^2).

#### Penanganan Panjang Array
- <p align="justify">Kode 2: Menerima panjang array sebagai argumen dalam fungsi cekDuplikat dan menghitung panjang array di dalam main().
- <p align="justify">Kode 1: Menggunakan panjang array yang di-hardcode menjadi 4 di dalam fungsi cekDuplikat, yang tidak fleksibel jika ukuran array berubah.


#### Efisiensi dan Kompleksitas Waktu
- <p align="justify">Kode 2: Lebih efisien dengan kompleksitas waktu rata-rata O(n) karena menggunakan unordered_set untuk melacak elemen-elemen yang sudah ditemui.
- <p align="justify">Kode 1: Kurang efisien dengan kompleksitas waktu O(n^2) karena menggunakan dua loop bersarang untuk membandingkan setiap elemen dengan setiap elemen lainnya.

#### Kompleksitas Waktu:
- <p align="justify"> A. Kode 2 (Menggunakan unordered_set)
- Loop tunggal iterasi array: O(n)
- Pencarian dan penyisipan elemen dalam unordered_set: O(1) rata-rata
- Kompleksitas total: O(n)

- <p align="justify"> B. Kode 1 (Menggunakan dua loop bersarang):
- Loop luar: O(n)
- Loop dalam: O(n)
- Kompleksitas total: O(n * n) = O(n^2)

<p align="justify">Fungsi cekDuplikat memanfaatkan Di dalam fungsi, kita membuat sebuah objek unordered_set<int> bernama elemenSet. Set ini digunakan untuk menyimpan elemen-elemen yang sudah ditemui dalam array. Selanjutnya, kita melakukan iterasi melalui setiap elemen dalam array menggunakan loop for. Pada setiap iterasi, kita memeriksa apakah elemen tersebut sudah ada dalam set elemenSet menggunakan metode find(). Jika ditemukan bahwa elemen tersebut sudah ada dalam set (artinya elemen tersebut duplikat), maka fungsi mengembalikan true. Jika elemen tidak ditemukan dalam set, maka elemen tersebut dimasukkan ke dalam set menggunakan metode insert(). Jika setelah iterasi selesai tidak ditemukan duplikat, fungsi mengembalikan false. Di dalam main, kita mendeklarasikan sebuah array integer arrA[] dengan nilai {2, 1, 3, 1}. Kemudian, kita menghitung panjang array arrA[] dengan membagi ukuran total array dengan ukuran satu elemen array menggunakan sizeof(arrA) / sizeof(arrA[0]). Hal ini dilakukan agar program bisa bekerja dengan ukuran array yang fleksibel.Selanjutnya, kita memanggil fungsi cekDuplikat() dengan parameter array arrA[] dan panjang array panjangArr, dan mencetak hasilnya ke layar menggunakan cout. Dengan cara ini, program dapat mendeteksi apakah terdapat duplikat dalam array yang diberikan dan mencetak 1 jika ada duplikat, dan 0 jika tidak ada duplikat. 