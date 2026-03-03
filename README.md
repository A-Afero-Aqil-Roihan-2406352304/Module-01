# Reflection 

# Module 01
## Reflection 01

prinsip clean code yang saya sudah terapkan di source code saya adalah meaningful names. Di kode ini, saya berusaha menamakan setiap variabel dan metode dengan nama yang dapat membuat orang langsung dapat mengerti tujuan dari variabel atau metode tersebut hanya dari namanya. Lalu saya juga menggunakan comment di kode yang memang butuh penjelasan, jadi tidak asal menaruh.  contoh penggunaan comment saya adalah di ProductRepositoryTest.

Hal yang dapat di-_improve_ dari kode saya adalah tampilan dari editProduct.html yang dapat lebih bagus dan menarik lagi. Dapat dilihat bahwa tampilan dari page editproduct tersebut masih merupakan tampilan HTML saja dan belum ada _styling_, sehingga itulah yang saya akan perbaiki nantinya.

## Reflection 02
Setelah membuat unit test, saya merasa lebih lega karena mengetahui kode yang saya buat bisa berjalan dengan benar. Banyaknya unit test yang harus dibuat di sebuah class tergantung banyaknya atribut (buat setter dan getter) dan metode yang ada di class tersebut. Cara kita memastikan unit test kita sudah cukup untuk memverifikasi program kita, adalah sampai code coverage mencapai 100%. Namun, code coverage 100% tidak berarti program bebas dari bug, karena code coverage hanya memeriksa apakah suatu baris di kode sudah dijalankan di unit-test, tidak memperhatikan apkah baris yang dijalankan itu sudah dicek kebenarannya.

What do you think about the cleanliness of the code of the new functional test suite? Will
the new code reduce the code quality? Identify the potential clean code issues, explain
the reasons, and suggest possible improvements to make the code cleaner!

Kebersihan kodenya akan menurun karena akan banyak duplikasi kode dari pembuatan functional test yang baru ini. Kualitas Kode akan menurun jug karena kode akan memiliki _readability_ yang lebih kecil akibat banyaknya kode yang berulang.
Saran : Gunakan konsep inheritance, jadi semua konfigurasi yang sama antar functional test akan diletakkan di parent, dan semua test yang baru akan diletakkan di child. Hal ini akan mengurangi duplikasi pada kode.

# Module 02

## Reflection 1
Perbaikan yang saya lakukan:
Saya mengatasi error dependensi dengan menghapus library yang tidak valid seperti spring-boot-starter-webmvc dan menggantinya dengan spring-boot-starter-web. Langkah bertujuan untuk memastikan pengelolaan dependensi menjadi lebih bersih dan mencegah konflk versi saat kompilasi. 
Saya memisahkan eksekusi unit test dan functional test untuk mempercepat feedback loop dalam pengembangan. Strategi ini dilakukan dengan menambahkan filter excludeTestsMatching("*FunctionalTest") pada build.gradle.kts agar task test utama hanya menjalankan pengujian unit yang cepat. 
Saya memperbaiki masalah pelaporan code coverage yang sebelumnya tidak terdeteksi oleh SonarCloud. saya mengaktifkan format laporan XML pada konfigurasi jacocoTestReport (xml.required.set(true)), sehingga SonarCloud menampilkan coverage.


## Reflection 2
Workflow saya sudah mengimplementasikan Continous Integration. Hal ini dikarenakan setiap push/pull, workflow akan secara otomatis melakukan tests berupa test jacoco dan sonarcloud. 
Namun workflow saya masih belum bisa mengimplementasikan Continous Deployment. Hal ini dikarenakan saya belum dapat mendeploy projek saya ke Koyeb, Render, ataupun layanan lain yang serupa.
Saya baru membuat dockerfile dan isinya untuk packaging (progress CD). Kedepannya saya akan menambahkan pekerjaan yang langsung deploy proyek saya ke Koyeb ketika terdapat push di main branch.

