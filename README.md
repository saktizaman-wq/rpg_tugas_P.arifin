Analisis 1:
Mengubah `hero1.hp = 500` secara langsung akan berhasil mengubah nilai HP. Ini karena atribut `hp` masih bersifat publik (*public attribute*), jadi bisa diakses dan diubah langsung dari luar class tanpa adanya pengecekan.

Analisis 2
Menerima objek utuh sebagai parameter `lawan` membuat method `serang` bisa mengakses data lawan dan juga memanggil method yang ada pada objek tersebut, seperti `lawan.diserang(...)'. Ini menunjukkan bagaimana objek dalam OOP bisa saling berinteraksi.

Analisis 3:
Jika `super().__init__()` dihapus dari class `Mage`, saat `eudora.info()` dijalankan akan muncul error `AttributeError: 'Mage' object has no attribute 'name'`. Ini karena constructor dari class `Hero` tidak dijalankan, sehingga atribut seperti `name`, `hp`, dan `attack_power` belum dibuat. Jadi, `super()` digunakan untuk menjalankan constructor dari class induk agar atribut yang diwariskan bisa dibuat juga.

Analisis 4:
`print(hero1._Hero__hp)` masih bisa menampilkan nilai HP karena Python menggunakan mekanisme *Name Mangling*. Walaupun bisa dilakukan, cara ini kurang baik karena bisa melewati aturan enkapsulasi dan validasi yang sudah dibuat. Misalnya, kalau tidak ada pengecekan pada *setter*, `hero1.set_hp(-100)` bisa membuat HP menjadi negatif. Jadi, *setter* digunakan untuk memastikan nilai yang dimasukkan tetap sesuai aturan.

Analisis 5:
Menghapus method `serang` dari `Hero` akan menyebabkan error `TypeError: Can't instantiate abstract class Hero with abstract method serang`. Hal ini terjadi karena `Hero` belum memenuhi method abstrak yang diwajibkan oleh `GameUnit`. Karena itu, objek `Hero` tidak bisa dibuat. `GameUnit()` juga tidak bisa langsung dibuat karena *Abstract Class* hanya digunakan sebagai dasar atau aturan untuk class turunannya, bukan untuk membuat objek secara langsung.

Analisis 6:
Menambahkan class `Healer` tidak perlu mengubah looping `for pahlawan in pasukan:`. Ini salah satu keuntungan Polimorfisme, karena kita bisa menambahkan karakter baru tanpa harus mengubah kode utama. Tetapi kalau nama method `serang` pada class `Archer` diganti menjadi `tembak_panah`, program akan menghasilkan `AttributeError`. Ini karena looping tetap memanggil `serang`, sehingga setiap class yang ingin digunakan dalam looping tersebut perlu memiliki method dengan nama yang sama.
