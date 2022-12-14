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
1. Pastikan kalian sudah melakukan register ke https://cloudflare.com, Jika kalian belum mempunyai akun __Cloudflare__ kalian bisa melakukan registrasi dengan klik link dibawah ini.

__LINK Cloudflare__ : https://dash.cloudflare.com/sign-up

![image](https://user-images.githubusercontent.com/40049149/187872014-5075669a-2218-4860-a070-62232379eac6.png)

2. Jika kalian sudah selesai melakukan registrasi kalian bisa masuk ke __menu pages__ untuk membuat project baru.

![image](https://user-images.githubusercontent.com/40049149/187875794-8cc2d920-5519-4c17-9fb6-05cb4ba45b26.png)

3. Selanjutnya Tekan bagian __Connect to GitHub__, supaya repository di github kita terdeteksi ke __Cloudflare Pages__

![image](https://user-images.githubusercontent.com/40049149/187875980-db7dbcce-e998-433c-9352-f235a56919b1.png)

![image](https://user-images.githubusercontent.com/40049149/187876526-b83688c2-543c-490d-907c-ed6418082622.png)

4. Pilih akun yang sesuai. Misalkan saya menggunakan akun pribadi yang bernama demo-dumbways dan pilih satu repository (karna saya hanya login satu akun maka akan langsung terhubung dengan akun yang ada).

5. Jika sudah kalian dapat memilih semua repository maupun salah satu repository saja. Dalam hal ini kita hanya menghubungkan __cloudflare pages__ ke salah satu repository saja.

![image](https://user-images.githubusercontent.com/40049149/187876924-407f2140-cdde-43a0-aa08-9f10fbccbbe9.png)

6. kemudian akan menampilkan halaman berikut, dan bisa klik __begin setup__ untuk proses konfigurasinya.

![image](https://user-images.githubusercontent.com/40049149/187880973-d1dc9cd1-7cba-4b62-8145-a41c2e7bdfce.png)

7. Pastikan untuk mengisi nama dan branch yang digunakan, kemudian pada bagian __build settings__ pilih __framework__ yang digunakan kemudian pastikan untuk memasukkan build commandnya. Jika sudah sesuai langsung saja klik __Save and Deploy__.

![image](https://user-images.githubusercontent.com/40049149/187878040-ef1e54a6-6ecf-4d8d-bc9c-b951813f62d8.png)
![image](https://user-images.githubusercontent.com/40049149/187878282-5264b18f-bfe8-44d2-a32f-ed0aa23b557f.png)

8. Setelah itu kita tunggu saja sampai proses build selesai.

![image](https://user-images.githubusercontent.com/40049149/187878496-5dc0b442-9655-4f60-8832-cf12651163f1.png)

9. Jika proses build berhasil maka akan terlihat seperti berikut.

![image](https://user-images.githubusercontent.com/40049149/187879623-bdbce44d-c63c-4661-aafe-68af81c507e6.png)

10. Sekarang kita coba akses aplikasi yang sudah kita deploy menggunakan __cloudflare__ ini dengan url yang ada di sebelah __Domains__.

![image](https://user-images.githubusercontent.com/40049149/187880171-d37619d2-19cb-4e1e-a3d6-d96fa0fdb304.png)

11. Berikut adalah website yang telah berhasil dijalankan ke server __Cloudflare Pages__.

![image](https://user-images.githubusercontent.com/40049149/187880382-fe3a7ba7-77f6-4c98-a581-aa35385fb69e.png)

## Update code​

Sekarang kita akan mencoba mempraktekkan bagaimana cara kerja dari __CI/CD__, setiap ada perubahan code maka code tersebut akan dikirimkan ke server __Cloudflare Pages__.

1. Sekarang kita akan mencoba untuk melakukan perubahan code pada bagian __title__, Kita coba ubah pada bagian __<title> ... </title>__, dimaksudkan untuk mengetahui apakah proses __CI/CD__ berhasil atau tidak.

      Selanjutnya kita akan coba merubah file index.html. Lalu cari tag html <title> dan rubah isinya
    
            git clone git@github.com:frenkyst/wayshub-frontend.git

![image](https://user-images.githubusercontent.com/40049149/187884306-e2ec2fb9-0cb5-44e7-8884-4259cb2b97a3.png)
    
![image](https://user-images.githubusercontent.com/40049149/187885040-674ac4e5-4f1a-4f56-932c-87251e3359a9.png)

            nano public/index.html

![image](https://user-images.githubusercontent.com/40049149/187885230-0c6e6aa8-2e6e-4d4d-9ad2-ca1e83e169fb.png)

   Lakukan add, commit, lalu lakukan push

    
        git add .

        git commit -m "edit titel"

![image](https://user-images.githubusercontent.com/40049149/187887640-da16db93-d1b3-45b0-9214-dd32880047b5.png)

        git push origin main
    
![image](https://user-images.githubusercontent.com/40049149/187887782-357f9eff-1c6e-4776-be96-b914f92840a3.png)


2. Selanjutnya kita coba lihat di __Cloudflare pages__ kita, disini __Cloudflare__ secara otomatis melakukan build ulang, kenapa? karena sebelumnya kita sudah melakukan suatu perubahan di bagian title tadi. Selanjutnya kita tunggu saja sampai proses build selesai.

![image](https://user-images.githubusercontent.com/40049149/187888120-45708738-23c9-4395-8152-60a823f78b85.png)

3. Jika sudah selesai dan proses build telah berhasil, maka akan berubah seperti di bawah ini. Pada bagian title yang sebelumnya __WaysHub__ telah menjadi __WaysHub - Frenky Menther__

![image](https://user-images.githubusercontent.com/40049149/187888313-4f122831-3116-4616-8642-4d154acd5c22.png)





