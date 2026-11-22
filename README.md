# Tubuh Ideal

Aplikasi web ringan (PWA) berbahasa Indonesia untuk:

- menghitung **BMI** beserta kategorinya,
- menampilkan **berat ideal** (IMT dan Broca),
- memprediksi **tinggi badan dewasa** dari tinggi orang tua,
- membandingkan tinggi dengan **rata-rata Indonesia**,
- memberi saran dan tautan bacaan lanjutan.

Tanpa framework, tanpa backend, tanpa pelacakan. Semua hitungan berjalan di perangkat pengguna dan aplikasi bisa dipakai offline setelah dibuka sekali.

## Struktur

```
index.html            halaman dan logika aplikasi
manifest.webmanifest  data agar bisa dipasang seperti aplikasi
sw.js                 service worker (cache offline)
icons/                ikon aplikasi
LICENSE               MIT
```

## Menjalankan

Cukup buka `index.html` di browser. Agar fitur pasang dan offline aktif, jalankan lewat server lokal:

```
python -m http.server 8000
```

lalu buka `http://localhost:8000`.

## Menayangkan gratis lewat GitHub Pages

1. Buat repositori baru di GitHub (publik), lalu unggah semua isi folder ini.
2. Buka **Settings > Pages**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
3. Tunggu beberapa menit. Alamatnya: `https://NAMA-PENGGUNA.github.io/NAMA-REPO/`

Setelah itu, buka alamat tersebut di Chrome Android, ketuk menu titik tiga, lalu **Pasang aplikasi** atau **Tambahkan ke layar utama**.

Setiap kali mengubah file, naikkan angka `VERSI` di `sw.js` agar cache pengguna diperbarui.

## Rumus

- **BMI** = berat (kg) / tinggi (m)². Kategori: kurus < 18,5; normal 18,5 sampai < 25; gemuk 25 sampai < 30; obesitas 30 ke atas.
- **Broca** = (tinggi cm - 100) dikurangi 10% (pria) atau 15% (wanita).
- **Prediksi tinggi** (tinggi potensi genetik): pria = (ibu + 13 + ayah) / 2; wanita = (ayah - 13 + ibu) / 2. Kisaran sekitar plus minus 8,5 cm.
- **Rata-rata tinggi Indonesia** yang dipakai: sekitar 166 cm (pria) dan 154 cm (wanita), perkiraan dari NCD-RisC dan World Population Review. Sumber lain bisa memberi angka sedikit berbeda. Ubah di variabel `RATA` pada `index.html`.

## Catatan penting

Aplikasi ini hanya alat bantu edukasi dan bukan alat diagnosis. BMI dan Broca adalah indikator kasar. Untuk kondisi kesehatan tertentu, konsultasikan ke dokter atau ahli gizi.

## Berkontribusi

Pull request dan saran sangat diterima, misalnya:

- menambah bahasa lain,
- menambah sumber bacaan yang tepercaya,
- memperbarui data rata-rata tinggi dan klasifikasi (misalnya versi Kemenkes),
- memperbaiki aksesibilitas.

## Lisensi

[MIT](LICENSE)
