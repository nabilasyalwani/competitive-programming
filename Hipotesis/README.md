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

## Contact Mechanics

**Update: 01-10-2025**

Beberapa hari terakhir ini saya meninjau ulang kembali soal ROLLBALL dan sepertinya saya mendapatkan perspektif baru mengenai output yang diminta dalam soal. Saya awalnya berasumsi bahwa output yang diminta adalah radius lingkaran kerucut ketika bola berputar secepat mungkin, tetapi setelah saya membaca kembali, sepertinya yang dimaksud oleh soal adalah radius lingkaran yang terbentuk dari titik-titik pada permukaan bola yang kontak dengan permukaan kerucut.

Misalkan diasumsikan kerucut memiliki cat berwarna merah, sehingga ketika ada benda ataupun objek yang melintas di dalam permukaannya, maka akan ada cat yang membekas di benda yang melintas tersebut.

Jika benda yang melintas adalah bola, yang di mana objeknya bisa menggelinding, maka secara otomatis cat yang membekas akan membentuk garis dan menjadi lingkaran di permukaan bola. Jika dimisalkan bola menggelinding dengan rotasi putaran sejajar dengan kemiringan permukaan kerucut, maka tentu saja radius lingkaran yang terbentuk sama dengan radius bola. Akan tetapi, sepertinya karena diasumsikan bola bergerak dengan kecepatan semaksimal mungkin, maka bisa jadi poros rotasinya tidak sejajar dengan bidang kerucut, sehingga radius lingkaran yang terbentuk lebih kecil dari radius bola.

## Rolling Motion

**Update: 15-10-2025**

Ketika bola dilepaskan dari keadaan diam dengan sumbu spin horizontal (θ = 90°), bola akan menggelinding membentuk lintasan melingkar dengan jari-jari R pada permukaan bola itu sendiri. Namun, apabila sumbu spin bola dimiringkan (θ < 90°), maka lintasan melingkar yang terbentuk pada permukaan bola akan memiliki jari-jari r yang lebih kecil dari R. Titik kontak antara bola dan bidang miring terletak di daerah bawah bola, dan dari hubungan geometris diperoleh persamaan

$$ r = R \sin(\theta) $$

Oleh karena itu, jari-jari lintasan kontak yang terbentuk pasti lebih kecil dari radius bola. Untuk menentukan posisi kontak dan hubungan antara translasi serta rotasi, digunakan kondisi rolling without slipping yakni:

$$ v = r\omega $$

Selain itu, berdasarkan penelitian Cross (2015), percepatan bola yang menggelinding menuruni bidang miring tidak bergantung pada kecepatan rotasi awal, kemiringan awal sumbu spin, massa, maupun jari-jari bola. Percepatan tersebut identik dengan bola tanpa spin awal, begitu pula gaya gesek dan koefisien geseknya. Sehingga, kita bisa menentukan kecepatannya dengan mengetahui panjang lintasan bidang, yakni dengan rumus berikut:

$$ v^2 = 2 a x = \frac{g x \sin{\alpha}}{0.7} $$

Setelah nilai kecepatan linear
v diketahui, maka hanya diperlukan satu nilai variabel lagi, yakni w untuk mengetahui radius lingkaran titik kontak bola dengan permukaan kerucut.
