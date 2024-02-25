# Pengimplementasian Test-Driven Development pada Framework Django dengan Memanfaatkan Git

## Pengenalan TDD
Test-Driven Development merupakan salah-satu metode dalam pembuatan kode. Dalam metode ini, programmer dipaksa untuk memikirkan hal-hal yang dibutuhkan dalam pembuatan kode, seperti input, output, dll., dan disusun dalam bentuk unit test. Programmer dipaksa untuk membuat test terlebih dahulu sebelum membuat kode di mana kode yang nantinya dibuat akan fokus untuk membuat test berhasil. Metode ini akan membantu programmer agar lebih terarah dalam pembuatan kode sehingga kode yang dihasilkan dapat lebih berkualitas.

## Proses-proses pada TDD
Dalam pengimplementasian metode Test-Driven Development, terdapat proses-proses yang perlu dilakukan.
   1. **Membuat test**, 
      Sebelum membuat kode, programmer akan membuat test untuk kode yang akan dibuat. Programmer memikirkan hal-hal yang dibutuhkan pada kode, membuat testnya, dan membuat kode untuk menyukseskan unit test. Setelah membuat test, programmer dapat mem-*push* kode test tersebut dengan tag [RED] sebagai penanda dimulainya pengembangan dengan test.
   2. **Membuat kode**, 
      Setelah membuat unit test, programmer akan mulai menyusun kode untuk menyukseskan unit test. Kode yang dibuat harus seminimum mungkin yang berfokus pada tujuannya, yaitu menyukseskan unit test. Setelah membuat kode, programmer dapat mem-*push* kode tersebut dengan tag [GREEN] sebagai penanda berhasilnya menyukseskan test.
   3. **Melakukan refactor**, 
      Setelah membuat unit test dan kode, programmer dapat melakukan refactor terhadap unit test dan kode yang telah dibuat apabila ada hal-hal yang terlewat atau ada hal-hal yang ingin di-*improve*. Proses ini dapat ditandai dengan tag [REFACTOR].

## Panduan Pengimplementasian TDD
Dalam mengimplementasikan TDD, terdapat tiga panduan dari Uncle Bob Martin yang dapat digunakan sebagai patokan.
   1. You are not allowed to write any production code unless it is to make a failing unit test pass.
   2. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
   3. You are not allowed to write any more production code than is sufficient to pass the one failing unit test.

## Contoh Pengimplementasian TDD pada Framework Django
Pada bagian ini, akan didemonstrasikan penerapan TDD pada framework Django. Contoh kasus yang akan digunakan adalah membuat fungsi untuk membuat dosen.
Models yang akan digunakan adalah models Dosen dengan spesifikasi sebagai berikut.
```
class Dosen(models.Model)
   nama = models.CharField(max_length = 50)
   nip = models.CharField(max_length = 30)
```

Tahap-tahap yang akan dilakukan dalam pembuatan fungsi.
1. **Membuat test**,
   Dalam membuat unit test, pikirkan apa yang akan dibutuhkan dalam fungsi, contoh pada kasus ini parameter yang dibutuhkan adalam nama dan nip karena kedua hal tersebut merupakan data yang dibutuhkan untuk membuat instance Dosen dan contoh nilai return yang dapat digunakan adalah instance dari Dosen tersebut. Selain itu, pikirkan apa yang akan di-test untuk fungsi tersebut, pada kasus ini contohnya adalah testing *value* yang ada pada setiap attribute dari dosen. Berikut ini merupakan contoh kode testnya.
   ```
   class DosenTest(TestCase)
      def test_create_dosen(self):
         nama = "dosen"
         nip = "1807829173"
         dosen = createDosen(nama, nip)
         self.assertEqual(nama, dosen.nama)
         self.assertEqual(nip, dosen.nip)
   ```
   Setelah membuat test, lakukanlah `git push` untuk mem-*push kode* ke remote repository. Berikan tag [RED] pada commit message.

2. **Membuat kode**, 
   Setelah membuat test, rancanglah kode yang akan dibuat. Berikut ini merupakan contoh kode implementasi.
   ```
   def createDosen(nama, nip):
      dosen = Dosen.objects.create(nama=nama, nip=nip)
      dosen.save
      return dosen
   ```
   Setelah membuat kode, lakukanlah `git push` untuk mem-*push kode* ke remote repository. Berikan tag [GREEN] pada commit message apabila kode yang dibuat sudah berhasil menyukseskan test yang telah dibuat sebelumnya.

Pengimplementasian metode TDD ini mungkin akan terasa sedikit sulit pada awalnya, tetapi jangan menyerah, terus mencoba, dan belajar dari kesalahan.

## Referensi
1. [Wiki PPL CS UI](https://wiki.ppl.cs.ui.ac.id/doc/panduan-tdd-clean-code-HmM8qKI0yk)
