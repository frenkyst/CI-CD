# CI-CD

Apa itu CI/CD?​
CI/CD atau Continuous Integration dan Continuous Deployment merupakan metode untuk mengirimkan perubahan code secara terus menerus hingga aplikasi dapat release ke publik dengan otomatis.

Continuous integration merupakan proses otomatis untuk memastikan semua code sudah berjalan dengan baik, jika terjadi error maka proses tersebut akan diulangi dari awal hingga code tersebut sudah tidak ada error.
Continuous deployment merupakan proses otomatis agar aplikasi yang telah siap di kirim ke server hingga aplikasi dapat diakses secara public.

### Kenapa menggunakan CI/CD​

1. Tanpa menggunakan CI/CD​

    - Proses penyebaran aplikasi dilakukan secara manual
    - Risiko aplikasi tidak berfungsi ketika production lebih besar
    - Rollback ke versi sebelumnya akan lebih sulit jika dilakukan manual

2. Jika menggunakan CI/CD​

    - Dapat menyebarkan aplikasi sesuai dengan permintaan
    - Dapat mengurangi risiko aplikasi tidak berfungsi ketika production
    - Dapat dengan mudah di rollback ke versi sebelumnya jika terjadi error

3. CI/CD Tools​

    - Github Actions
    - GitLab CI/CD
    - Bitbucket Bamboo
    - Jenkins



## Set-Up CI/CD Sederhana

Selain menggunakan tools CI/CD yang telah disebutkan sebelumnya, kita akan mencoba melakukan konfigurasi sederhana untuk memahami konsep dan cara kerja CI/CD menggunakan Cloudflare Pages.

CI/CD Set-Up with Cloudflare​
1. Pastikan kalian sudah melakukan register ke https://cloudflare.com, Jika kalian belum mempunyai akun Cloudflare kalian bisa melakukan registrasi dengan klik link dibawah ini.

LINK Cloudflare : https://dash.cloudflare.com/sign-up

![image](https://user-images.githubusercontent.com/40049149/187872014-5075669a-2218-4860-a070-62232379eac6.png)

2. Jika kalian sudah selesai melakukan registrasi kalian bisa masuk ke menu pages untuk membuat project baru.

image1

3. Selanjutnya Tekan bagian Connect to GitHub, supaya repository di github kita terdeteksi ke Cloudflare Pages

image1

4. Pilih akun yang sesuai. Misalkan saya menggunakan akun pribadi yang bernama demo-dumbways dan pilih satu repository.

image1

5. Jika sudah kalian dapat memilih semua repository maupun salah satu repository saja. Dalam hal ini kita hanya menghubungkan cloudflare pages ke salah satu repository saja.

image1

6. kemudian akan menampilkan halaman berikut, dan bisa klik begin setup untuk proses konfigurasinya.

image1

7. Pastikan untuk mengisi nama dan branch yang digunakan, kemudian pada bagian build settings pilih framework yang digunakan kemudian pastikan untuk memasukkan build commandnya. Jika sudah sesuai langsung saja klik Save and Deploy.

image1
image1

8. Setelah itu kita tunggu saja sampai proses build selesai.

image1

9. Jika proses build berhasil maka akan terlihat seperti berikut.

image1

10. Sekarang kita coba akses aplikasi yang sudah kita deploy menggunakan cloudflare ini dengan url yang ada di sebelah Domains.

image1

11. Berikut adalah website yang telah berhasil dijalankan ke server Cloudflare Pages.

image1

## Update code​

1. Sekarang kita akan mencoba mempraktekkan bagaimana cara kerja dari CI/CD, setiap ada perubahan code maka code tersebut akan dikirimkan ke server Cloudflare Pages.

2. Sekarang kita akan mencoba untuk melakukan perubahan code pada bagian title, Kita coba ubah pada bagian <title> ... </title>, dimaksudkan untuk mengetahui apakah proses CI/CD berhasil atau tidak.

image1

3. Selanjutnya kita coba lihat di Cloudflare pages kita, disini Cloudflare secara otomatis melakukan build ulang, kenapa? karena sebelumnya kita sudah melakukan suatu perubahan di bagian title tadi. Selanjutnya kita tunggu saja sampai proses build selesai.

image1

4. Jika sudah selesai dan proses build telah berhasil, maka akan berubah seperti di bawah ini. Pada bagian title yang sebelumnya Dumbflix - Fadhil Darma Putera Z telah menjadi Dumbflix - Frenky Menther






