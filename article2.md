# Teamwork dalam GitLab

Kita semua pasti pernah tergabung di dalam tim, baik dalam permainan maupun dalam pekerjaan. Satu hal yang perlu ada dalam suatu tim adalah adanya kerjasama sehingga proses yang kita lakukan dapat berjalan dengan baik dan efektif. Pada kali ini, kita akan membahas proses kerjasama tim dengan menggunakan bantuan tools pada GitLab.

## Fitur Kerjasama GitLab
Selain GitLab berguna sebagai remote repository dari project, kita juga dapat menggunakan GitLab untuk dapat bekerjasama dengan tim, seperti melihat progres dari teman dan berkomunikasi. Salah satu cara untuk melakukan proses ini adalah lewat *merge request*. *Merge request*(MR) adalah proses request untuk melakukan merge kumpulan commit yang ada pada suatu branch ke branch lain. Dalam proses merge request ini, kita dapat melakukan *code review* terhadap proses pengerjaan teman kita dengan membaca deskripsi MR, membaca kode pada commit, dan memberikan komentar terhadap commit yang terdapat di dalam MR. Selain itu, kita juga dapat melakukan approval/reject terhadap MR sehingga apabila terdapat kesalahan, perubahan tersebut tidak akan dapat di merge.

## Contoh Kerjasama dalam GitLab
### Pembuatan *Merge Request*
Pada bagian ini, akan dicontohkan cara membuat *merge request* terlebih dahulu. Hal ini dapat dilakukan dengan memilih menu Code->Merge requests yang terletak pada sidebar. [create]({{site.baseurl}}assets/article2/Screenshot+2024-03-06+084329)

Setelah itu, pilih New merge request dan pilih source dan target branch. Setelah itu tekan *Compare branches and continue*. Halaman akan berganti ke halaman pembuatan *merge request*. Pada halaman tersebut. Isilah judul dari *merge request* dan hal-hal lainnya yang diinginkan, seperti deskripsi MR, *assignees*, *reviewers*, dll. Setelah mengisi hal-hal yang diinginkan, tekan *Create merge request* dan akan terbuat *merge request* baru.

Berikut ini merupakan contoh *merge request* yang sudah terbentuk.

### Komunikasi dalam *Merge Request*
Setelah terbentuknya MR, kita dapat memulai membuat komentar terhadap MR. Hal ini dapat dilakukan dengan mengisi kolom komentar yang ada pada halaman MR.

Komentar yang telah dibuat akan ditanggapi oleh pembuat MR dengan menulis reply pada komentar.

Setelah komentar telah ditanggapi, pembuat MR dapat menekan tombol resolve thread yang menandakan sudah dilakukannya perubahan untuk menyesuaikan dengan komentar. Berikut ini merupakan contoh komunikasi dalam *merge request*.

Saat merasa MR yang dilakukan oleh teman kita sudah baik, kita dapat memberikan approval dengan menekan tombol Approve.

Pada MR milik kita, apabila semua komentar telah di-*resolved*, kita dapat menekan tombol merge untu melakukan merge dengan branch yang kita tuju.

## Tips Bekerja sama dalam *Merge Request*
Beberapa tips yang dapat diterapkan dalam proses *merge request* menurut penulis.
1. Tulislah judul yang singkat dan jelas serta tulislah deskripsi yang berisikan detail pekerjaan yang dilakukan.
2. Berikan syarat approval sehingga perubahan yang dilakukan tidak dapat langsung di merge dan perlu adanya *review* dari teman kita.
3. Berikan komentar yang konstruktif di dalam MR teman kita.

## Penutup
Proses kerjasama dalam *merge request* akan terasa melelahkan untuk kita, terutama apabila kita perlu me-*review* kode teman kita atau perlu membuat deskripsi yang jelas untuk MR yang kita buat. Namun, hal ini sangat penting untuk meningkatkan kualitas dari kode yang sudah kita buat. Oleh karena itu, kita harus belajar terus melakukan kerjasama dalam *merge request* sehingga kita dapat memberikan hasil yang terbaik.
