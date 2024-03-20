# Implementasi SOLID *Principle* dan OOP
Sebagai programmer, tentu saja kita pernah mendengar tentang SOLID *principle* dan OOP. Bahkan tanpa disadari, mungkin kita sendiri sudah pernah menggunakan prinsip-prinsip ini sebelumnya. Pada artikel ini, kita akan membahas tentang SOLID *principle* dan OOP mulai dari pengertiannya hingga penerapannya.

## Pengertian SOLID *Principle*
SOLID *principle* merupakan salah satu prinsip yang dapat digunakan sebagai pedoman dalam mengembangkan program perangkat lunak yang lebih baik. SOLID *principle* merupakan akronim/singkatan yang terdiri atas 5 prinsip yang dapat dijabarkan sebagai berikut.
1. Single Responsibility Principle\
    Prinsip ini menyatakan bahwa setiap class, method, dan module hanya dapat memiliki satu tanggung jawab. Dengan menerapkan prinsip ini, kode yang kita kembangkan dapat lebih mudah untuk di-*maintain* dan di-*test*. Selanjutnya, prinsip ini sangat membantu apabila terdapat bug sehingga kita dapat mengisolasi bug tersebut hanya pada satu method atau class. Prinsip ini merupakan salah satu prinsip yang tanpa kita sadari kita pernah memakainya, yaitu saat membuat method/function baru untuk melakukan suatu pekerjaan.

2. Open-closed Principle\
    Prinsip ini menyatakan dua hal, yaitu *open for extension* yang menyatakan bahwa diperbolehkan untuk meng-*extend* *behavior* suatu module dan *closed for modification* yang menyatakan bahwa tidak diperbolekan untuk melakukan modifikasi pada kode yang sudah ada. Contoh penerapan prinsip ini adalah saat kita ingin menambah komponen yang ada dalam suatu class yang sudah rampung, tetapi kita menghindari adanya modifikasi pada kode. Untuk itu, kita dapat melakukan *extend* class dengan *inheritance* sehingga penambahan komponen tersebut dapat dilakukan pada sub-class baru. Prinsip ini sangat bermanfaat untuk menghindari adanya bug pada kode-kode yang sudah baik. 

3. Liskov Subtitution Principle\
    Prinsip ini menyatakan bahwa setiap sub-class harus dapat disubstitusi dengan parent-class nya. Prinsip ini bermanfaat untuk mempertahankan behavior dari parent-class yang ada pada sub-class. Manfaat prinsip ini adalah kita dapat mengurangi masalah pada sistem yang berkaitan dengan implementasi *inheritance* suatu class.

4. Interface Segregation Principle\
    Prinsip ini menyatakan bahwa perlunya untuk membuat interface-interface kecil dibanding satu interface besar. Prinsip ini berfungsi untuk menghindari adanya melakukan implementasi interface yang sebenarnya tidak diperlukan untuk suatu class.

5. Dependecy Inversion Principle\
    Prinsip ini menyatakan bahwa high-level module tidak seharusnya dependen dengan low-level module, tetapi keduanya seharusnya dependen dengan abstraksi. Prinsip ini bermanfaat untuk menghindari perubahan yang ada pada suatu module untuk mempengaruhi module lain.

## Pengertian *Object-Oriented Programming*
*Object-oriented programming* (OOP) adalah suatu paradigma pemrograman yang berorientasi pada konsep objek. Kita sendiri mungkin sudah sangat mengenal dengan paradigma pemrograman ini, yaitu saat kita membuat objek dari class dan menerapkan konsep-konsep seperti *polimorphism* dan *abstraction*. Beberapa bahasa pemrograman mengadaptasi paradigma ini, contohnya adalah pada Python dan Java.

Last modified: {{ .Lastmod.Format "January 2, 2006" }}


