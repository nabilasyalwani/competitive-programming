# Hipotesis Penyelesaian Soal RollBall

## Circular Motion

Hipotesis pertama saya untuk kasus soal ROLLBALL adalah menggunakan rumus Circular Motion, di mana bola menggelinding tanpa slip pada permukaan dalam kerucut tetapi dengan kecepatan yang konstan.

Dengan kecepatan yang konstan, kita dapat mengetahui radius dari titik kontak bola dengan permukaan kerucut dengan persamaan berikut:

$$ r = \frac{v^2 \tan(\theta)}{g} $$

Jika persamaan tersebut diubah bentuk menjadi fungsi mencari kecepatan, maka akan menjadi seperti berikut:

$$ v^2 = \frac{rg}{\tan(\theta)} $$

Namun, hasil yang didapatkan adalah kecepatan \( v \) meningkat secara **monoton** terhadap \( r \). Artinya, semakin besar jari-jari lintasan \( r \), semakin besar pula kecepatan \( v \) yang diperoleh.

Hal ini seharusnya tidak mungkin terjadi, karena dari test case yang diberikan pada soal, keluaran radius titik kontak lebih kecil dari radius awal bola.

Maka dari sini, pendekatan yang saya gunakan masih belum berhasil dan belum sesuai dengan yang diinginkan soal.

## Hamiltonian

Pada website visualisasi gerakan bola dengan pendekatan hamiltonian, saya mencoba mengubah beberapa nilai variabel kondisi awal bola.

Jika diasumsikan bahwa bola bergerak berputar secara horizontal, maka variabel `zdot` harus semakin kecil.

Kemudian, saya mencoba mengubah ketinggian inisialisasi dari bolanya pada variabel `z` dan menemukan bahwa semakin kecil nilainya maka semakin cepat pula gerakan dari bola berputar. Nilai `z` yang semakin kecil menandakan bahwa bola berputar mendekati ujung kerucut.

Dari analisis ini, saya menyimpulkan bahwa kecepatan maksimum bola terjadi saat lintasannya berada pada radius terkecil kerucut. Namun, tidak sampai pada ujung karena radius bola akan sampai di titik menyamai radius lingkaran kerucut sehingga ukuran tersebut menghalangi bola untuk masuk lebih dalam lagi.
