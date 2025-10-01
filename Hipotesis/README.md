# Hipotesis Penyelesaian Soal RollBall

## Circular Motion

**Update: 08-09-2025**

Hipotesis pertama saya untuk kasus soal ROLLBALL adalah menggunakan rumus Circular Motion, di mana bola menggelinding tanpa slip pada permukaan dalam kerucut tetapi dengan kecepatan yang konstan.

Dengan kecepatan yang konstan, kita dapat mengetahui radius dari titik kontak bola dengan permukaan kerucut dengan persamaan berikut:

$$ r = \frac{v^2 \tan(\theta)}{g} $$

Jika persamaan tersebut diubah bentuk menjadi fungsi mencari kecepatan, maka akan menjadi seperti berikut:

$$ v^2 = \frac{rg}{\tan(\theta)} $$

Namun, hasil yang didapatkan adalah kecepatan \( v \) meningkat secara **monoton** terhadap \( r \). Artinya, semakin besar jari-jari lintasan \( r \), semakin besar pula kecepatan \( v \) yang diperoleh.

Hal ini seharusnya tidak mungkin terjadi, karena dari test case yang diberikan pada soal, keluaran radius titik kontak lebih kecil dari radius awal bola.

Maka dari sini, pendekatan yang saya gunakan masih belum berhasil dan belum sesuai dengan yang diinginkan soal.

## Hamiltonian

**Update: 15-09-2025**

Pada website visualisasi gerakan bola dengan pendekatan hamiltonian, saya mencoba mengubah beberapa nilai variabel kondisi awal bola.

Jika diasumsikan bahwa bola bergerak berputar secara horizontal, maka variabel `zdot` harus semakin kecil.

Kemudian, saya mencoba mengubah ketinggian inisialisasi dari bolanya pada variabel `z` dan menemukan bahwa semakin kecil nilainya maka semakin cepat pula gerakan dari bola berputar. Nilai `z` yang semakin kecil menandakan bahwa bola berputar mendekati ujung kerucut.

Dari analisis ini, saya menyimpulkan bahwa kecepatan maksimum bola terjadi saat lintasannya berada pada radius terkecil kerucut. Namun, tidak sampai pada ujung karena radius bola akan sampai di titik menyamai radius lingkaran kerucut sehingga ukuran tersebut menghalangi bola untuk masuk lebih dalam lagi.

## Lagrangian

**Update: 23-09-2025**

Pada pertemuan minggu lalu, saya mendapatkan masukan dari dosen pembimbing bahwa untuk menentukan kecepatan maksimum bola yang berputar mengelilingi permukaan dalam kerucut, diperlukan fungsi waktu sebagai indikator waktu tempuh tercepat. Berdasarkan arahan tersebut, saya kemudian menelusuri beberapa referensi terkait particle in a cone, di mana pendekatan dengan teori Lagrangian banyak digunakan. Saya mencoba menuliskan kembali bentuk kasar persamaannya dengan tujuan mendapatkan fungsi waktu tersebut, namun ketika sampai pada tahap penurunan persamaan kecepatan, saya mengalami kesulitan dan belum menemukan cara untuk melanjutkannya.

![WhatsApp Image 2025-10-01 at 09 22 45](https://github.com/user-attachments/assets/bb8028d0-f7f9-4c14-9afc-d4a56d153ef2)

## Contact Point

**Update: 01-10-2025**

Beberapa hari terakhir ini saya meninjau ulang kembali soal ROLLBALL dan sepertinya saya mendapatkan perspektif baru mengenai output yang diminta dalam soal. Saya awalnya berasumsi bahwa output yang diminta adalah radius lingkaran kerucut ketika bola berputar secepat mungkin, tetapi setelah saya membaca kembali, sepertinya yang dimaksud oleh soal adalah radius lingkaran yang terbentuk dari titik-titik pada permukaan bola yang kontak dengan permukaan kerucut.

Misalkan diasumsikan kerucut memiliki cat berwarna merah, sehingga ketika ada benda ataupun objek yang melintas di dalam permukaannya, maka akan ada cat yang membekas di benda yang melintas tersebut.

Jika benda yang melintas adalah bola, yang di mana objeknya bisa menggelinding, maka secara otomatis cat yang membekas akan membentuk garis dan menjadi lingkaran di permukaan bola. Jika dimisalkan bola menggelinding dengan rotasi putaran sejajar dengan kemiringan permukaan kerucut, maka tentu saja radius lingkaran yang terbentuk sama dengan radius bola. Akan tetapi, sepertinya karena diasumsikan bola bergerak dengan kecepatan semaksimal mungkin, maka bisa jadi poros rotasinya tidak sejajar dengan bidang kerucut, sehingga radius lingkaran yang terbentuk lebih kecil dari radius bola.

![Ilustrasi titik kontak](https://github.com/user-attachments/assets/8476c5c0-f6d8-47cd-b47f-14b1dd664cb6)

