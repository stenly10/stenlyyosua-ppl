# Article 1: Menambah Attribute dosen tambahan Pada Model Pi, Proceeding, dan Sm

Pada artikel ini, saya akan menjelaskan task yang saya ambil, yaitu untuk mengubah attribute dosen menjadi list.
Sebelum mengerjakan task, saya mencoba memahami kode yang sudah ada terlebih dahulu dan saya menemukan
kode yang sudah ada sangatlah rumit dan akan membutuhkan waktu yang sangat lama untuk melakukan penyesuaian.
Selain akan memakan waktu yang sangat lama, akan sangat berisiko apabila langsung mengubah kolom dosen pada ketiga model yang ada.
Contoh risiko yang ada adalah dapat menyebabkan bug yang cukup fatal di mana sistem akan langsung tidak bekerja dan kegagalan sistem karena kegagalan migration.

Oleh karena alasan-alasan tersebut, saya mencoba mengambil pendekatan lain, yaitu tidak mengubah attribut dosen yang sudah ada, tetapi menambahkan attribute baru bernama dosen_tambahan. Dengan menambahkan attribute tersebut, logic sistem yang sudah ada saat ini tidak akan terganggu dan penyesuaian nantinya dapat dilakukan secara bertahap. Selain itu, proses migration kemungkinan besar tidak akan terganggu karena konflik dengan data lama dapat dihindari.

Dengan berdasarkan hal tersebut, saya mencoba untuk membuat test dan kode untuk pengimplementasiannya. Namun, saat saya ingin mengimplementasikan, ternyata default database django tidak bisa menampung data array sehingga perlu adanya penyesuaian kembali. Pendekatan yang saya gunakan kali ini adalah dengan menggunakan ManyToManyField di mana field ini akan membuat hubungan ManyToMany antara model Pi, Proceeding, dan Sm dengan model dosen.

Sekian dari yang saya kerjakan, berikut merupakan lampiran kode-kode yang saya gunakan.

1. Kode test (contoh: Pi)
   ```
   def test_attr_dosen_tambahan_pi_model(self):
        semester = "2022-23/Genap"
        nama = "nama"
        npm_or_nip = 210101010
        judul = "judul"
        topik = "topik"
        dosen1 = baker.make(dosen)
        abstrak = "abstrak"
        dosen2 = baker.make(dosen)
        dosen3 = baker.make(dosen)
        
        new_pi = Pi.objects.create(semester=semester,
                          nama=nama,
                          npm_or_nip=npm_or_nip,
                          judul = judul,
                          topik = topik,
                          dosen = dosen1.user.username,
                          abstrak = abstrak)
        new_pi.dosen_tambahan.add(dosen2, dosen3)
        new_pi.save()

        dosen_tambahan = new_pi.dosen_tambahan.all()
        self.assertTrue(dosen2 in dosen_tambahan and dosen3 in dosen_tambahan)
   ```
2. Kode penambahan attribute
   ```
   ...
   dosen_tambahan = models.ManyToManyField(Dosen, null=True, blank=True)
   ...
   ```


