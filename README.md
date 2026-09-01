Jawaban Analisis Tugas Praktikum

Analisis 1:
Mengubah hero1.hp = 500 secara langsung akan berhasil karena hp bersifat publik. Jadi, nilainya bisa diakses dan diubah dari luar class tanpa pengecekan.

Analisis 2:
Parameter lawan yang berupa objek membuat method serang bisa mengakses data dan method milik lawan, seperti lawan.diserang(...). Ini menunjukkan bagaimana objek dalam OOP bisa saling berinteraksi.

Analisis 3:
Jika super().**init**() dihapus dari Mage, akan muncul error karena atribut seperti name, hp, dan attack_power belum dibuat. super() digunakan untuk menjalankan constructor dari class induk agar atribut tersebut tetap dibuat.

Analisis 4:
print(hero1._Hero__hp) masih bisa menampilkan HP karena adanya Name Mangling. Tapi cara ini kurang baik karena bisa melewati enkapsulasi dan validasi. Tanpa pengecekan pada setter, hero1.set_hp(-100) juga bisa membuat HP menjadi negatif.

Analisis 5:
Jika method serang dihapus dari Hero, akan muncul error karena Hero belum memenuhi method abstrak dari GameUnit. Hero tidak bisa dibuat sebagai objek sebelum method tersebut diimplementasikan. Abstract Class sendiri digunakan sebagai dasar untuk class turunannya.

Analisis 6:
Class Healer bisa ditambahkan tanpa mengubah looping for pahlawan in pasukan:. Ini karena Polimorfisme membuat beberapa jenis objek bisa diproses dengan cara yang sama. Jika serang pada Archer diganti menjadi tembak_panah, akan muncul AttributeError karena looping tetap memanggil method serang.
